---
layout: default
title: Kategorier
permalink: /categories/
---


# Kategorier


{% assign cats = site.posts | map: 'categories' | uniq | compact | sort %}
{% for c in cats %}
## {{ c }}
{% for post in site.posts %}
{% if post.categories contains c %}
- [{{ post.title }}]({{ post.url | relative_url }})
{% endif %}
{% endfor %}
{% endfor %}
