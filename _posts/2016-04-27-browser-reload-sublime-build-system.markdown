---
layout: post
title:  "Sublime Text Build System for Browser Reload (Mac)"
date:   2016-04-27 12:45:12
tags: fast, development, sublime, text, build, system, browser, reload, web, chrome, mac
---
When you're working on a website, browser reload on file changes isn't always the best option, especially with complex one-page applications. So if you like the be in control, just use this [Sublime Text][sublime_text] build system to trigger a reload of the currently active browser tab (Cmd+B on Mac).

* Open [Sublime Text][sublime_text] and go to Tools --> Build System --> New Build System...
* Copy & paste the below code
```json
{
	"cmd": ["osascript -e 'tell application \"Google Chrome\" to tell the active tab of its first window to reload'"],
	"working_dir": "$folder",
	"shell": true
}
```
* Save this file to your [Sublime Text][sublime_text] user folder. I named it `TiShadow.sublime-build`.
* Now open up your web project folder in [Sublime Text][sublime_text]
* Select your newly created build system (Tools --> Build System --> YOUR_BUILD_SYSTEM_NAME)
* Hit Cmd+B to run trigger a reload.

If you don't use Google Chrome, you can just replace the browser name in the build script.

[sublime_text]: http://www.sublimetext.com/
