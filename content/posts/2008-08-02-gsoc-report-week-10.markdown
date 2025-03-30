---
layout: post
title: GSoC report - week 10
date: 2008-08-02
---

Just a quick report: this week I worked on reloading the zeo.conf file, so we can add or remove storages from the ZEORaid server without having to restart it. It seems to be working well, but it needs better (automated) testing and I need to use the correct ZODB.config options to recognize the config file without problems (this has been my main issue for the week). My work is on <span class="link-external"><a href="http://svn.zope.org/gocept.zeoraid/branches/dirceu-addstoragetool/">this branch</a></span>.
