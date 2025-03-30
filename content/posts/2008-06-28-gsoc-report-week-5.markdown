---
layout: post
title: GSoC report - week 5
date: 2008-06-28
---

In the beginning of this week I finished the tests for my last task and done some refactoring on it's code. My main problem were to get a storage implementation to use on my tests; first I wrote a subclass of ZODB.DemoStorage.DemoStorage, but it wasn't implementing the full API needed by ZEORaid. Christian said that I should change the base class to ZODB.FileStorage.FileStorage - a pretty trivial change to do, and it solved my problems. After that I fixed some things in the test (that was getting possible false alarms).

Finishing that I begin my current task: parallelizing requests to multiple backends. Basically what ZEORaid currently does when it needs to send write requests to multiple backends is:

<ul>
<li>talk to backend a, wait for answer</li>
<li>talk to backend b, wait for answer</li>
<li>...</li>
<li>proceed</li>
</ul>

What we want it to do is:

<ul>
<li>send request to backend a</li>
<li>send request to backend b</li>
<li>send requests ...</li>
<li>wait for answers of all requests and proceed</li>
</ul>

Reading (briefly) the source code I've found 4 methods that loops the list of backends in the "optimal" state and make calls:

<ul>
<li>new_oid</li>
<li>_apply_all_storages</li>
<li>_synchronise_oids</li>
<li>_apply_single_storage</li>
</ul>

The first three methods could be changed to start len(self.storages_optimal) threads and make the work; then we could use join() to wait for all answers and proceed. About the 4th method, _apply_single_storage(), Christian said that "Distributing the read requests in parallel is a good idea too, but a bit less important than distributing the write requests. Serialized writes currently cause a lot of overhead and slowness and reading won't benefit as much, so I'd leave apply_single_storage out of the story for now.", so I will focus on parallelizing write requests first. He also said that should be some refactoring to have the looping/thread creation only once in the code.

This seems a bit more challenging than my last task (specially to test), which is great! I'm learning a lot about many things, and it's been very fun :-).
