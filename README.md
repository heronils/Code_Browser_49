# Code Browser 4.9

![Screenshot of Code Browser](Screenshot.png)

[Code Browser](http://tibleiz.net/code-browser/) is a [code folding text editor](http://www.tibleiz.net/code-browser/code-folding.html) written by Marc Kerbiquet. Its nice features include *sections* (sometimes called *folders*, blue in the screenshot), *links* (allowing crosslinking in code files, green in the screenshot) and *descriptions* (pretty looking comments, gray in the screenshot). It loads very fast and is able to load very big files.

Not so nice is that it does not have an autocompleter, refactoring, linting, and other features which full throttle IDE´s like Pycharm provide. Currently i solve it by using [Typing Aid](https://github.com/ManiacDC/TypingAid) for autocompletion and i use other editors for the rest. Code Browsers own scripting language (which i wish was Python) can solve many of those issues.

## Why this repo?

This is a backup of version 4.9. As the current version is 6.6, Marc Kerbiquet removed those older downloads from [his site](http://tibleiz.net/code-browser/download.html) (but [archive.org still has them](https://web.archive.org/web/20160912162221/http://tibleiz.net:80/code-browser/download.html)).

What is so special about version 4.9? It was the last version that supported *relative indentation*. Marc removed this feature after version 4.9, but it is very much needed.

*What is relative indentation? Example: You [fold](http://www.tibleiz.net/code-browser/code-folding.html) a class method in Python to a section. Then you indent the text of the blue section line by one. With relative indentation: The `def` keyword inside of the section will start at column 0. Without relative indentation (the default since version 4.9): This `def` keyword will instead start at column 1 (where it started before you folded it).*

The behaviour since version 4.9 is not pleasant when using languages like [Python](https://www.python.org/), [Nim](https://nim-lang.org/), [Haskell](https://www.haskell.org/), [Coffeescript](https://coffeescript.org/). You can just fold global classes and functions with it, otherwise you will have those indents inside of the sections. But the idea was to have a tree of code sections, not just a list of code sections.

Another problem with versions since 4.9 is that ctrl+shift navigation inside of links now switches to other levels. This is a problem when for example you have lists of links in lists of sections and want to navigate between sections.

## What can this repo do for me?

Here you have the original version 4.9 portables and the source code.

Further, here is my [preferences.cbc](preferences.cbc) which

* defines my own color scheme (see the screenshot),
* defines some tools,
* sets page view as the default view, page navigation is set to fastest speed,
* turns on word wrapping and turns off elastic tabstops (because it does not play together with word wrapping),
* introduces some other changes i made over the years.

You may want to change the keyboard shortcuts according to your flavour.

Further here is my userscript file, which provides extended functionality. I am in the process of making it look more pretty and fix some bugs i found.

The scripts do the following:

* *alt + up/down* – navigate to the previous/next section line or to the start/end of this section.
* *ctrl + alt + up/down* – navigate to the previous/next paragraph or to the start/end of this section (paragraph = lines of code separated by empty lines). Pressing shift will also select the paragraph.
* *ctrl + alt left/right* – if something is selected, move that selection left/right, otherwise fold the paragraph/unfold the section line under the cursor.
* *ctrl + up/down* – move line or selection one line up/down.
* *(shift +) alt + x* – outcomment/unoutcomment the current line or the selection. Works recusively on sections.


## Installation

*Notice, i just tested this on Windows. Let me know if things do not work for you on Linux.*

First choose the portable version fitting your OS and unzip it somewhere.

Then start the executable once, this will create the user config directories (or create them manually). They are located at

* `$(HOME)/.code-browser-4` on Linux and
* `\Documents and Settings\<you>\Application Data\code-browser-4` on Windows.

See *Customizing* -> *Files* in the Code Browser help file for infos how Code Browser loads its configuration files.

### Enabling the color scheme

If you want to use my color scheme, navigate

* *Windows* into to the *config* folder located in the same directory as the executable.
* *Linux* to `/usr/local/share/code-browser-4`.

Replace the original *preferences.cbc* located there with the one located here.

### Enabling the user scripts

If you want to have the extended functionality, navigate to the **user** config directory (see description above), and create/replace the three *user.xxx* files there with the ones in the *User Scripts* folder located here.

## Thats all folks

Written in 2019.09.26 by [heronils](https://github.com/heronils?tab=repositories).
