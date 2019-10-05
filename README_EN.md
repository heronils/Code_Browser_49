# Code Browser 4.9

[Introduction](#introduction) • [Why this repo](#why-this-repo) • [Installation](#installation) • [Shortcuts](#shortcuts) • [Tips and Tricks](#tips-and-tricks ) • [Directives](#directives) • [Credits](#credits)

![Screenshot of Code Browser](Screenshots/Hello_World.png)

*Screenshot of Code Browser*

## Introduction

[Code Browser](http://tibleiz.net/code-browser/) is a Zen-style text editor written by [Marc Kerbiquet](http://tibleiz.net/). It loads quickly and also displays large files without grumbling. It has its own scripting language, with which one can extend the functionality of the editor.

But its revolutionary feature is how it interprets and displays special [directives](#directives) in source code:

* *Sections*. Blue in the screenshot. They fold away freely chosen parts of the code. You can navigate in and out of such sections using `Alt` + (`→` or `←`) just as you can navigate in and out of folders in file browsers. Which is why sections were originally called *folders* by Marc Kerbiquet.

  Sections can be nested arbitrarily deep. Thus, one can convert a linear code file into a tree of 'mini-files', which is very supportive to code structuring. However, it actually remains a single file.
* *Links*. Green in the screenshot. They extend the concept, and make it possible to insert links to other sections or to other files, similar to [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink) in HTML documents. In practice, links are often used in index files or docs, less often in the code itself. They offer other interesting possibilities because of their ability to link to line numbers or even search results of regular expressions.
* *Descriptions*. The text with gray background in the screenshot. They are 'visual sugar'. They are nice-to-look-at, optionally color-highlighted comments. The comment characters are hidden.

More information can be found in the help file or [on the project page](http://www.tibleiz.net/code-browser/code-folding.html).

## Why this repo?

Unfortunately, after version 4.9, the author removed an important feature - relative indentation (see *Folding* → *Relative Indentation* in the help file) - which renders the editor rather useless for indentation-based languages like [Python](https://www.python.org/ ) or [Nim](https://nim-lang.org/). Furthermore, the sibling navigation has been changed - `Ctrl` + `Shift` + (`↑` or `↓`) - which now changes the level when navigating across section borders.

Since I need these features in [Treesearcher](https://github.com/heronils/Treesearcher), here is a backup of version 4.9, as well as my global settings and my user scripts.

## Installation

1. Download the portable which fits your operating system from the `Setup` folder located here and [unpack it](https://www.7-zip.org/). The editor is the `cb.exe` under Windows and the `code-browser` in the folder `usr/local/bin` under Linux.

The following steps are optional.

2. Read the section *Customizing* → *Files* in the contained help file.

3. Start the editor once. This creates the user directories described under 2.

4. *Change global settings*: Replace the global `preferences.cbc` with the one in this directory.

   The main differences are: Relative indentation is set as default, a (in my opinion) prettier to look at theme is used (See *Themes* → *Bob* in `preferences.cbc`), some shortcuts are redefined (see *Key Mappings* → *Bob*), and some languages ​​are changed (see *Languages​​*). Among other things, Python is defined as a tool (`Alt` + `p`, see *Tools*).

   The `preferences.cbc` can be changed at will, **but will - [if you have used the installer](https://web.archive.org/web/20160912162221/http://tibleiz.net:80/code-browser/download.html) - be overwritten during a reinstall**.

5. *Enable user scripts*: Move the `user.cbs` and the `user.cbc` here in the directory into the user directory created in step 3. The `user.cbs` are the scripts, and the `user.cbc` connects the scripts to the editor.

   *Note that the layout of `user.cbc` is destroyed when you make changes within Code Browser via 'Tools' → 'Options ...'. If necessary, make a backup of this file.*

   The user scripts provide additional functionality such as folding and unfolding sections and commenting out parts of the code. It is not pretty looking code right now – I wrote the scripts a long time ago – but they work. A revision is in planning.

## Shortcuts

[If my user scripts and my user settings are installed](#installation), the Code Browser uses the following shortcuts. The abbreviations can be changed under `preferences.cbc` → *Key Mappings* → *(activated Key Mapping)*. Those with the text `(user script)` behind them are defined by my user scripts and can be changed in the `user.cbc`.

### Basic
* `Ctrl` + `z` and `Ctrl` + `y` – Undo and Redo
* `Ctrl` + `Shift` + `s` – Save all files, including those not visible (for example, those that you have changed and from which you then have navigated away via link).
* `Esc` – Close any dialog below the editor or, if no dialog is open, close the current tab.
* `Alt` + `f4` – Exit Code Browser. If files are unsaved, Code Browser will ask what should be done.
* ... and more, which you can inspect in the main menu.

### view modes

* `F4` to `F7` – Switch between the four different view modes of Code Browser.

  *Because of a bug in Code Browser, you can not navigate back to a previous document via link when you change the view mode in between. In that case you have to reopen the previous document by hand.*

### Navigation

* `Alt` + (`↑` or `↓`) – Jump to the previous or the next section/Link.
* `Alt` + (`→` or `←`) – Move into or out of a section/link.
* `Ctrl` + `Shift` + (`↑` or `↓`) – Jump to the previous or next sibling section in the parent layer – Shortcut for `Alt` + `←`, `Alt` + (`↑` or `↓`), `Alt` + `→`.
* `Ctrl` + `Alt` + (`↑` or `↓`) *(user script)* – Jump to the previous or next paragraph (Paragraph = lines separated by blank lines). Additionally `Shift` also selects the paragraph.
* `Alt` + `g` – Jump to the line number to be entered.
* `Ctrl` + `b` – Jump to the corresponding bracket. Additionally `Shift` selects the text in between.

### Sections

* `F12` – Create a new section. If text is selected, it will become the content of the section.
* `Shift` + `F12` – Delete the section under the cursor. Its content is not deleted but moved to the parent level.
* `Alt` + `Enter` – Edit the properties of the section or the link under the cursor.
* `Ctrl` + `Alt` + (`←` or `→`) *(user script)* – If something is selected, move the selection one character left or right, otherwise fold the paragraph under the cursor or unfold the section under the cursor.

  *Without the closing marker of an unfolded section – e.g. `#)` in Python or `/*)*/` in CSS – you can not fold the section again.*

### Links

* `Ctrl` + `Alt` + `c` – Copy a link to the current section to the clipboard. Can then be inserted elsewhere with `Ctrl` + `v` – also into other files.

  For this to work, the section and all parent sections must have an ID (ID = a freely choosable text). It can either be added by hand for a section (or a link) pressing `Alt` + `Enter` when the cursor is on the section or link line, or simply unfold the section once with `Ctrl` + `Alt` + `→` and then fold it again with `Ctrl` + `Alt` + `←`. This equates the ID with the title of the section.

There is no shortcut defined to create a link by hand, because I think that's a cumbersome procedure anyway.

### Descriptions

* `F11` or `F10` – Convert the selected text to a description or back to normal text.

### Moving text

* `Ctrl` + (`↑` or `↓`) *(user script)* – Move the current line or selection one line up or down. The selection does not have to be a cleanly selected block, it simply moves all lines in which something is selected. `Ctrl` + `Alt` + (`←` or `→`) moves the selection to the left or right.

### Outcommenting and unoutcommenting lines

* (`Shift` +) `Alt` + `x` *(user script)* – Outcomment or unoutcomment the current line or selection. Uses `<comment sign of the language>~<space>` as a directive, for example, `#~` in Python. Works recursively on sections.

  *Outcommenting multiple times is currently not working properly with languages like CSS that do not have single-line comments.*

### Bookmarks

* `Ctrl` + `F2` – Set a bookmark.
* (`Shift` +) `F2` – Jump to the next or previous bookmark. Bookmark navigation works only within a single file and bookmarks are not persistent between sessions.
* (`Shift` +) `Ctrl` + `m` – Highlight all occurrences of the currently selected text in the current document or remove all highlightings.

### Search and replace

* `Ctrl` + `r` – Open the *Find and replace* dialog.
* `Alt` + `r` – If the *Find and Replace* dialog has the focus, select the first search result, or replace it and select the next search result. Unfortunately, this keyboard shortcut can not be changed.
* (`Shift` +) `F3` – Find the next or the previous search result, do not replace the current one.

## Tips and tricks

* The theme used by my `preferences.cbc` tries to use the following fonts in this order: *[Consolas](https://www.google.com/search?q=Download+Consolas+font)*, *[Lucida Sans Typewriter](https://www.google.com/search?q=Download+Lucida+Sans+Typewriter+font)*, *[Courier New](https://www.google.com/search?q=Download+Courier+New+font)*, *Monospace*. You can change these fonts under *Themes* → *Bob* → *Font*.
* At the moment I use tabs for indentation – if that does not fit, set the variable `expand-tabulation` to `true` in `preferences.cbc` under *Languages* → *default* → *Indents and word wrapping*. Here you can also set the width of a tab or the number of spaces that will be entered when pressing `Tab`, with the variable `tabulation-size`.
* All defined languages – except for the root language `default`, whose name can not be changed – inherit variables from a parent language via `prototype = languages.<parent language>`. You can change these variables in a specific language by simply copying them there.

  `<Name of variable> =` sets the variable to null, it does not inherit from the parent variable either.
* You can not use underscores – `_` – within `*.cbc` files, but the separator sign – `-`.
* Code Browser can not do code completion. The Autohotkey-based [Typing Aid](https://github.com/ManiacDC/TypingAid) can help.

## Directives

Here is a reference of the meta characters and -character groups that are meaningful for Code Browser and my user scripts. That's how they would look in another editor. Those that are relevant for Code Browser are highlighted in yellow. Those that are relevant for my user scripts are highlighted in orange.

<pre>
<span style = 'background:yellow'>#[of]</span>ID of the section<span style = 'background:yellow'>:</span>Title of the section
Content of the section
<span style = 'background:yellow'>#[cf]</span>

<span style = 'background:yellow'>#[l]:</span>Title of the link<span style = 'background:yellow'>:#</span>ID of the section

<span style = 'background:yellow'>#[c]</span>Descriptive comment

<span style = 'background:orange'>#( </span>Title of the unfolded section
Content of the section
<span style = 'background:orange'>#)</span>

<span style = 'background:orange'>#~ </span>Outcommented text
<span style = 'background:orange'>#~ #~ </span>Outcommented twice

# Normal comment


Normal text
</pre>

The directives start with the language-specific metacharacter for [Comments](https://en.wikipedia.org/wiki/Comment_(computer_programming)). In this example, it is the hash sign – `#` – used by Code Browser by default for unknown file types, text, [Python](https://www.python.org/) and [Nim](https://nim-lang.org/). For javascript it is `//`, for CSS, which has no single-line comments, `/*` at the start of the line and `*/` at the end.

Comment characters can be defined in `preferences.cbc` under *Languages* → *(Language)* with the variable `line-comment`. Or with `open-comment` and `close-comment` if the language does not have single-line comments. If all three are defined, `line-comment` is preferred.

Directives are each in a separate line.

Meaning of the individual directives:

* `#[of]` and `#[cf]` opens and closes a section (originally called *Folder*). The colon – `:` – separates the ID of the section (that to which links point) from the title of the section.
* `#[l]:` denotes a link. The second colon separates the title of the link from the target of the link.

  The syntax for link destinations is about the same as [URLs](https://en.wikipedia.org/wiki/URL).

  If the destination is an absolute file path, it must start with `file:///`. Relative link goals are also possible.

  If the target is a section, append a hash sign – `#` – followed by the path to the section, to the file path. So `file:///<file path>#<path to the section within the file>`. If the section is in the same file, you can omit the file path, as in the example above.

  You can also link to line numbers by appending `?aln=<number>` (*absolute line number *).

  And more, see section *Links* in the help file.

  The easiest way to create links is to use `Ctrl` + `Alt` + `c` – [See Keyboard Shortcuts → Links](#links).
* `#[c]` denotes a description line.
* `#(<Space>` and `#)` opens and closes an unfolded section.
* `#~<Space>` denotes an outcommented line. `~<Space>` denotes an outcommented section.
* `#<Space>` denotes a normal comment that has no special meaning for Code Browser or for my user scripts.

This file would look like this in Code Browser:

![Different types of comments and how they look in Code Bowser](Screenshots/Comment_Types.png)

*Different types of comments and how they look in Code Bowser*

## Credits

Many thanks to Marc Kerbiquet for [Code Browser](http://tibleiz.net/code-browser/) and [for other languages, tools, and games he wrote](http://tibleiz.net/).

This text was translated from german with the help of [Google Translate](https://translate.google.com/). If you find errors here, please open an [issue](https://github.com/heronils/Code_Browser_49/issues) or make a [pull request](https://help.github.com/en/articles/creating-a-pull-request).

Posted 2019-09-26 by [heronils](https://github.com/heronils?tab=repositories). Last update: 2019-10-05.
