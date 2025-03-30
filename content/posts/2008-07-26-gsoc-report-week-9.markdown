---
layout: post
title: GSoC report - week 9
date: 2008-07-26
---

This week I've been working on allowing to define and remove new backend storages while running using the management tool or reloading the config. I worked first on defining a new storage using the management tool. Using <span class="link-external"><a href="http://svn.zope.org/gocept.zeoraid/branches/dirceu-addstoragetool/">this branch</a></span>, you can connect to a new ClientStorage using 'zeoraidX-manage-main add IP:PORT:STORAGE_NAME'. Example:

<pre>
# ./bin/zeoraid1-manage-main add 127.0.0.1:8003:main
</pre>

Now I need to work on the following things:
<ul>
	<li>Add any kind of storage, not only ClientStorage;</li>
	<li>Add a command to remove an existing storage using the client tool;</li>
	<li>Add a command ('reload') to reload the zeo.conf and add/remove the storages as needed.</li>
</ul>
