---
layout: post
title:  "Rapid App Development with TiShadow and TiNy CLI"
date:   2015-10-15 12:45:12
tags: appcelerator, titanium, tishadow, node, npm, appc, android, ios, fast, development, tiny
---
### Synopsis
Looking for a fast way to develop mobile apps with [Appcelerator's Titanium Framework][titanium], I came across two CLI tools which give you live reload on any number of Android and iOS devices and simulators by using a few short commands. There are two ways to get there, but first we need to get those tools installed.

### Tools
[TiNy CLI][tiny] by Fokke Zandbergen saves you keystrokes when using the titanium CLI.  
(Ad-hoc IPA Build: `tn ah` --> `ti build --platform ios --target dist-adhoc`)  
Install with `npm install -g tn`  

[TiShadow][tishadow] by David Bankier is a complete toolset for rapid app development and testing.  
It consists of a Server and an App-Wrapper. You wrap your app with [TiShadow][tishadow] and install and launch it on your test devices and/or simulators. Then you start up the server, which will send changed files zipped to the App via Websockets. This process takes seconds and can be triggered by file save or command.
Install with `npm install -g tishadow`  

### Generate TiNy Recipes
Let TiNy generate shortcuts ("recipes") for all your simulators and connected devices:  
`tn generate`  
You can list these later on with:  
`tn list`

### Develop on a single Device / Simulator
Just run `tn ipad-2 --shadow` from your app project's root folder to launch the iPad 2 Simulator with live reload enabled. The app will be updated on every file save. You can replace "ipad-2" with any name from `tn list`.

### Develop on multiple Devices / Simulators
Here comes the real Magic. Want to see changes on all connected Devices and running Simulators? Here's how:  

* Create a shadow (appified) version of your app by running the needed commands from your project's root:

```bash
For iOS:		tn ah --appify
For Android:		tn playstore --appify
For a specific device:	tn DEVICE_NAME_FROM_TINY --appify
```

* If you did not use the specific device install, copy and install the app to your device
* Start up the server with `tishadow server` (logs will be printed here)
* Initially push your code to all devices with `tishadow run`
* You can then push just your changes with `tishadow run --update` (or use my [Sublime Text Build System]({% post_url 2015-10-15-tishadow-sublime-build-system %}))

Want to learn more and dive deeper into [TiShadow][tishadow]? Check out the [TiShadow README][tishadow_readme] for more info.

### Attention
[TiShadow][tishadow] only works for changes in your projects Resources directory and i18n files. For changes elsewhere (e.g. tiapp.xml) you need to rebuild the shadow app with `--shadow` or `--appify` options.

### Running multiple iOS Simulators
You can do this by using this command to launch as many as you need:  
`open -n /Applications/Xcode.app/Contents/Developer/Applications/Simulator.app`

[titanium]: https://github.com/appcelerator/titanium
[tiny]: https://github.com/FokkeZB/tn
[tishadow]: http://tishadow.yydigital.com/
[tishadow_readme]: https://github.com/dbankier/TiShadow/blob/master/README.md
