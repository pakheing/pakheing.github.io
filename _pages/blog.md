---
layout: page
title: Blog
permalink: /blog/
---

## Blog Posts

{% for post in site.posts %}
  <article class="blog-list-item">
    <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </article>
{% endfor %}

{% if site.posts.size == 0 %}
  <p>No blog posts yet. Stay tuned!</p>
{% endif %}
