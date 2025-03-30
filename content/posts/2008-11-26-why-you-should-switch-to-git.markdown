---
layout: post
title: Why you should switch to Git
date: 2008-11-26
---

Over the last few months I've switched from Subversion and Bazaar to Git. I'm using Git on a daily basis now and I'm much happier with it than I was when using Subversion. In this post I'll try to explain why and provide some useful links.
<h3>You can work offline</h3>
How cool is that? You can clone a repository (which is similar to doing a "checkout"), go offline and then change what you want, commit, merge, branch and whatever. When you go back online you can push your commits to the origin server - if you want.

When using Git you don't work on a "working copy" of the last revision (as you do with Subversion) - using "git clone URL" you clone the *entire repository*: all commits, merges, branches, everything.
<h3>It's fast as hell</h3>
Git is fast. Really fast. Doing commits, branches, merging and even cloning a remote repository: everything is (way) faster than Subversion. I didn't do any benchmarks on my own, but it's what I can see.
<h3>It will make you want to try new things</h3>
Branching and merging in Git are trivial tasks. In Subversion these operations are kind of <em>troublesome</em>; you need to interact with the remote copy, merging is not so easy and you need write access to the remote repository. This - the need of write access - is actually the main problem with it.

With Git I can clone a remote repository, create branches, try things out and never ever send anything back to the origin repository. I can do pretty much everything without getting permission, without bureaucracy.
<h3>Github</h3>
<a href="http://github.com"><img class="size-medium wp-image-109" title="Github - Social Code Hosting" src="/blog/images/github_logo.png" alt="Github - Social Code Hosting" width="157" height="60" align="left" /></a>
<a title="Github" href="http://github.com">Github</a> is a really cool social network for programmers. It allows you to share and manage Git repositories in a very easy way; with a few clicks one person can fork, say, <a title="httparty" href="http://github.com/jnunemaker/httparty">httparty</a>, branch, merge and do whatever with it.

Also it allows you to make "pull requests" (a way to poke someone and let them know you&iacute;ve got some code they may want) and  get your code on the main repository.
<h3>Some useful links about Git</h3>
So this is why I'm using Git. The following links are tutorials and explanations about how and why Git works and more reasons to use it. Enjoy.
<ul>
	<li><a title="The Thing About Git" href="http://tomayko.com/writings/the-thing-about-git">The Thing About Git</a></li>
	<li><a title="Using Git within a project (forking around)" href="http://drnicwilliams.com/2008/02/03/using-git-within-a-team/">Using Git within a project (forking around)</a></li>
	<li><a title="New to Git?" href="http://github.com/blog/120-new-to-git">New to Git?</a></li>
	<li><a title="Git Internals PDF | PeepCode" href="http://peepcode.com/products/git-internals-pdf">Git Internals</a> (Highly Recommended!)</li>
</ul>