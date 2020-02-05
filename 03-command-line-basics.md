---
layout: page
title: Command Line Basics
---

# Command Line Basics

Twarc requires familiarity with using the command line to navigate your file system, configure twarc, and run queries. We've provided some quick practice to get help you gain comfort with the command line.

### [for MacOS](#practice-with-command-line-for-mac-os) \| [for Windows](#practice-with-command-line-for-windows)

## Practice with Command Line for Mac OS

_For Windows users, click [here](#practice-with-command-line-for-windows)_

1. The Terminal app can be found in the Utilities folder in Applications.

    ![Screen shot of Terminal program]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-1.png "Terminal app")

    - The shell or command prompt is the line where you type in commands, which are then passed on to the computer’s operating system to run. 
    - Here, the shell prompt includes your user profile (`UL-EAM5HC-MBP13`), current directory (`eam5hc`) followed by `$`. Yours should look similar. 
    - After entering a command, you can tell when the process is complete when it returns to the shell prompt (`$`). 

2. Create a new folder on your desktop named twarc. Now let’s navigate into this folder. This is the same process as moving through folders in your Finder window. In this example, the twarc folder has been saved to the desktop for simplicity. Adjust accordingly if you’ve saved it elsewhere. 

3. To navigate into a folder, or directory, use the `cd` (change directory) command. Type ‘cd’ into the shell prompt, followed by a space, and then the name of the directory you’re moving into.

    - Capitalization and spacing matters. Navigating onto your desktop requires ‘Desktop’ with a capital ‘D’.
    - Instead of typing in the file path, you can also drag and drop the folder into the command prompt after the cd and the path with autofill (just be sure to include a space after `cd` ):

    ![Screen shot of terminal cd drag]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-cd-drag.png "Drag folder into terminal")
    - You can also use the ‘tab’ key to autofill the rest of a directory’s name.

4. Press **enter** to change directories. You’ll notice that your shell prompt will update to include the name of your current directory/folder (`twarc eam5hc$`): 

    ![Screen shot of terminal cd command]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-cd.png "Cd into directory")

5. If you get lost in your filesystem or want to double check that you are in the expected folder, use the command `pwd` (print working directory) to display your current directory. In the command prompt type pwd and press enter:

    ![Screen shot of terminal pwd command]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-pwd.png "print working directory")

6. To see the list of files and folders within your current directory, use the `ls` (list files) command:

    ![Screen shot of terminal ls command]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-ls.png "list files in directory")

7. To navigate back, from the current directory into its parent directory, use the command `cd`, followed by a space and two periods:

    ![Screen shot of terminal cd command]({{ site.url }}{{ site.baseurl }}/assets/images/terminal-parent.png "navigate into parent directory")

There is a lot you can do with the command line, but for now, this is all we’ll need for the rest of the twarc tutorial. 

## Practice with Command Line for Windows

This tutorial uses the Windows program **Command Prompt**, a command line interpreter for Windows. We’re going to do some very quick practice to get comfortable with the command line.

1. Open Command Prompt by searching cmd from your computer’s taskbar or start menu.

    ![Screen shot of Command Prompt program]({{ site.url }}{{ site.baseurl }}/assets/images/cmd-prompt.png "Command prompt application")

    - The shell or command prompt is the line where you type in commands, which are then passed on to the computer’s operating system to run. 
    - Here, the shell prompt includes the drive name (`C:`), location (`\User`) and user account name (`\User`), followed by `>`. Yours should look similar. 
    - After entering a command, you can tell when the process is complete when it returns to the shell prompt. 

2. Create a new folder on your desktop named twarc. Now let’s navigate into this folder. This is the same process as moving through folders in your File Explorer. In this example, the twarc folder has been saved to the desktop for simplicity. Adjust accordingly if you’ve saved it elsewhere. 

3. To navigate into a folder, or directory, use the `chdir` or `cd` command. Type ‘cd’ into the shell prompt, followed by a space, and then the name of the directory you’re moving into. If you are navigating through several directories at once, use a backslash ( `\` ) as seen in the screen shot below. Then press enter: 

    ![Screen shot of Command Prompt cd command]({{ site.url }}{{ site.baseurl }}/assets/images/cmd-prompt-cd.png "change directory command")

4. You’ll notice that your shell prompt will update to include the path of your current location in the filesystem.
    - Capitalization and spacing matters. Navigating onto your desktop requires ‘Desktop’ with a capital ‘D’.
    - You can drag and drop folders into Command Prompt instead of typing out their filepath, just be sure to include a space after `cd`.
    - You can also use the ‘tab’ key to autofill the rest of a directory’s name.

5. If you get lost in your filesystem or want to double check your current location, using the command `chdir` or `cd` alone will print your current directory:

    ![Screen shot of cd command]({{ site.url }}{{ site.baseurl }}/assets/images/cmd-prompt-check-dir.png "check current location")

6. To see the list of files and folders within your current directory, use the command `dir`:

    ![Screen shot of dir command]({{ site.url }}{{ site.baseurl }}/assets/images/cmd-prompt-ls.png "list all files in directory")

7. To navigate back, from the current directory into its parent directory, use the command `cd`, followed by a space and two periods:

    ![Screen shot of parent command]({{ site.url }}{{ site.baseurl }}/assets/images/cmd-prompt-parent.png "return to parent directory")

There is a lot you can do with the command line, but for now, this is all we’ll need for the rest of the tutorial. 
