---
description: >-
  I just changed something and now the level's not working AND I CAN'T FIX IT
  FOR 2 HOURS AAAAAHHHHHHHHHHH
---

# The Newbie Git Guide

## Overview

{% hint style="info" %}
This guide only introduces the very fundamentals of Git in a simplified fashion.
{% endhint %}

{% hint style="info" %}
This guide assumes you're using VS Code but Git is fully usable without it.
{% endhint %}

Git is a version control system. That basically means you get to see all the changes you (or someone else if you're collaborating) have made to files in a repository. Git is commonly used for storing files online and even publicly for anyone to see, such as [GTFO-API](https://github.com/Kasuromi/GTFO-API) on GitHub, but it's fully functional for offline use as well. For now, we're only covering offline use.

In VS Code, the main view for Git is the source control view, seen at the top left side of the window:

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption><p>Source Control view icon</p></figcaption></figure>

The changes are shown on the files themselves:

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Git changes in VS Code explorer: U (Untracked - new) file<br>and M (Modified) file</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p>Git changes in VS Code source control view - <br>also showing a D (deleted) file</p></figcaption></figure>

...and their contents, marked as red for deletions and green for additions:

<figure><img src="../.gitbook/assets/image (23) (1).png" alt=""><figcaption><p>Modified line in ArchetypeDataBlock.json, showing "Bullpup" -> "Bullpups" change<br>(opened through source control view)</p></figcaption></figure>

How useful this is depends on how you use it, for example:

* You can easily return to a version of your content that you know for sure is working.
* You can undo one little change at a time to see where exactly things went wrong.
* You can keep it as a form of documentation for the changes made over time or the changes required for certain things to work.

Using Git is completely optional but (speaking from experience) it can save hours wasted debugging and even dropped/restarted levels (for rundown developers) when no fix for problems is found.

## Installation

If you haven't installed git yet, the source control view will show something like this:

<figure><img src="../.gitbook/assets/image (26) (1).png" alt=""><figcaption><p>Source control view showing git is not installed</p></figcaption></figure>

Download and launch git installer from there. Most users should use 64-bit standalone installer.

When going through the installation, most default options should be fine. Just one change you might want to make:\


<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Git install - use VS Code as default editor</p></figcaption></figure>

Either way, for basic git use none of these options should matter much.

Now that git is installed, reload VS Code and open the folder you want to start working with, such as a fresh MTFO dump (moved to a folder where mod managers won't mess with it), or your own rundown if you have one. The guide will use [OriginalDataBlocks](https://github.com/UntiIted/OriginalDataBlocks).

First step when working with a project offline is to initialize the repository. If you open the source control view now, you should see something like this:&#x20;

<figure><img src="../.gitbook/assets/image (20) (1).png" alt=""><figcaption><p>Source control view on a folder without git</p></figcaption></figure>

We're almost ready to start using git, but first there's 2 commands to run. We have to set a user name and email for commits author tracking. For offline repositories this shouldn't matter much and can be changed later, but remember that you can't change author information on existing commits. To run the commands, open a new terminal in VS Code:

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption><p>VS Code new terminal button</p></figcaption></figure>

In the terminal, input the commands with your own values:

`git config --global user.name "somename"`

`git config --global user.email "somename@gmail.com"`

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>git config commands settings name and email</p></figcaption></figure>

Now you're ready to start using Git.

### GitLens extension

VS Code has extensions that bring additional functionality to the editor. GitLens is one such extension for Git:

<figure><img src="../.gitbook/assets/image (19) (1).png" alt=""><figcaption><p>GitLens extension in VS Code</p></figcaption></figure>

It will not be covered here, but if you see some functionality in the guide that you don't see in your own VS Code, it likely comes from this extension.

## Basic Git use in VS Code

Now that we're ready, let's initialize the repository. Once it's done, the source control view should list all your files as new since we haven't started tracking them yet:

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption><p>Source control view after initializing repository</p></figcaption></figure>

Let's stage and commit all of them as the initial commit:

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption><p>Initial commit</p></figcaption></figure>

1. Press the + icon to stage all the changes (make sure you press it to the right of the "Changes" text instead of a specific file) - you're selecting the files to include in the commit
2. Write the commit message - "initial commit"
3. Press the commit button to finalize the commit.

Now the source control window should only show the "Publish Branch" button. This is an offline project so we're not going to do that.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>Source control view with no changes</p></figcaption></figure>

There may have been a lot of unfamiliar terms used just now. The git glossary is [here](https://git-scm.com/docs/gitglossary) (google is also an option), but let's look at some fundamentals:

* Stage (verb) - to stage a change is to prepare it for a commit, i.e. include in the commit. Git allows you to select just the changes you want instead of everything that's been edited (including selecting only specific parts of files).
* Commit - a snapshot of the hierarchy and the contents of the files in a Git repository; a single point in the Git history. A commit is like a specific version of your project.
* Commit message - a description of the changes made in a specific commit.
* Branch, "master" branch - a "branch" is a line of development. Essentially, it allows you to isolate your changes and commits from others based on people working on them or their purpose. Branching is a more advanced topic that you likely won't run into when working alone. The master branch is the default, the main branch in a project.

### Practical use

So now we kind of know how to work with Git and it does track the changes in our project correctly, but how do we make use of it? For starters, when do we commit? And what commit messages do we use?

That's completely up to you. If you are developing a rundown on thunderstore, one thunderstore version can be one commit, with commits like "V 1.0.1", "added C1" etc. You can make it more detailed, for example "adjusted ammo balancing for C1", "added shadow baby charger", "added hel hammer launcher". There's probably just 2 things I could mention:

* Generally, smaller commits are better than large commits - keep them more focused, easier to define and less progress lost when reverting;
* Make sure your changes work before you commit. A commit with a broken project version is the last thing you want.

Now let's say that we did indeed break something (but didn't commit) and want to use Git to help fix it. The first straightforward way is to see the specific changes you made and change them back. We don't want to revert the entire commit or entire files, just some one line that's probably broken. We have 2 easy ways to do that.

For the first, go to source control view and select a file with changes, then find some specific change:

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>ArchetypeDataBlock with changes</p></figcaption></figure>

Click the arrow in the middle to revert the change:

<figure><img src="../.gitbook/assets/image (13) (1).png" alt=""><figcaption><p>Arrow showing revert</p></figcaption></figure>

The change should be reverted, just remember to save the file.

{% hint style="warning" %}
You can't always easily undo reverted changes.
{% endhint %}

For the second method, go directly to the changed file and line. You should see a blue line near line numbers:

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>Blue line to the right of line numbers</p></figcaption></figure>

Click it. You should now see the changes inline. At the top right there should be a revert icon:

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption><p>Inline change with revert icon</p></figcaption></figure>

Click it to revert the change.

In 2 other common cases where you want to revert a whole file or all the changes since the last commit, it's easily done through source control view. All you need to do is click the revert icon on a file or next to changes:

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Discard changes icon in source control view</p></figcaption></figure>

Reverting that specific change would restore the deleted file.

Now if you break your project and don't remember what was different when it worked, you can simply look and see. Hopefully this prevents some painful debugging for you.

Git keeps the entire history of the project since the repository was initialized, so you could go back to a version of your project from years back if you wanted to. You can also look into storing a project privately or publicly online as well and even working with other people.
