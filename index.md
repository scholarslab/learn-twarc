---
layout: default
---

# Learn Twarc

## From Documenting the Now

twarc is a command line tool and Python library for archiving Twitter JSON data.
Each tweet is represented as a JSON object that is
[exactly](https://dev.twitter.com/overview/api/tweets) what was returned from
the Twitter API.  Tweets are stored as [line-oriented JSON](https://en.wikipedia.org/wiki/JSON_Streaming#Line-delimited_JSON).  Twarc will handle
Twitter API's [rate limits](https://dev.twitter.com/rest/public/rate-limiting)
for you. In addition to letting you collect tweets Twarc can also help you
collect users, trends and hydrate tweet ids.

twarc was developed as part of the [Documenting the Now](http://www.docnow.io)
project which was funded by the [Mellon Foundation](https://mellon.org/).