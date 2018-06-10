---
title: "Jenkins Server Setup on Macos X"
date: 2016-01-30T00:00:00-06:00
draft: false
---

* _Originally published on https://sapuglha.wordpress.com_

* 2018-06-13 _Fixed linked article URL_

There are countless posts with instructions on how to do this, I won't create another.

This is the best and succinct I could find, kudos to the author:

_http://nsbogan.com/mobile%20ci/2015/02/01/jenkins-ci-server-on-osx_

I'd just like to add a couple things I had to do in order to make it work:

Go with the LaunchAgent, easy and good control on start/stop
Add the log file configuration to the plist file
Fix the __.jenkins/log__ directory permissions, mine was failing and I could not figure out why, if it failed to launch, it’s most likely due to a log file not being owned by the Jenkins user. You can verify this by typing:

* __$ ls -l ~/.jenkins__ to see who owns the __log__ directory. If it says __root__, you need to change it to the Jenkins user.
* Enter the following to change ownership: __$ sudo chown -R <the user name> ~/.jenkins/log__