---
layout: default
title: Twarc Utilities for Windows
---

# Twarc Utilities for Windows
{: .no_toc }

**This guide is optimized for Windows users** (tutorial for MacOS users [here]({{site.baseurl}}/07-utilities-mac)). Windows 10 is required. 

To use the following utilities, make sure the JSONL file of collected tweet data you want to use is in the same folder as the utils folder (but not inside this utils folder).

**Important Note:** At the time of writing this, Windows does not play well with certain Unicode UTF-8 characters, including emojis, that are commonly found in tweet datasets. Without making any changes to your computer's settings, you will likely run into an error while using many of the twarc utilities that looks like this:

![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/encode-error.png)

**Fix this:** You can [change your Region settings]({{site.baseurl}}/08-win-region-settings) for Unicode UTF-8 character encoding. Follow the instructions, [here]({{site.baseurl}}/08-win-region-settings). You can change these settings back later if you'd prefer.

For the following twarc lessons, all <code><span style="color:blue">blue text</span></code> can be modified to fit your purpose. These are either file names or search/filter terms. 

Use the Table of Contents below to quickly navigate this guide. 

### Table of contents
{: .no_toc }

1. TOC
{:toc}

---

## Tweet Count
To get the total number of tweets in your dataset, enter the command below:

<code>find /v /c “” <span style="color:blue">tweets</span>.jsonl</code>

## Convert JSON to CSV
Use the following command to create a csv file (spreadsheet): 

<code>python utils/json2csv.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets</span>.csv</code>

Output: Creates a .csv file with the following tweet attributes:
Id, tweet_url, created_at, parsed_created_at, user_screen_name, text, tweet_type, coordinates, hashtags, media, urls, favorite_count, in_reply_to_screen_name, in_reply_to_status_id, in_reply_to_user_id, lang, place, possibly_sensitive, retweet_count, retweet_or_quote_id, retweet_or_quote_screen_name, retweet_or_quote_user_id, source, user_id, user_created_at, user_default_profile_image, user_description, user_favourites_count, user_followers_count, user_friends_count, user_listed_count, user_location, user_name, user_statuses_count, user_time_zone, user_urls, user_verified

