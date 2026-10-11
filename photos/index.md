---
layout: default
title: 摄影图文
permalink: /photos/
---

# 摄影图文

{% for post in site.pages %}
  {% if post.path contains 'photos/' and post.path != 'photos/index.md' %}
- [{{ post.title | default: post.name }}]({{ post.url | relative_url }}){% if post.date %} · {{ post.date | date: "%Y-%m-%d" }}{% endif %}
  {% endif %}
{% endfor %}

---

个人文章与摄影档案 · 本地另有备份
