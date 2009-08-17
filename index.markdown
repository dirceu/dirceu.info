---
layout: default
title: dirceu.info
---

<div id="home">
  {% for post in site.posts limit:4 %}
  <div class="post">
    <h2><a class="post_title" href="/blog{{ post.url }}">{{post.title}}</a></h2>
    <span class="date">{{ post.date | date:"%B %d, %Y" }}</span>
    {{ post.content }}
    <div class="view_comments_link">
      <a href="/blog{{ post.url }}#disqus_thread">View Comments</a> <br />
    </div>
  </div>
  {% endfor %}
</div>