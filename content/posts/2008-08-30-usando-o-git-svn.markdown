---
layout: post
title: Usando o git-svn
date: 2008-08-30
---

Nos &uacute;ltimos dias venho trabalhando em uma app Django e, como sou iniciante no uso desse framework, todos os dias aprendo algum feature novo para melhorar meu c&oacute;digo (como generic views, por exemplo). Para testar esses features o ideal &eacute; criar um branch, usar os features no c&oacute;digo e, se valer a pena, fazer o merge. O problema: usamos svn <a title="PyTown.com" href="http://pytown.com">na empresa</a>, e fazer branches no svn &eacute; bem chatinho (principalmente se comparado ao git). Para resolver isso estou usando o <a title="Git-SVN Crash Course" href="http://git.or.cz/course/svn.html">git-svn</a>.

Segue abaixo meu fluxo de trabalho no git-svn:

<script src="http://gist.github.com/8107.js"></script>

<a title="Gist 8107 - git-svn" href="http://gist.github.com/8107">Link do Gist</a>, para quem n&atilde;o consegue ver no feed.

Enfim, esse &eacute; um post pra que eu mesmo n&atilde;o esque&ccedil;a como fazer isso. Alguns links e tutoriais interessantes sobre o git e o git-svn est&atilde;o no meu <a title="delicious.com/dirceu" href="http://delicious.com/dirceu/">del.icio.us</a>: <a title="delicious.com/dirceu/git" href="http://delicious.com/dirceu/git">http://delicious.com/dirceu/git</a>.