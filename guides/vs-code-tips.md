---
description: Editor features that make working with datablocks easier
---

# VS Code Tips

## Saving files

This may seem very basic but it can come up more often than expected. There's 2 quick ways to save files and you should save often.

* `Ctrl + s`  - save the current file
* `Ctrl + k, s` - save all opened files (press ctrl and k together, release both, and press s)

## Opening folders from context menu

This is a neat function to have, it allows you to easily open any folder from file explorer with VS Code. You can enable this when installing. If you didn't, you can reinstall VS Code without deleting it and select the option (or you can go mess with registry files but I wouldn't recommend it).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Open with code in context menu</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Open with code checkboxes during installation</p></figcaption></figure>

## Syntax errors

If VS Code detects an error in your file, it'll mark that file red.

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption><p>File with syntax errors</p></figcaption></figure>

It might not be obvious what causes this or what the exact error is, so you can open the problems view to see it by pressing `ctrl + shift + m`:

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption><p>Problems view</p></figcaption></figure>

From here, you can click on the problem and you'll be taken straight to it. And if you're lucky, the error message will accurately explain the problem.

## Split editor

This allows you to see several files at once. To use it, simply drag a file in the top view to the side of the screen.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>Split editor view with 2 files open</p></figcaption></figure>

## Collapse blocks

You can collapse blocks by clicking the arrow next to them at the left side of the screen. This can be useful to hide unnecessary information or quickly select entire blocks.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption><p>A rundown block collapsed</p></figcaption></figure>

## Navigating files

### Go to start/end of block

Useful when navigating big lists, such as levels in a tier. Pressing `ctrl + shift + \` anywhere inside a block will take you to the end of it, and pressing it again while at the end of a block will take you back to the start.

### Breadcrumbs

Breadcrumbs tell you where you are inside a file in terms of blocks:

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption><p>Breadcrumbs showing the cursor is in CustomGeomorphs</p></figcaption></figure>

You can click the breadcrumbs to navigate and even find out what block you're in.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Breadcrumbs showing that the cursor is in CustomGeomorphs in<br>Complex_Tech block</p></figcaption></figure>

### Go to line

Sometimes it's possible that you know the line you need but scrolling would take some effort. To quickly go to the line you want, press `ctrl + g`. This will open an input field at the top of the screen. Input the line number you need and press enter.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>Line number menu</p></figcaption></figure>

### Go to file

When working with datablocks, it's common to open and close a lot of files. The explorer view at the left side of the screen is a good way to see all the files but it can take a bit of effort to get the one you want. A better way is to use the top menu to go to the file you want, similarly to going between lines. Open the menu with `ctrl + p` and start typing the name of the file you want, then press enter to open the file. This works for any file in the folder you have open and its subfolders.

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption><p>Top menu with enemybalancing file selected</p></figcaption></figure>

## Search

This one might seem obvious but there can be features you're not aware of.

### Searching in selection

The basic shortcut for search is `ctrl + f` but afterwards you can press `alt + l` or manually click the icon to limit the search to selected text.

For example, if i want to search for tier D in rundowndatablock, i get this:

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption><p>tierd with 7 matches</p></figcaption></figure>

But if i want to find tier d in a specific rundown, i could use breadcrumbs to get to the start/end of the block, collapse it, select it and then find in selection instead, showing 2 matches:

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption><p>tierd with find in selection</p></figcaption></figure>

This may seem trivial but imagine you're trying to find a specific chained puzzle use in a certain level and have to go through hundreds of matches instead. Then it ends up saving tons of time.

### Searching across files

Available either with `ctrl + shift + f` or with 2nd menu at the left side of the screen, this function allows search/replace to work across all files in the opened folder. You can also search in a subset of files.

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption><p>Searching for "hunter" in the enums folder</p></figcaption></figure>

### RegEx search

RegEx is a powerful search & replace tool, not limited to VS Code, and is quite a complex topic. For now let's just say that it allows you to find text based on patterns.

Let's say I want to find enemy with persistent id 13, but I'm lazy to enter the whole text in the search. Using RegEx, i can search for pattern `pers.+13` and find what I want.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>RegEx search pers.+13</p></figcaption></figure>

Here "pers" and "13" are taken as literal text to search for, but ".+" is a pattern saying "match any character at least once" (except line breaks), and this ends up matching the rest of the missing text in-between "pers" and "13".

I recommend you check out guides to RegEx and test online for mistakes and explanations, for example in [regex101](https://regex101.com/).

### RegEx replace

RegEx (as well as search without regex) can be used not only to find, but to replace text, performing massive amounts of editing in no time at all.

Let's say we want to take ALL the enemy groups in base game and rename them to mark as such.

* The search pattern is `"name": "(.+)"`. All of these characters are matched literally, except for "`(.+)`". The ".+" pattern is the same as before, but "()" marks a capturing group. That means we're going to reuse it later.
* The replace pattern is `"name": "OBSOLETE_$1"`. Here almost everything is literal, except for $1. That means the first capturing group should be inserted here.

The result:

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>RegEx search &#x26; replace for all names</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption><p>Group names with OBSOLETE_ prefix added</p></figcaption></figure>

Depending on creativity and circumstances, this can be used to great effect. In fact, RegEx was used to generate a big part of this wiki.

## Creating temporary files

A simple but neat feature, this allows you to create a new file simply by double-clicking next to the list of existing files. You can use this to store a block for editing temporarily, back up certain information, mark notes and so on. VS Code will keep the file even if you close and reopen the app.

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption><p>New file created by double-clicking</p></figcaption></figure>

## Comments

Comments are created purely to give additional context/information for the reader. JSON technically does not have comments, but there are workarounds for this.

One way is to make a new JSON field. The game ignores whatever fields it doesn't know, so it won't break anything.&#x20;

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption><p>Comment field in<br>enemy population</p></figcaption></figure>

But this can get annoying, and there is a way to use comments normally with `//`. If you do it in a plain JSON file, VS Code will likely complain about it.

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption><p>big striker comment</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>VS Code saying comments are not allowed in JSON</p></figcaption></figure>

But the game ignores comments so it can be left as-is. However, the red text triggers our OCD and we want it gone. Well, there is a way. JSONC (json with comments) exists, and while mods do not usually use it, we can configure VS Code to take any JSON file as JSONC.

To do this, open the command menu with `ctrl + shift + p` and start typing "language". "Change language mode" should pop up. Select it, then select "Configure file association", then type in "jsonc" and press enter.

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>Change language mode<br>in command menu</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption><p>Configure file association option</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Json with comments selection</p></figcaption></figure>

Now VS Code will assume JSONC for all JSON files and you won't see it complaining about comments.

## Git

Git is a powerful versioning tool not limited to VS Code. It is covered in its own guide [here](the-newbie-git-guide.md).

