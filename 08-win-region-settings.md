---
layout: default
title: Change Character Encoding (Windows Users)
---

# Change Character Encoding (Windows Users)

The twitter datasets you’ll be creating with Twarc contain characters, like emojis, that require your computer’s console to use Unicode UTF-8 character encoding. This is not default for Windows computers.

To change these settings (**Windows 10 required**):

1. From your taskbar, search for the program **Run**. Click to open:

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/run_app.png)

2. Type **intl.cpl** into the prompt and click **OK**:

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/run_region.png)

3. This opens your Region settings (which can also be accessed via control panel, we just used a shortcut). Select the tab for **Administrative**:

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/region_set.png)

4. Under ‘Language for non-Unicode Programs’, click the button for ‘Change system locale…’

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/region_set_2.png)

5. Check the box for ‘Beta: Use Unicode UTF-8 for worldwide language support”

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/region_set_3.png)

6. Click OK.

7. An an alert box will appear telling you to restart your computer. Click ‘Restart now’ to restart your computer with these settings saved. 

8. You can uncheck these settings later if you’d prefer. These settings are only required when using selected Utilities, like emojis, hashtags, users, and others. 

    If you do not change this region setting, you will see an error message like the below when you try to run these Twarc utilities:

    ![Screenshot of unicode encode error]({{ site.url }}{{ site.baseurl }}/assets/images/encode-error.png)

**[- Return to Twarc Utilities Guide for Windows -]({{site.baseurl}}/07-utilities-windows)**

