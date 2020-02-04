---
layout: page
title: Twarc Command Basics
---

# Start Collecting: Twarc Command Basics
{: .no_toc }

Let’s start collecting tweets! Consider using a spreadsheet to keep track of the datasets you create using Twarc. You can use this [Collection Template](https://docs.google.com/spreadsheets/d/1FJ-wdIXZWcA8OTc1A9xtkVrho6FZ8TwkdVpbaoK4CRA/edit?usp=sharing){:target="_blank"} to get started. Click on the [template link](https://docs.google.com/spreadsheets/d/1FJ-wdIXZWcA8OTc1A9xtkVrho6FZ8TwkdVpbaoK4CRA/edit?usp=sharing){:target="_blank"} to open, select File > Make a Copy to create an editable document in your Google Drive. 

## Using Twarc: A Typical Workflow
{: .no_toc }

Each time you use twarc to collect twitter data, start here:
1. **Use the command line to navigate into your twarc folder**
    - **Open** the Terminal application (MacOS users), or Command Prompt (Windows users) 
    - **Navigate** into the twarc folder on your desktop, or another folder where you want to save your twitter data, using the [`cd` **change directory** command]({{site.baseurl}}/03-command-line-basics). In your shell prompt, type in `cd` followed by the path of your twarc folder, then press enter.
2. **Start Twarcing!**
    - **Enter** the twarc commands into your command line, following the detailed usage guide below. 
    - **Usage Guides:** [for MacOS](#for-mac-os) \| [for Windows](#for-windows)

For the following twarc lessons, all <code><span style="color:blue">blue text</span></code> can be modified to fit your purpose. These are either file names or search/filter terms. 

Use the Table of Contents below to quickly navigate this guide. 

### Table of contents
{: .no_toc }

1. TOC
{:toc}

---

## For Mac OS

### Search
This uses Twitter's [search/tweets](https://developer.twitter.com/en/docs/api-reference-index) to download _pre-existing_ tweets from the prior 7 days matching a given query. You can use any word or hashtag, capitalization does not matter in this case. If you search for a phrase (that includes spaces between words), enclose it within quotes, i.e. “climate strike”. The 7 day window is imposed by Twitter’s search API. To collect tweets as they happen in real time, use the filter command.
 
Type the following into your command prompt and press enter: 

<code>twarc search <span style="color:blue">blacklivematter</span> > <span style="color:blue">tweets</span>.jsonl</code>

- Your collection may take some time to return all tweets. You can tell when the process has completed if your terminal has returned to the shell ($) prompt:

    ![Screen shot of twarc search command]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-search.png)

- While the prompt is running, check to make sure your command was successful by looking inside the twarc folder. Inside you should see your tweets.jsonl file and a twarc.log file (You don't need to open these files, just make sure they've been created.):

    ![Screen shot of twarc log files]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-data-folder.png)

- You can stop the process at any time by entering **Ctrl + C**, but to get the entire collection for your search query, you must keep the process running until it completes. 

### More Search Examples

Search for tweets from a single user:
twarc search from:aoc > tweets_aoc.jsonl
The best way to get familiar with Twitter's search syntax is to experiment with Twitter's Advanced Search and copy and pasting the resulting query from the search box. 
For example, here is a more complicated query that searches for tweets containing either the words climate or action and the hashtag #NewGreenDeal that were sent to @aoc:

For this advanced search query, copy/paste the search box query, contained between two single quotes ('') into the twarc search command:
twarc search '(climate OR action) (#greennewdeal) (to:aoc)' > tweets.jsonl
For more on using the Twarc search command, see the Search section of DocNow’s Twarc Usage guide.

### Filter