See the [Tweet Data Dictionary](https://developer.twitter.com/en/docs/tweets/data-dictionary/overview/tweet-object) for a complete description of these attributes. 

## Users
To count the number of unique users in the dataset, enter the following command:

<code>python utils/users.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">users</span>.txt</code>

This will create a text file listing all users in the dataset.

## Hashtags
To to get a list of all the unique hashtags used in the dataset, enter the following command:

<code>python utils/tags.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_hashtags</span>.txt</code>

## Emojis
To see a list of all emojis in the dataset, use the following command: 

<code>python utils/emojis.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets</span>.txt</code>

Output: Creates a text file with all emojis and number count:

![Screenshot of emoji txt file]({{ site.url }}{{ site.baseurl }}/assets/images/emoji-win.png)

Most Windows programs use black and white emoji characters (Notepad was used to open the text file above). You have a few options:

1. Change the font to Segoe UI Emoji. In Notepad, click the option Format > Font to change font to Segoe UI Emoji:
    ![Screenshot of emoji txt file]({{ site.url }}{{ site.baseurl }}/assets/images/emoj2.png)

    They will probably still be in black and white, but the emojis are more current and legible:
    ![Screenshot of emoji txt file]({{ site.url }}{{ site.baseurl }}/assets/images/emoj3.png)

2. To view in color, copy/paste the contents of your text file into a browser based text editor. Some options include:
    - Enter the following into the address bar in Chrome: `data:text/html, <html contenteditable>`
    - Copy/paste your emoji text into the blank browser page:
    ![Screenshot of emoji txt file]({{ site.url }}{{ site.baseurl }}/assets/images/emoj4.png)

    - Other browser text editors:
        - [https://www.editpad.org/](https://www.editpad.org/)
        - [https://microsoft.github.io/roosterjs/index.html](https://microsoft.github.io/roosterjs/index.html)
        - [http://textpad.surge.sh/](http://textpad.surge.sh/)

## Wordcloud

To create a wordcloud, use the following command (_see note below_): 

<code>python utils/wordcloud.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">wordcloud</span>.html</code>

Output: Creates an html file, open in your browser to see wordcloud.

![Screenshot of wordcloud]({{ site.url }}{{ site.baseurl }}/assets/images/wordcloud.png)
 
_Note on wordclouds:_ Consider [removing retweets](#remove-retweets-from-jsonl) from your dataset when creating your wordcloud. With retweets included, the text from the original tweet is shortened in the dataset, and can create odd/deceptive wordclouds. 

_Example:_

From original dataset: | After retweets removed:
![Screenshot of wordcloud]({{ site.url }}{{ site.baseurl }}/assets/images/wordcloud-1.png) | ![Screenshot of wordcloud]({{ site.url }}{{ site.baseurl }}/assets/images/wordcloud-2.png)
              
_That large red “arm…” in the original dataset was from a highly retweeted tweet, where the word “army” was cut off mid-word in the retweet data._ 

## Tweet Network Graph
Create a network graph from your tweet data, use the following command (note there is no ‘>’ in this command between the jsonl file name and the html file name): 

<code>python utils/d3_network.py <span style="color:blue">tweets</span>.jsonl <span style="color:blue">tweet_graph</span>.html</code>

Output: Creates an html file, open in your browser to view the network graph of your tweets. This script only shows a graph of original tweets that have been quoted and/or have replies (not the entire dataset). Hover over circles to show connections, click to show tweet (if you click and no tweet appears, it was likely deleted or set private)

![Screenshot of tweet network]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-network.png)

To **include retweets** in your network graph, use the following command (if you have a very large dataset, this will take a long time to load, and may be too crowded to read well):

<code>python utils/d3_network.py --retweets <span style="color:blue">tweets</span>.jsonl <span style="color:blue">tweet_graph</span>.html</code>

Output: an html file of your network graph, including retweets. Open in browser:

![Screenshot of tweet network w retweets]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-network-retweets.png)

## Create Geojson
Use the following command: 

<code>python utils/geojson.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets</span>.geojson</code>

Output: Creates a .geojson file. Quickly create map from geojson file:
- [Geojson.io](http://geojson.io): Drag and Drop your geojson file into the </>JSON left panel to create map:
    ![Screenshot of geojson.io map]({{ site.url }}{{ site.baseurl }}/assets/images/geojson.png)
- With a github account, logged in: [https://gist.github.com/](https://gist.github.com/), drag geojson file into browser window, and save gist. Will automatically make into a map

## Tweet Wall
Create a wall of tweets, use the following command: 

<code>python utils/wall.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets</span>.html</code>

Output: Creates an html file, open in your browser to view all tweets, easy to browse through. 

![Screenshot of tweet wall]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-wall.png)

## Media URLs
Creates a text file the URLs of images uploaded to Twitter in a tweet json. Use the following command: 

<code>python utils/media_urls.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_media</span>.txt</code>

Output: Creates a text document with the tweet ids and media urls. 

For just a list of embedded media URLs (without the associated tweet id):

<code>python utils/embeds.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_embeds</span>.txt</code>

## Remove Retweets from JSONL
Creates a new JSONL file with retweets removed. Use the following command: 

<code>python utils/noretweets.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_noretweets</span>.jsonl</code>

## Sort Tweets Chronologically 
Tweet IDs are generated chronologically. This command will sort your tweet data by Tweet ID in ascending order, which is the same as sorting by date:

<code>python utils/sort_by_id.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_sorted</span>.jsonl</code>

Another option is to [create a csv](#convert-json-to-csv), open in Excel and sort the “id” column by ascending and descending order to identify the first and last tweets in your dataset.

## Remove Tweets Before Certain Date
You may want to study tweets from only a select number of days in your dataset. For example, you’ve searched a hashtag related to an event that occured within the last two days, but your search query retrieves tweets from the previous seven days. 

Use this command to remove tweets occurring before a given date: 

<code>python utils\filter_date.py --mindate <span style="color:blue">13-oct-2019</span> <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">filtered</span>.jsonl</code>

## Remove Duplicate Tweets
Creates a new JSONL file with no duplicate tweets. This script removes any tweets with duplicate IDs. Use the following command: 

<code>python utils/deduplicate.py <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweets_deduped</span>.jsonl</code>
