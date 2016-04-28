---
layout: post
title:  "TiShadow Build System for Sublime Text"
date:   2015-10-15 12:45:12
tags: appcelerator, titanium, tishadow, android, ios, fast, development, sublime, text, build, system
---
Already got into [TiShadow][tishadow]?  
If not read my post about [Rapid App Development with TiShadow and TiNy CLI]({% post_url 2015-10-15-app-development-with-tishadow %}).  

Here is a [Sublime Text][sublime_text] build system, that lets you trigger your app updates with a keyboard shortcut (Cmd+B on Mac):

* Open [Sublime Text][sublime_text] and go to Tools --> Build System --> New Build System...
* Copy & paste the below code

```json
{
  "cmd": ["tishadow run --update"],
  "working_dir": "$folder",
  "shell": true,
  "variants": [
    {
      "name": "first run",
      "cmd": "tishadow run"
    }
  ]
}
```

* Save this file to your [Sublime Text][sublime_text] user folder. I named it `TiShadow.sublime-build`.
* Now open up an Appcelerator mobile app project folder in [Sublime Text][sublime_text]
* Select your newly created build system (Tools --> Build System --> YOUR_BUILD_SYSTEM_NAME)
* Hit Cmd+B to run the [TiShadow][tishadow] update. (You can also open the Command Palette and enter "first run" to trigger an initial update)

[sublime_text]: http://www.sublimetext.com/
[tishadow]: http://tishadow.yydigital.com/
