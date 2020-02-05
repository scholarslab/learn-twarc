---
layout: page
title: Install Python
---

# Python Installation Guide

### [for MacOS](#python-for-mac-os) \| [for Windows](#python-for-windows)

## Python for Mac OS

### Check your Python version (Mac users)
Python should come already installed on MacOS. But we need to make sure you have a version compatible with Twarc.

1. Open Terminal, type in the following command, and then press enter. 
    
        python --version

    If you already have Python installed, the above command will print the version number:

    ![Screen shot of python version command]({{ site.url }}{{ site.baseurl }}/assets/images/python-v.png)

    To check if you have Python 3, enter the command: 
    
        python3 --version

    If you have Python 3 installed, this will print the version number:

    ![Screen shot of python 3 version command]({{ site.url }}{{ site.baseurl }}/assets/images/python-3-v.png)

2. Make sure you have at least 2.7, Python 3 is ideal. 

3. Otherwise, install the most current version of Python 3 (or update if you currently have Python 2). Visit [https://www.python.org/downloads/](https://www.python.org/downloads/){:target="_blank"} for the latest version. It is fine to download Python 3 if you currently have Python 2 on your system, both versions can coexist without conflict. 

## Python for Windows

### Install Python

Python does not come standard on Windows, so you will need to download the software if you have not previously done so. If you have Anaconda on your computer, you may need to follow another process for installing twarc. 

1. Visit [https://www.python.org/downloads/](https://www.python.org/downloads/){:target="_blank"} to download the latest version of Python. 

2. When the installer opens, **make sure to check the box for ‘Add Python to Path’**, then click ‘Install Now’:

    ![Screen shot of python install setup]({{ site.url }}{{ site.baseurl }}/assets/images/python-win.png)

3. When the setup completes, you will be prompted with an option to ‘Disable path length limit’. Click to select this option:

    ![Screen shot of python setup]({{ site.url }}{{ site.baseurl }}/assets/images/python-install-2.png)

4. After this configuration is set, Python should be successfully installed on your computer. You can check to make sure Python was installed correctly by entering the command `python --version` in your Command Prompt:

    ![Screen shot of python setup]({{ site.url }}{{ site.baseurl }}/assets/images/python-version.png)
