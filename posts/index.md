---
layout: default
title: 博客文章
permalink: /posts/
---

# 博客文章

{% assign articles = site.posts | sort: "date" | reverse %}
{% for post in articles %}
- [{{ post.title }}]({{ post.url | relative_url }}) · {{ post.date | date: "%Y-%m-%d" }}
{% endfor %}
