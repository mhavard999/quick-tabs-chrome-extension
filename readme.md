I forked this because I hate the way it's string matching algorithm, so I'm gonna try to change it to something I prefer.

# INTRODUCTION

Quick Tabs is a tab management browser extension for the Google Chrome web browser based on the "Recent Files" quick selector built into the excellent IntelliJ IDEA by Jetbrains.

Quick Tabs allows you to move quickly between recently used tabs without requiring the use of your mouse, locate and switch to tabs as you need them with minimal keystrokes even when you have large numbers of open tabs.

Visit the [Quick Tabs](https://chrome.google.com/extensions/detail/jnjfeinjfmenlddahdjdmgpbokiacbbb) google extensions page to install this and try it out ...


# FEATURES

* lists all the open tabs in Chrome across all of your open windows
* tabs are listed in most recently used (MRU) order and excludes the current tab (since you're switching tabs)
* quickly search and select tabs by typing letters in the page title or url
* fuzzy search your bookmarks:
  * bookmarks are automatically searched when only a few tabs match your search string
  * add a space at the start or end of your search string to search bookmarks along with tabs
  * add two spaces at the start or end of your search string to search only bookmarks
* fuzzy search your browser history:
  * add three spaces at the start or end of your search string to search browser history
* displays the number of tabs you currently have open in all your Chrome windows
* track recently closed tabs and allow them to be searched and restored
* shortcut key to launch popup window from most tabs, defaults to Ctrl + e, configurable on the keyboard shortcuts page at the bottom of the Chrome Extensions page.
* keyboard navigation of tab list (up and down arrow keys, enter to select)
* tab list shortcut keys:
  * to close selected tab (default ctrl+d)
  * to close ALL displayed tabs in the tab list, honors search filtering (default shift+ctrl+d)
  * select next tab (ctrl+n)
  * select previous tab (ctrl+p)
* popup customization using css


# PERMISSIONS

Quick Tabs requires the following:

* **Read and change your browsing history**: _read only_ access is required to record your open tabs and search browser history.
* **Read and change your bookmarks**: _read only_ access is required to search and display your bookmarks.


# SCREENSHOTS

#### Quick Tabs ready for action.

![Popup Screenshot](screenshots/in_action.png?raw=true)

#### Tab and bookmark search.

![Search Screenshot](screenshots/searching_tabs.png?raw=true)

#### History search.

![Search History](screenshots/searching_history.png?raw=true)

Search your browser history by adding 3 spaces to the start or end of your search query.

#### Decide what to show.

![Search History](screenshots/go_minimal.png?raw=true)

#### Custom CSS styling.

![Search Screenshot](screenshots/custom_css.png?raw=true)

In this case https://userstyles.org/styles/99938/better-styling-for-chrome-extension-quick-tabs by @Bunnyslippers


# SOURCE

The source code for this extension is available on [github](http://github.com/babyman/quick-tabs-chrome-extension), please feel free to inspect it before you install this extension, especially as I am asking permission to interact with your computer and its private data.


# FEEDBACK AND BUGS

Please report all your valuable feedback, feature requests and bug reports on the github [issues page](http://github.com/babyman/quick-tabs-chrome-extension/issues) for this extension.


# RELEASE NOTES

2015.4.30 - fixed issue when rendering bookmarklet code in search results, thanks @benbarth. Added history filter option, allows history search results to be filtered through a regular expression and exclude matches (for example this can be used to exclude past google searches)

2015.4.18 - optimize secondary history searches

2015.4.17 - fixed issue opening urls when they contain search character matches. Added support to fuzzy history search by starting or ending the search string with 3 spaces

2015.4.8 - underline search string hits, add option to include URLs when searching even if they are not being displayed in the tab list

2015.3.31 - added show/hide badge tab count option, removed the css rules that forced the popup window to a specific size (allowing chrome to manage that)

2015.3.12 - added css option placeholder to avoid confusion over expected textarea content

2015.3.8 - popup window timers, separate mouse hover style from keyboard navigation focus to prevent focus jumps when the popup opens under the mouse pointer

2015.3.3 - popup window cleanup, search urls only if displayed

2015.2.28 - library updates, better scrolling, search bookmarks by starting or ending your search string with spaces

2015.2.26 - performance improvements, fuzzy searching and tighter UI

2015.2.25 - added support for bookmarks search ( **IMPORTANT adding bookmark search required adding bookmark permissions, READ ONLY access only** ) and UI style updates, huge thanks to @oarrabi for this

2015.1.2 - delay script execution till window.onload fires (closes #70), thanks @aakash-shah

2014.12.27 - re-enable mouseover events (close #69), thanks @KayNoSpam

2014.12.23 - quick fixes for the two reoccurring errors, thanks @heavyk.  Moved the template rendering code into a sandbox as per https://developer.chrome.com/extensions/sandboxingEval

2014.9.27 - support custom css through the extensions option page, this supports custom styling of the popup window (for example https://userstyles.org/styles/99938/better-styling-for-chrome-extension-quick-tabs by @Bunnyslippers)

2014.9.13 - permissions fix, thanks @jtanner

2014.7.8 - More stability improvements

2014.7.6.1 - NPE bug fix

2014.7.6 - bug fixes and allow cycling through with TAB and SHIFT+TAB (close #28), allow PageUp/PageDown navigation (close #53), thanks @eush77

2014.7.1 - merged fix to html encoding bug, thanks @eush77

2014.5.6 - add vim style next/prev keys to popup, thanks @roblund

2014.4.4 - performance improvements, thanks @philippotto for the work and inspiration (and @olado for doT.js)

2014.1.14 - fixed shortcut keys issue

2014.1.12 - merged design improvements, thanks @rodrigok

2013.11.2 - merged shortcut key update, thanks @Mononofu, based on this update I have rewritten the shortcut code and stripped all the content-script stuff out, no more tab reload warnings or window placement issues and the extension works on chrome:// pages

2013.8.4 - merged fix for issue #35, thanks @kho

2013.6.24 - merged fix for issue #8, thanks @yaauie

2013.5.1 - fix for bug #44, Showing nonexistent "New Tabs" open with incorrect total

2013.1.23 - bug fixes, removed console logging

2012.12.9 - bug fixes, pressing the popup load shortcut once the popup has loaded now selects the next tag in the list

2012.12.8 - bug fixes and performance improvements

2012.12.7 - bug fixes and code updates

2012.12.4 - applied patches from @konk303 (line hight, ctrl+n/ctrl+p tab select keyboard shortcuts), @ignacysokolowski (search delay option and integer parse bug) and @slay2k (huge code update, updated to manifest version 2, library version updates and improved search matching)

2011.2.18 - applied patches from @yaauie, option to set search provider, open popup in the middle of current window, compatible with multiple monitors

2010.6.27 - applied crtl+D tab close tab focus enhancement patch from @osheroff

2010.5.8 - updated since chrome bug fix to allow tab focus switching between windows in 5.0.375.29 - big thanks to @clayhinson.  If a tab search returns no results and you press enter a new tab will be opened and if the search is a url it is loaded in the tab otherwise a google search is performed.

2010.3.2 - fixed a bug that cause the popup to close in dev version 5.0.336.0 (39716)  - thanks @ds :D

2010.2.21 - added more display options and improved scrollbar - thanks @Randy

2010.1.31 - better list scrolling and fixed some minor bugs

2010.1.30 - fixed display when urls are hidden, also resolved shortcut key issues created in the last release

2010.1.17 - changed default popup keys to ctrl+m due to windows issues, added button to close selected tab

2010.1.9 - css fixes for popup  window, option to hide URL's

0.9.10 - exclude devtools by default, ctrl+d and ctrl+shift+d shortcuts added

0.9.9 - added options page, recently closed tab tracking, shortcut key configuration and fixed search list highlighting bug

0.9.8 - removed tab auto-reload on install, now alert users when tab reload is required

0.9.7 - bug fixes

0.9.6 - reduced popup size when few tabs are open

0.9.5 - fixed missing scrollbars on Linux


# ACKNOWLEDGEMENTS

Inspired by
http://www.jetbrains.com/idea/

Icon image based on photo by Ged Carroll found at
http://www.flickr.com/photos/renaissancechambara/3380657988/

Blank Icon by Deleket (Jo)
http://deleket.deviantart.com/


# LICENSE

Copyright (c) 2009 - 2015, Evan Jehu
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the author nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL EVAN JEHU BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
