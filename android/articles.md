---
layout: page
title: Статьи
---

<h1>Статьи</h1>

Здесь вы можете почитать статьи по Android разработке на разные темы.

{% assign index = 1 %}
{% assign articles = site.articles %}
{% for article in articles %}
<a href="{{ article.url | absolute_url }}" class="markdown-link" style="font-size: 26px">{{index}}. {{article.title}}</a>
{% assign index = index | plus: 1 %}
{% endfor %}