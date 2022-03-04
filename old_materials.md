---
layout: page
title: Старые материалы
---

<h1>Старые материалы</h1>

Раньше сайт был сделан по готовому шаблону, в котором было много лишнего.

На данный момент я полностью переписал его практически с нуля и изменил многие вещи, включая более приятный шрифт.

Но материалы сохранились с прошлого сайта и поэтому я решил их оставить здесь.

{% assign index = 1 %}
{% assign olds = site.old | sort: "order" %}
{% for old in olds %}
<a href="{{ old.url | absolute_url }}" class="markdown-link" style="font-size: 26px">{{index}}. {{old.title}}</a>
{% assign index = index | plus: 1 %}
{% endfor %}