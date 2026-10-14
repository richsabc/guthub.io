---
layout: default
title: 摄影
---

# 📷 摄影

这里记录摄影作品、拍摄经历、器材体验与摄影心得。

## 摄影文章

{% assign photo_pages = site.pages | where_exp: "p", "p.url contains '/photos/'" | sort: "url" %}
{% assign count = 0 %}

<ul>
{% for article in photo_pages %}
  {% unless article.url == '/photos/' or article.url == '/photos/index.html' %}
    {% assign count = count | plus: 1 %}
    <li><a href="{{ article.url | relative_url }}">{{ article.title | default: article.name | remove: ".md" }}</a></li>
  {% endunless %}
{% endfor %}
</ul>

{% if count == 0 %}
暂时还没有发布文章。
{% endif %}

---

[← 返回网站首页]({{ '/' | relative_url }})
