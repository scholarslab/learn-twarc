---
layout: default
title: Twarc Usage Guide for MacOS
---
# Twarc Usage Guide for MacOs
{: .no_toc }

**This guide is optimized for Mac users** (tutorial for Windows users [here]({{site.baseurl}}/06-usage-windows)).

For the following twarc lessons, all <code><span style="color:blue">blue text</span></code> can be modified to fit your purpose. These are either file names or search/filter terms. 

Use the Table of Contents below to quickly navigate this guide. 

### Table of contents
{: .no_toc }

1. TOC
{:toc}

---

## Search
This uses Twitter's [search/tweets](https://developer.twitter.com/en/docs/api-reference-index) to download _pre-existing_ tweets from the prior 7 days matching a given query. You can use any word or hashtag, capitalization does not matter in this case. If you search for a phrase (that includes spaces between words), enclose it within quotes, i.e. “climate strike”. The 7 day window is imposed by Twitter’s search API. To collect tweets as they happen in real time, use the filter command.
 
Type the following into your command prompt and press enter: 

<code>twarc search <span style="color:blue">blacklivematter</span> > <span style="color:blue">tweets</span>.jsonl</code>

- Your collection may take some time to return all tweets. You can tell when the process has completed if your terminal has returned to the shell ($) prompt:

    ![Screen shot of twarc search command]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-search.png)

- While the prompt is running, check to make sure your command was successful by looking inside the twarc folder. Inside you should see your tweets.jsonl file and a twarc.log file (You don't need to open these files, just make sure they've been created.):

    ![Screen shot of twarc log files]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-data-folder.png)

- You can stop the process at any time by entering **Ctrl + C**, but to get the entire collection for your search query, you must keep the process running until it completes. 

## More Search Examples

Search for tweets from a single user:

<code>twarc search <span style="color:blue">from:aoc</span> > <span style="color:blue">tweets_aoc</span>.jsonl</code>

The best way to get familiar with Twitter's search syntax is to experiment with Twitter's [Advanced Search](https://twitter.com/search-advanced) and copy and pasting the resulting query from the search box. 

For example, here is a more complicated query that searches for tweets containing either the words climate or action and the hashtag #NewGreenDeal that were sent to @aoc:

![Screen shot of advanced search field]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-advanced.png)

For this advanced search query, copy/paste the search box query, contained between two single quotes ('') into the twarc search command:

<code>twarc search <span style="color:blue">'(climate OR action) (#greennewdeal) (to:aoc)'</span> > <span style="color:blue">tweets</span>.jsonl</code>

For more on using the Twarc search command, see the [Search section](https://github.com/DocNow/twarc#search) of DocNow’s [Twarc Usage guide](https://github.com/DocNow/twarc#usage).

## Filter

The filter command will use Twitter's [statuses/filter](https://dev.twitter.com/streaming/reference/post/statuses/filter) API to collect tweets as they happen. Type the following into your command prompt and press **enter**:

<code>twarc filter <span style="color:blue">climatestrike</span> > <span style="color:blue">tweets</span>.jsonl</code>

- The filter command will run as long as you let it. You may need a designated computer to run this process without interruption, depending on how long you want to collect tweets for a given query. 
- End the process by entering **Ctrl + C**.

To collect tweets from a given user id as they happen (this example is collecting tweets from @cnn, you can get an account’s user id using the [Users](#users) twarc command below):

<code>twarc filter --follow <span style="color:blue">759251</span> > <span style="color:blue">tweets</span>.jsonl</code>

Note that the syntax for the Twitter's track queries is slightly different than what queries in their search API. Please consult the documentation on how best to express the filter option you are using. For more on using the Twarc filter command, see the [Filter section](https://github.com/DocNow/twarc#filter) of DocNow’s [Twarc Usage guide](https://github.com/DocNow/twarc#usage).

## Users

The users command will return User metadata for the given screen names:

<code>twarc users <span style="color:blue">cnn</span> > <span style="color:blue">users</span>.jsonl</code>

You can also input user ids:

<code>twarc users <span style="color:blue">1232134,1413213</span> > <span style="color:blue">users</span>.jsonl</code>

You can also use a text file of user ids, which can be useful if you are using the [followers](#followers) and [friends](#friends) commands below:

<code>twarc users <span style="color:blue">ids</span>.txt > <span style="color:blue">users</span>.jsonl</code>

## Followers

The followers command will use Twitter's follower id API to collect the follower user ids for exactly one user screen name per request as specified as an argument:

<code>twarc followers <span style="color:blue">deray</span> > <span style="color:blue">follower_ids</span>.txt</code>

The result will include exactly one user id per line. The response order is reverse chronological, or most recent followers first.

## Friends

Like the followers command, the friends command will use Twitter's friend id API to collect the friend user ids for exactly one user screen name per request as specified as an argument:

<code>twarc friends <span style="color:blue">deray</span> > <span style="color:blue">friend_ids</span>.txt<code>

## Dehydrated and Rehydrated Data Sets

Twitter API’s [Terms of Service](https://developer.twitter.com/en/developer-terms/policy#6._Be_a_Good_Partner_to_Twitter) does not allow for making large amounts of raw Twitter data available on the Web. The fully-hydrated Twitter data you collect using Twarc can be used for research and archived for local use, but cannot be shared publicly. However, Twitter does allow files of tweet identifiers to be publicly shared. This is useful for when you would like to make a dataset of tweets available, for example, in [DocNow’s Tweet Catalogue](https://www.docnow.io/catalog/). This is referred to as a “dehydrated” data set - each tweet is reduced to its unique ID number, and a list of these IDs is saved as a text document. 

A dehydrated data set can be “rehydrated” using Twarc - Twitter will take each ID and search the current Twitterverse for a corresponding tweet. If it locates a tweet that matches the ID, it will return the original JSON code for that tweet. This process is called “rehydration”, and will return a JSON file containing the data for every tweet that it was able to locate. It’s important to note that any tweet rehydrator can only check for tweets that are currently live - they cannot find tweets that have been deleted or made private since the original collection event.

### Dehydrate your Dataset

Each Tweet in your dataset has a unique identifier. Twarc’s dehydrate command will generate a list of tweet ids from a JSONL file of tweets. To dehydrate your tweets, enter the following command:

<code>twarc dehydrate <span style="color:blue">tweets</span>.jsonl > <span style="color:blue">tweet_ids</span>.txt</code>

- You should now have a text file in your twarc folder containing the unique tweet ids of all tweets in your dataset.
- Open the .txt file to see the list of unique tweet ids:

![Screen shot of tweet ids txt file]({{ site.url }}{{ site.baseurl }}/assets/images/tweet-ids.png)


### Rehydrate a Dataset

Twarc’s hydrate command will read your file of unique identifiers and write out the tweet JSON for them using Twitter’s [status/lookup](https://developer.twitter.com/en/docs/api-reference-index) API. This is useful if you have a set of Twitter ids from another institution and would like to view the full dataset. Documenting the Now has a collection of Tweet ids that you can explore and rehydrate [here](https://www.docnow.io/catalog/).

Rehydrate your dataset by entering the following command:

<code>twarc hydrate <span style="color:blue">tweet_ids</span>.txt > <span style="color:blue">tweets_hydrated</span>.jsonl</code>

- You now have your tweets in JSONL format ready to go in your twarc folder. 