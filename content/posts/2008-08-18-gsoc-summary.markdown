---
layout: post
title: GSoC Summary
date: 2008-08-18
---

As the Google Summer of Code coding period comes to an end, I must write about what I have done, so here we go. My proposed tasks were:
<ol>
	<li>Invalidation processing optimization: test if ZEORaid is processing validations from the backend storages too often. This should be proven and maybe optimized.</li>
	<li>Allow defining/removing new backend storages while running using the client tool or reloading the config.</li>
	<li>Define a transaction rate limit / recovery ration to ensure that recovery can always be faster than new transactions that are flowing in.</li>
	<li>Currently requests to multiple backends are run in sequence. This should be done in parallel, to speed up.</li>
	<li>Single requests to backends should be distributed (randomly or round robin) over the available backends.</li>
	<li>Implement `off-site` backends which are written to as a kind of secondary backend which don't have to respond to write requests synchronously to allow replication over slow links to a different site.</li>
</ol>
<strong>Task 1</strong>

The first two weeks were used on this task and on getting myself familiar with gocept.zeoraid codebase. As I said in <a title="GSoC report - week 3" href="http://www.dirceu.info/blog/gsoc-report-week-3/">my first report</a>, I didn't found anything wrong with the invalidation proccess when doing my tests, so I moved to another task.

<strong>Task 5</strong>

This was a reasonably easy one. My main problem was getting an automated test to prove the implementation. It's hard to test a distributed system, and doing the setup is a little problematic; anyway, with help from my mentor, <a title="gocept.com" href="http://gocept.com">Christian Theune</a>, I got a working test. My work is on <a title="distributed-remote-calls" href="http://svn.zope.org/gocept.zeoraid/branches/distributed-remote-calls/">this branch</a>.

<strong>Task 4</strong>

This one was tricky. I had no "real world" experience on writing threads, so I stepped into many obvious bugs - joining threads, dealing with exception handling and such things. I've spent almost four weeks working on this task, but in the end I got it right. My work is on <a title="dirceu-distributed-write-calls" href="http://svn.zope.org/gocept.zeoraid/branches/dirceu-distributed-write-calls/">this branch</a>.

<strong>Task 3</strong>

I started researching a bit about this task, but Christian said that task 2 was much more important, so I stopped working on it.

<strong>Task 2</strong>

My final task over the GSoC period. I started by writing a "add" command to the ZEORaid command-line tool, as I described in <a title="GSoC report - week 9" href="http://www.dirceu.info/blog/gsoc-report-week-9/">this report</a>. It was easy to get this working for ClientStorage objects, but I needed to get it working with other types of storages too; some time later Christian said that it was only a "helper" for me to understand better the way that ZEORaid handles storages and openers.

I dropped this implementation and started working on reloading the entire config file. I got it working in a couple of days, but spent *much* more time than that working on an automated test for it. My work is on <a title="dirceu-addstoragetool" href="http://svn.zope.org/gocept.zeoraid/branches/dirceu-addstoragetool/">this branch</a>.