---
layout: default
title: dirceu.info
---

{% for post in site.posts limit:5 %}
<div class='post'>
  <h2 class='title'>
    <a href="/blog{{ post.url }}">{{ post.title }}</a>
  </h2>
  <div class='entry'>
    <p>
      {{ post.content }}
    </p>
  </div>
</div>
{% endfor %}