---
layout: post
title:  "About Starting the Blog"
date:   2015-09-24 12:30:46
tags: jekyll, blog, ruby
---
### Motivation
This is about putting my daily experiences and code snippets in a centralized space and at the same time trying out a github hosted blog with [Jekyll][jekyll].  

### How-To
Hosting a blog this way is easy:

* Create a github repo with your account name in the form of `username.github.io`
* Install [Jekyll][jekyll]

```bash
gem install jekyll
jekyll new SITENAME
cd SITENAME
jekyll server
```

* Edit the `_config.yml` to suit your needs
* Upload your site to github

```bash
git init
git add .
git commit -am "init"
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin master
```

* Github automagically builds jekyll blogs when you push to your repos master branch.
* You're done. So make some more posts

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll.

[jekyll]:      http://jekyllrb.com
