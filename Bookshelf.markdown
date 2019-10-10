---
layout: page
title: Bookshelf
permalink: /bookshelf/
---

<img src="{{site.baseurl}}/assets/img/books.png">

This is my book shelf

<ul>
  {% for post in site.categories.book-review %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>
