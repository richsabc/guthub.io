
---
layout: default
title: 电子书
---

# 📚 我的电子书库

这里存放值得长期保存、阅读与参考的电子书和文献。

## 📖 精选藏书

{% assign ebook_files = site.static_files | where_exp: "file", "file.path contains '/books/'" | sort: "name" %}
{% for file in ebook_files %}
  {% assign ext = file.extname | downcase %}
  {% if ext == ".pdf" or ext == ".epub" %}
- [{{ file.name }}]({{ file.path | relative_url }})
  {% endif %}
{% endfor %}

---

[← 返回网站首页]({{ '/' | relative_url }})
