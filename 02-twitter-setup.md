---
layout: page
title: Twitter Setup
---

# Setting up your Twitter Account for Collecting
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Steps for Creating a Twitter Application

_Please note that these instructions may be subject to change with updates to Twitter. If the following steps and screenshots do not match precisely, please use this as a general guide, or contact [DocNow](https://www.docnow.io/){:target="_blank"}._
{: fw-300 }

1. If you do not have a twitter account, create one at [twitter.com](https://twitter.com/){:target="_blank"}. A twitter account is required for access to twitter data. 

2. Log into you twitter account to set-up and and authorize a twitter application. A Twitter application will let you download twitter data using Python. 
   
   Create an app at [developer.twitter.com/en/apps](https://developer.twitter.com/en/apps){:target="_blank"}

   Following the above link should bring you to this page:

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/developer-page.png)

3. Click on 'Create an App'

   You may be prompted to create a Twitter developer account. Select 'Apply' and continue:

   ![Screen shot of Twitter Developers Site popup]({{ site.url }}{{ site.baseurl }}/assets/images/developer-popup.png)

### Setting up a Twitter Developer Account

If you already have a developer account set up, skip to [Creating a Twitter App](#creating-a-twitter-app).

1. Select a user profile to associate with the developer account, and select 'Continue'.

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/select-account.png)

2. In the 'Account details' section, select your request for access for either your organization or for personal use. 

   **Note:** Selecting "for my own personal use" offers the simplest and quickest method of setting up a developer account. If you are following this guide for research or teaching purposes, an individual, personal account is suggested. Twitter users can only have a single development account, and cannot change account types. An 'Organization' account differs in that it allows for additional twitter users to share access on a single dev account, however, this is mainly geared toward commercial use and is intended for development for premium APIs ($), and is outside the scope of this guide. For more, see [Twitter's FAQ](https://developer.twitter.com/en/docs/basics/developer-portal/faq.html){:target="_blank"}.

    - If you select "for my own personal use," you will be prompted to fill in an Account Name and to select your Primary Country of Operation. Both are required.


3. In the next section on 'Use Case Details', answer several questions about your project and why you are building an app to gather twitter data. You can provide answers similar to the ones below if relevant to your project. **Most importantly note that this is for academic purposes and that you will not be Tweeting, Retweeting, or liking content.**

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-use-case.png)

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-use-case-4.png)

   **Note:** If your project does involve analysis of twitter content, an answer for question #2 might look something like "Yes, my project will analyze tweets using text analysis, word clouds, word frequency, and word association using R."

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-use-case-5.png)

4. Read and Accept the Twitter Terms of Service.

5. Verify your Twitter Development Account via the email associated with your Twitter account. 

    ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-verify.png)

### Creating a Twitter App

1. Once you have your Twitter Developer Account set up, you can register an application at [developer.twitter.com/en/apps](https://developer.twitter.com/en/apps){:target="_blank"}. Click 'Create an App' to begin:

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/developer-page.png)

2. Fill out the required parts of the form for App Details. For the Website URL, you can simply put the URL for your twitter account, or any website you are affiliated with:

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-app-4.png)

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-app-5.png)

3. Click 'Create'. A pop-up may appear for reviewing the Twitter Developer Terms, click 'Create' to continue.

4. You now have a registered Twitter app! You can edit any of these fields later from your [Developer Account Apps page](https://developer.twitter.com/en/apps){:target="_blank"}.

### Accessing Keys and Tokens

1. From your [Developer Account Apps page](https://developer.twitter.com/en/apps){:target="_blank"}, find your app and click 'Details'.

   ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-app-3.png)

2. Select the option for 'Keys and Tokens'. On this page you will find your Consumer API keys. Under 'Access token & access token secret', click 'create' to generate. 

    ![Screen shot of Twitter Developers Site]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-keys-1.png)

   Note down for use with Twarc these four alphanumeric values:
   - Consumer API key
   - Consumer API secret 
   - Access token 
   - Access token secret

_Updated: April 25, 2019_