---
layout: post
title: Installing Erlang, Yaws and Erlyweb on Mac OS X
date: 2009-08-10
---

This is a short how-to showing how to install <a title="Erlang Programming Language" href="http://erlang.org/">Erlang</a>, <a title="Yaws" href="http://yaws.hyber.org/">Yaws</a> and <a title="Erlyweb: The Erlang Twist on Web Frameworks" href="http://erlyweb.org/">Erlyweb</a> on Mac OS X via <a title="The MacPorts Project" href="http://www.macports.org/">MacPorts</a>.

<p>First we need to install Erlang and Yaws and link Yaws under erlang/lib:</p>
<pre>$ sudo port install erlang yaws
$ sudo ln -sf /opt/local/lib/yaws /opt/local/lib/erlang/lib/yaws</pre><br />
<p>Then we append erlang/bin to the PATH env variable (you can put this on your ~/.bashrc file):</p>
<pre>$ export PATH=/opt/local/lib/erlang/bin:$PATH</pre><br />
<p>And finally we install Erlyweb:</p>
<pre>$ git clone git://github.com/dirceu/erlyweb.git
$ cd erlyweb ; make ; sudo make install
$ cd .. ; rm -rf erlyweb</pre><br />
<p>My fork of Erlyweb contains some changes I did today:</p>

<ul>
<li>"make install" creates a create_erlyweb_app.sh under erlang/bin. It's just a link to erlyweb/scripts/create_app.sh and takes two arguments: AppName and AppDir;</li>
<li>erlyweb_util:create_app/2 now creates a "log" directory (for Yaws log files) and a ready-to-run yaws.conf file.</li>
</ul>

<p>With this changes you can create and run a simple application using:</p>
<pre>$ mkdir -p ~/apps/myapp
$ create_erlyweb_app.sh myapp ~/apps
$ cd ~/apps/myapp
$ yaws --conf yaws.conf</pre>