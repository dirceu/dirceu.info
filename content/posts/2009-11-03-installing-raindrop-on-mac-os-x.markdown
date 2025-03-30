---
layout: post
title: Installing Raindrop on Mac OS X
date: 2009-11-03
---

I'm really excited about [Mozilla Raindrop](http://mozillalabs.com/raindrop); it have many cool features *and* technologies behind it. If you don't know what Raindrop is, take a look at [Introducing Raindrop](http://mozillalabs.com/raindrop/2009/10/22/introducing-raindrop/).

This is a very short how-to showing how to install Raindrop on a machine running Mac OS X; a more complete guide can be found on [Mozilla Wiki](https://wiki.mozilla.org/Raindrop/Install). 

First, download and install [CouchDBX](http://janl.github.com/couchdbx/). Then create a file called ~/.raindrop containing something like this:

<pre>
[account-gmail-username]
proto=imap
kind=gmail
username=username@gmail.com
password=topsecret
ssl=True

[account-twitter-username]
proto=twitter
kind=twitter
username=username
password=topsecret
</pre>

Finally, install Raindrop and it's dependencies:

<pre>
$ sudo port install mercurial
$ sudo easy_install-2.6 -U Skype4Py python-twitter feedparser paisley simplejson
$ hg clone -r 0.1 http://hg.mozilla.org/labs/raindrop
$ cd raindrop
$ ./server/python/check-raindrop.py
$ ./server/python/run-raindrop.py sync-messages --max-age=2days --folder=inbox
</pre>

After the "run-raindrop.py" command finishes you can access [http://127.0.0.1:5984/raindrop/inflow/index.html](http://127.0.0.1:5984/raindrop/inflow/index.html) to see the Raindrop web interface.