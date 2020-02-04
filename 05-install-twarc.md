---
layout: page
title: Install & Configure Twarc
---

# Installing and Configuring Twarc

_Required for this step:_
- _[Make sure Python is installed]({{site.baseurl}}/04-install-python)_
- _[Have your Twitter application API keys and tokens on hand]({{site.baseurl}}/02-twitter-setup#accessing-keys-and-tokens)_

[Twarc for MacOS](#twarc-for-mac-os) \| [Twarc for Windows](#twarc-for-windows)

## Twarc for Mac OS
_For Windows users, click [here](#twarc-for-windows)_

### Installing Twarc

1. Open the Terminal application (located in the applications folder).
2. Pip install Twarc by entering the following command: 

       pip install twarc

   _Note: [Pip](https://pip.pypa.io/en/stable/installing/){:target="_blank"} is already installed if you are using Python 2 ≥ 2.7.9 or Python 3 ≥ 3.4_

   macOS users may also have the option of installing Twarc via homebrew using the command:

       brew install twarc

### Configuring Twarc

To get started, you will need to tell Twarc about your application API keys and grant access to one or more Twitter accounts. Follow these directions to configure Twarc:

1. Enter the following command in Terminal:

       twarc configure

2. Twarc will ask you to enter several keys. You should have these keys ready to go after [registering an application]({{site.baseurl}}/02-twitter-setup#accessing-keys-and-tokens). 

   ![Screen shot of twarc configuration]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-config.png)

   Type or copy/paste your consumer key, then press **enter**. Next, Twarc will ask for your consumer secret. Type or copy/paste your consumer secret, then press **enter**.

3. Next, Twarc will ask you to log into your twitter account. Copy/paste the provided URL into your browser to authorize your application. 

4. Following the provided URL will bring you to a page that looks something like this:

   ![Screen shot of twitter authorize page]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-authorize.png)

   Click 'Authorize app'. A pin number will be provided, Type this pin into your terminal, as seen in step 3, then press **enter**.

5. After entering your pin, your terminal should give a message telling you where your twitter credentials are saved, followed by "Happy twarcing!" This means your twarc installation is configured. 

Next, learn the basics of collecting twitter data: [Twarc Command Basics]()

## Twarc for Windows

### Installing Twarc

1. Open the Command Prompt program (Windows PowerShell is another option).
2. Pip install Twarc by entering the following command: 

       pip install twarc

   _Note: [Pip](https://pip.pypa.io/en/stable/installing/){:target="_blank"} is already installed if you are using Python 2 ≥ 2.7.9 or Python 3 ≥ 3.4_

### Configuring Twarc

To get started, you will need to tell Twarc about your application API keys and grant access to one or more Twitter accounts. Follow these directions to configure Twarc:

1. Enter the following command in you command line:

       twarc configure

2. Twarc will ask you to enter several keys. You should have these keys ready to go after [registering an application]({{site.baseurl}}/02-twitter-setup#accessing-keys-and-tokens).

    ![Screen shot of twarc configuration]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-config.png)

    Type or copy/paste your consumer API key, then press **enter**. Next, Twarc will ask for your consumer secret. Type or copy/paste your consumer API secret, then press **enter**. 

3. Next, Twarc will ask you to log into your twitter account. Copy/paste the provided URL into your browser to authorize your application.

4. Following the provided URL will bring you to a page that looks something like this:

    ![Screen shot of twitter authorize page]({{ site.url }}{{ site.baseurl }}/assets/images/twitter-authorize.png)

    Click Authorize app. A pin number will be provided. Type this pin into your terminal where requested, then press **enter**.

5. After entering your pin, your terminal should give a message telling you where your twitter credentials are saved, followed by “Happy twarcing!” This means your twarc installation is configured.

Next, learn the basics of collecting twitter data: [Twarc Command Basics]()