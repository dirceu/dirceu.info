---
layout: post
title: Creating RSS feeds with rssifier
date: 2008-10-16
---

Two of my favorite webcomics doesn't have official feeds - <a title="Quadrinhos de humor - tirinhas dos Malvados" href="http://www.malvados.com.br">Malvados</a> and <a title="Giant in the Playground Games - The Order of The Stick" href="http://www.giantitp.com/comics/oots.html">The Order of The Stick</a> (this one actually *have* a feed, but the images aren't shown in the feed items). I didn't like to visit these sites manually, so I quickly wrote a script (which is now a very simple Ruby lib) to create these feeds for me: <a title="dirceu's rssifier at master" href="http://github.com/dirceu/rssifier/tree/master">rssifier</a>.

The lib code is ugly at some points, but it's working for me. Here is an example script (malvados.rb) that uses rssifier to create a feed:

<script src="http://gist.github.com/17310.js"></script>

(<a title="gist: 17310 (malvados.rb)" href="http://gist.github.com/17310">Link of the Gist</a>).

And <a title="malvados.xml" href="http://dirceu.info/malvados.xml">this</a> is the result; I have a cronjob calling the malvados.rb periodically, so this XML gets updated from time to time.

Any contributions via�<a title="dirceu's rssifier at master" href="http://github.com/dirceu/rssifier/tree/master">github</a> are obviously welcome :-).