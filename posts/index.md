---

layout: default
title: 博客
---

# 📝 我的博客

这里记录日常随笔、生活观察与摄影文章。

{% assign articles = site.pages | where_exp: "p", "p.url contains '/posts/'" | sort: "url" %}
{% assign count = 0 %}
{% for article in articles %}
  {% unless article.url == '/posts/' or article.url == '/posts/index.html' %}
    {% assign count = count | plus: 1 %}
    - [{{ article.title | default: article.name | remove: ".md" }}]({{ article.url | relative_url }})
  {% endunless %}
{% endfor %}

{% if count == 0 %}
暂时还没有发布文章。
{% endif %}
---

[← 返回网站首页]({{ '/' | relative_url }})
