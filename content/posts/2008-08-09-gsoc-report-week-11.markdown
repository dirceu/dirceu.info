---
layout: post
title: GSoC report - week 11
date: 2008-08-09
---

I've nearly finished the 'reloading' task described in my <a href="http://dev.pytown.com:8080/Dirceu/artigos/gsoc-report-week-11/gsoc-report-week-10/">last report</a>; now we're able to reload the config file without modifications. The code is quite simple: we open and parse the config file, using the list of storages defined there to see what storages needs to be removed (and then we disable them) and what storages needs to be added (and then we add and 'recover' them). I'm now working on a automated test to prove the implementation is right.