The filter command will use Twitter's statuses/filter API to collect tweets as they happen. Type the following into your command prompt and press enter:
twarc filter climatestrike > tweets.jsonl
The filter command will run as long as you let it. You may need a designated computer to run this process without interruption, depending on how long you want to collect tweets for a given query. 
End the process by entering Ctrl + C.
To collect tweets from a given user id as they happen (this example is collecting tweets from @cnn, you can get an account’s user id using the Users twarc command below):
twarc filter --follow 759251 > tweets.jsonl
Note that the syntax for the Twitter's track queries is slightly different than what queries in their search API. Please consult the documentation on how best to express the filter option you are using. For more on using the Twarc filter command, see the Filter section of DocNow’s Twarc Usage guide.

### Users

The users command will return User metadata for the given screen names:
twarc users cnn > users.jsonl
You can also give it user ids:
twarc users 1232134,1413213 > users.jsonl
You can also use a text file of user ids, which can be useful if you are using the followers and friends commands below:
twarc users ids.txt > users.jsonl

### Followers

The followers command will use Twitter's follower id API to collect the follower user ids for exactly one user screen name per request as specified as an argument:
twarc followers deray > follower_ids.txt
The result will include exactly one user id per line. The response order is reverse chronological, or most recent followers first.

### Friends

Like the followers command, the friends command will use Twitter's friend id API to collect the friend user ids for exactly one user screen name per request as specified as an argument:
twarc friends deray > friend_ids.txt

### Dehydrated and Rehydrated Data Sets

Twitter API’s Terms of Service does not allow for making large amounts of raw Twitter data available on the Web. The fully-hydrated Twitter data you collect using Twarc can be used for research and archived for local use, but cannot be shared publicly. However, Twitter does allow files of tweet identifiers to be publicly shared. This is useful for when you would like to make a dataset of tweets available, for example, in DocNow’s Tweet Catalogue. This is referred to as a “dehydrated” data set - each tweet is reduced to its unique ID number, and a list of these IDs is saved as a text document. 

A dehydrated data set can be “rehydrated” using Twarc - Twitter will take each ID and search the current Twitterverse for a corresponding tweet. If it locates a tweet that matches the ID, it will return the original JSON code for that tweet. This process is called “rehydration”, and will return a JSON file containing the data for every tweet that it was able to locate. It’s important to note that any tweet rehydrator can only check for tweets that are currently live - they cannot find tweets that have been deleted or made private since the original collection event.

#### Dehydrate your Dataset

Each Tweet in your dataset has a unique identifier. Twarc’s dehydrate command will generate a list of tweet ids from a JSONL file of tweets. To dehydrate your tweets, enter the following command:
        twarc dehydrate tweets.jsonl > tweet_ids.txt
You should now have a text file in your twarc folder containing the unique tweet ids of all tweets in your dataset:
Open the .txt file to see the list of unique tweet ids:

#### Rehydrate a Dataset

Twarc’s hydrate command will read your file of unique identifiers and write out the tweet JSON for them using Twitter’s status/lookup API. This is useful if you have a set of Twitter ids from another institution and would like to view the full dataset. Documenting the Now has a collection of Tweet ids that you can explore and rehydrate here.
Rehydrate your dataset by entering the following command:
        twarc hydrate tweet_ids.txt > tweets_hydrated.jsonl
You now have your tweets in JSONL format ready to go in your twarc folder. 

## For Windows

### Search
This uses Twitter's search/tweets to download pre-existing tweets from the prior 7 days matching a given query. You can use any word or hashtag, capitalization does not matter in this case. If you search for a phrase (that includes spaces between words), enclose it within quotes, i.e. “climate strike”. The 7 day window is imposed by Twitter’s search API. To collect tweets as they happen in real time, use the filter command. 
 
Type the following into your command prompt and press enter: 
twarc search climatestrike > tweets.jsonl
Your collection may take some time to return all tweets. You can tell when the process has completed if your terminal has returned to the shell prompt (C:\):

While the prompt is running, check to make sure your command was successful by looking inside the twarc folder. Inside you should see your tweets.jsonl file and a twarc.log file:

