---
layout: page
title: All Posts
permalink: /Posts/
---

<img src="{{site.baseurl}}/assets/img/blommor.png">

<ul>
  {% for post in site.posts %}
    {% if post.url %}
        <a href="{{ post.url }}">{{ post.title }}</a><br>
    {% endif %}
  {% endfor %}
</ul>
