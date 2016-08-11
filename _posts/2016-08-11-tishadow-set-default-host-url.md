---
published: true
layout: post
date: 2016-08-11T08:00:12.000Z
tags: 'development, build, tishadow, default, host'
---
You use [tishadow](http://tishadow.yydigital.com/) for rapid development of appcelerator titanium apps?  
If there is more then one ip configured on your system, e.g virtualbox ethernet, then you have to select the host ip everytime you build an app with `--appify`.  
```bash
Which ip address you want to use?
   1)  192.168.1.42  IPv4(en0, external)
   2)  192.168.57.1  IPv4(vboxnet1, external)
Select a ip_address by number:
```
  
You can **skip the above prompt** by setting the default host in the tishadow config with this command:  

```bash
ts config --host YOUR.HOST.IP.HERE
```

it will be written to tishadow's config file and you will not be prompted to enter it again.
