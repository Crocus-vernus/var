---
layout: default
title: Taggar
permalink: /tags/
---


# Taggar


{% assign all = '' | split: '' %}
{% for post in site.posts %}
{% assign all = all | concat: post.tags %}
{% endfor %}
{% assign tags = all | uniq | sort %}


{% for t in tags %}
## {{ t }}
{% for post in site.posts %}
{% if post.tags contains t %}
- [{{ post.title }}]({{ post.url | relative_url }})
{% endif %}
{% endfor %}
{% endfor %}
