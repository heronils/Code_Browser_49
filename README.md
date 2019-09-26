# Code Browser 4.9 Backup

This is a Backup of *Code Browser* 4.9, written by Marc Kerbiquet

![Screenshot of Code Browser](Screenshot.png)

[Code Browser´s website is here](http://tibleiz.net/code-browser/), the current (2019.09) version is 6.6.

### Why

After version 4.9 Marc Kerbiquet rewrote the editor and in this process he abandoned support for *relative indentation* - [sections](http://www.tibleiz.net/code-browser/code-folding.html) which can be indented and the indent of the contained code will reflect it.

The removal renders the editor not so usable for indentation-based languages like Python, Nim, Haskell and others.

Further, after a while Marc also removed the code, the installer, and the portable versions for this version from [his website](http://tibleiz.net/code-browser/) (however, [archive.org still has it](https://web.archive.org/web/20160912162221/http://tibleiz.net:80/code-browser/download.html)).

### What

Therefore i uploaded this version 4.9 – which is the last version which supports relative indentation – here, as an extra backup, should the [archive.org](https://web.archive.org/web/20160912162221/http://tibleiz.net:80/code-browser/download.html) link disappear one day.

Included is also my [preferences.cbc](preferences.cbc) which defines some handy tools and has my own syntax scheme enabled, see the screenshot.

Further included is my userscript which provides some extended functionality. It works, but the code is not nice to look at. Im currently in the process of rewriting it.

If you want to have autocompletion in Code Browser, i suggest to have a look at [Typing Aid](https://github.com/ManiacDC/TypingAid). It is Windows only. [Here is the Discussion Thread in the Autohotkey Forum](https://autohotkey.com/board/topic/49517-ahk-11typingaid-v2220-word-autocompletion-utility/).

### Basic installation

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

I also made some other changes in that file, to the languages, i added some tools, page view is the default, and some other options are also different. The file has changed a bit over time.

### Enabling the user scripts

If you want to have the extended user script functionality, navigate to the **user** config directory (see description above), and create/replace the three *user.xxx* files there with the ones in the *User Scripts* folder located here. The scripts do the following:

* *alt + up/down* – Navigate to the previous/next section line or to the start/end of this section.
* *ctrl + alt + up/down* – Navigate to the previous/next paragraph or to the start/end of this section (paragraph = lines of code separated by empty lines). Pressing shift will also select the paragraph.
* *ctrl + alt left/right* – if something is selected, move that selection left/right, otherwise fold the paragraph/unfold the section line under the cursor.
* *ctrl + up/down* – move line or selection one line up/down.
* *(shift +) alt + x* – outcomment/unoutcomment the current line or the selection. Works recusively on sections.

### Thats all folks

Written in 2019.09.26 by Nils-Hero Lindemann, <nilsherolindemann@gmail.com>.

Have fun with Code Browser :-)
