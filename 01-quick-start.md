---
layout: page
title:  "Quickstart Guide"
---
# Quickstart Guide

## Before you begin

1. [Register a Twitter application]({{site.baseurl}}/02-twitter-setup)  
2. [Make sure you have Python installed]({{site.baseurl}}/04-install-python)
3. [Learn some command line basics]({{site.baseurl}}/03-command-line-basics)

## Start twarcing

1. Open the Terminal application (MacOS users), or Command Prompt (Windows users), and [navigate]({{site.baseurl}}/03-command-line-basics) into the directory where you want to save your tweet data.

2. pip [install]({{site.baseurl}}/05-install-twarc) twarc by entering the following command: 

       pip install twarc

   MacOS users may also have the option of installing twarc via homebrew using the command:

       brew install twarc

3. Grant twarc access to your twitter account using your application's [API keys]({{site.baseurl}}/02-twitter-setup#accessing-keys-and-tokens):

        twarc configure

4. Use twarc to [search]({{site.baseurl}}/06-twarc-command-basics#search) for tweets:

        twarc search climatestrike > tweets.jsonl
