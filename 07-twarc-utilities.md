---
layout: page
title: Twarc Utilities
---

# Twarc Utilities 

Twarc comes with a set utilities that will help you explore the data you’ve collected. To begin, first [download the utilities folder from github](#get-the-utilities-from-github). 

Next, [install a few python modules](#install-relevant-python-packages) required for some of the utilities. See [here](#install-relevant-python-packages) for details.

Then, select the relevant utilities guide:
### [for MacOS]({{site.baseurl}}/07-utilities-mac) \| [for Windows]({{site.baseurl}}/07-utilities-windows)

---

## Get the Utilities from Github

1. Go to the DocNow Twarc Github page: [https://github.com/DocNow/twarc](https://github.com/DocNow/twarc){:target="_blank"}

2. Find and click on the green button towards the right side of the page that says **Clone or download**: 

    ![Screenshot of github clone button]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-github.png)

3. Download and unzip the compressed folder to your computer: click **Download ZIP** from the drop-down options. (Use git clone if familiar)

4. Navigate to the location on your computer where you want to download the Twarc folder and click save. Save to your desktop for easy access.

5. Open the folder location and unzip the compressed folder to access the contents.

6. Inside you will find a folder labeled **utils**. Copy or move this entire folder into the folder where you've saved your twitter json files:

    ![Screenshot of twarc folder with utils]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-utils.png)

    The **utils** folder has a bunch of python (.py) files inside. You don't need to directly open these files, unless you're familiar with python and want to explore them further.

    ![Screenshot of twarc folder with utils]({{ site.url }}{{ site.baseurl }}/assets/images/twarc-utils-2.png)

For the purposes of this tutorial, all you need to do is make sure the JSONL file of collected tweet data you want to use is in the same folder as the utils folder (but not inside this utils folder, see screenshot above for an example).

## Install relevant Python packages

pip install the following packages for the associated utility. You'll only need to do this step once. If you run a twarc utility and recieve an error `requires <something> module`, you can follow the pattern below, and enter the command, `pip install <something>`, and/or search for the package on [https://pypi.org/](https://pypi.org/) 

Open the Terminal application (MacOS users), or Command Prompt (Windows users), and enter the following, one at a time:

### For the emoji utility:

    pip install emoji

Installs the [emoji package](https://pypi.org/project/emoji/)

### For the tweet network graph:

    pip install networkx

Installs the [networkx package](https://pypi.org/project/networkx/)



