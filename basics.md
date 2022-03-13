---
layout: page
title: Основы
---

<h1>Основы</h1>

Если вы полноценный новичок, то вы выбрали правильный раздел!

Здесь мы изучим самые основные принципы и вещи в программировании, которые вам нужно знать

{% assign index = 1 %}
{% assign basics = site.basics | sort: "order" %}
{% for basic in basics %}
<a href="{{ basic.url | absolute_url }}" class="markdown-link" style="font-size: 26px">{{index}}. {{basic.title}}</a>
{% assign index = index | plus: 1 %}
{% endfor %}



