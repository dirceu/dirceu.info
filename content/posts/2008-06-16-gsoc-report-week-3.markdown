---
layout: post
title: GSoC report - week 3
date: 2008-06-16
---

<span class="link-external"><a href="http://faassen.n--tree.net/blog">Martijn</a></span> suggested that I should write periodic reports about my work on <span class="link-external"><a href="http://code.google.com/soc/2008/zope/appinfo.html?csaid=480505ACAC256B7D">GSoC</a></span>, so here we go.

My first task was to test if <span class="link-external"><a href="http://pypi.python.org/pypi/gocept.zeoraid">ZEORaid</a></span> is processing validations from the backend storages too often. I've done some tests in different situations, and I haven't found anything wrong yet. I have to put more work on this, but it will wait because there are more important things that need attention until the 1.0 release.

After that I've been working on distributing single requests to backends over the available (optimal) backends. Right now ZEORaid (trunk) iterates over a list of optimal storages and gets the first reliable result; I wrote a simple <span class="link-external"><a href="http://svn.zope.org/gocept.zeoraid/branches/distributed-remote-calls/">patch</a></span> to distribute the requests randomly.

My current task is to provide supplemental tests to verify that the new changes actually apply as predicted (e.g. that reading actually does trigger requests to different backends).