You can stop the process at any time by entering Ctrl + C, but to get the entire collection for your search query, you must keep the process running until it completes. 
### More Search Examples
Search for tweets from a single user:
twarc search from:aoc > tweets_aoc.jsonl
The best way to get familiar with Twitter's search syntax is to experiment with Twitter's Advanced Search and copy and pasting the resulting query from the search box. 
For example, here is a more complicated query using Advanced Search that searches for tweets containing either the words climate or action and the hashtag #NewGreenDeal that were sent to @aoc:

For this advanced search query, copy/paste the search box query, contained between two single quotes ('') into the twarc search command:
twarc search '(climate OR action) (#greennewdeal) (to:aoc)' > tweets.jsonl
For more on using the Twarc search command, see the Search section of DocNow’s Twarc Usage guide.
### Filter
The filter command will use Twitter's statuses/filter API to collect tweets as they happen. Type the following into your command prompt and press enter:
twarc filter climatestrike > tweets.jsonl
The filter command will run as long as you let it. You may need a designated computer to run this process without interruption, depending on how long you want to collect tweets for a given query. 
End the process by entering Ctrl + C.
To collect tweets from a given user id as they happen (this example is collecting tweets from @cnn, you can get an account’s user id using the Users twarc command below):
twarc filter --follow 759251 > tweets.jsonl
Note that the syntax for the Twitter's track queries is slightly different than what queries in their search API. Please consult the documentation on how best to express the filter option you are using. For more on using the Twarc filter command, see the Filter section of DocNow’s Twarc Usage guide.
### Users
The users command will return User metadata for the given screen names:
twarc users cnn > users.jsonl
You can also give it user ids:
twarc users 1232134,1413213 > users.jsonl
You can also use a text file of user ids, which can be useful if you are using the followers and friends commands below:
twarc users ids.txt > users.jsonl
### Followers
The followers command will use Twitter's follower id API to collect the follower user ids for exactly one user screen name per request as specified as an argument:
twarc followers deray > follower_ids.txt
The result will include exactly one user id per line. The response order is reverse chronological, or most recent followers first.
### Friends
Like the followers command, the friends command will use Twitter's friend id API to collect the friend user ids for exactly one user screen name per request as specified as an argument:
twarc friends deray > friend_ids.txt
### Dehydrated and Rehydrated Data Sets
Twitter API’s Terms of Service does not allow for making large amounts of raw Twitter data available on the Web. The fully-hydrated Twitter data you collect using Twarc can be used for research and archived for local use, but cannot be shared publicly. However, Twitter does allow files of tweet identifiers to be publicly shared. This is useful for when you would like to make a dataset of tweets available, for example, in DocNow’s Tweet Catalogue. This is referred to as a “dehydrated” data set - each tweet is reduced to its unique ID number, and a list of these IDs is saved as a text document. 
A dehydrated data set can be “rehydrated” using Twarc - Twitter will take each ID and search the current Twitterverse for a corresponding tweet. If it locates a tweet that matches the ID, it will return the original JSON code for that tweet. This process is called “rehydration”, and will return a JSON file containing the data for every tweet that it was able to locate. It’s important to note that any tweet rehydrator can only check for tweets that are currently live - they cannot find tweets that have been deleted or made private since the original collection event.
#### Dehydrate your Dataset
Each Tweet in your dataset has a unique identifier. Twarc’s dehydrate command will generate a list of tweet ids from a JSONL file of tweets. To dehydrate your tweets, enter the following command:
twarc dehydrate tweets.jsonl > tweet_ids.txt
You should now have a text file in your twarc folder containing the unique tweet ids of all tweets in your dataset.
Open the .txt file to see the list of unique tweet ids:

#### Rehydrate a Dataset
Twarc’s hydrate command will read your file of unique identifiers and write out the tweet JSON for them using Twitter’s status/lookup API. This is useful if you have a set of Twitter ids from another institution and would like to view the full dataset. DocNow has a collection of Tweet ids that you can explore and rehydrate here.
Rehydrate your dataset by entering the following command:
twarc hydrate tweet_ids.txt > tweets_hydrated.jsonl
You now have your tweets in JSONL format ready to go in your twarc folder. 



