---
layout: default
title: 电子书
---


# 📝 我的博客

这里记录日常随笔。

<ul>
{% assign articles = site.pages | where_exp: "p", "p.url contains '/posts/'" | sort: "url" %}
{% assign count = 0 %}
{% for article in articles %}
  {% unless article.url == '/posts/' or article.url == '/posts/index.html' %}
    {% assign count = count | plus: 1 %}
    <li><a href="{{ article.url | relative_url }}">{{ article.title | default: article.name | remove: ".md" }}</a></li>
  {% endunless %}
{% endfor %}
</ul>

{% if count == 0 %}
<p>暂时还没有发布文章。</p>
{% endif %}

---

[← 返回网站首页]({{ '/' | relative_url }})
