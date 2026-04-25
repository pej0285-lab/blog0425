---
title: Blog
layout: default
nav_order: 2
has_children: true
permalink: /blog/
---

# Blog

{% if site.posts.size > 0 %}
  {% assign posts_by_order = site.posts | sort: "nav_order" %}
  {% for post in posts_by_order %}
## [{{ post.title }}]({{ post.url | relative_url }})

{{ post.date | date: "%Y-%m-%d" }}

{{ post.excerpt }}
  {% endfor %}
{% else %}
No posts yet.
{% endif %}
