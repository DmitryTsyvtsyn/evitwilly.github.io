---
layout: page
title: Планирование
---

<h1>Планирование</h1>

Я решил составить несколько простых схем обучения, чтобы создать целостное представление 
и понимание: **что нужно будет изучать и по каким материалам.**

{% assign index = 1 %}
{% assign plans = site.plans | sort: "order" %}
{% for plan in plans %}
<a href="{{ plan.url | absolute_url }}" class="markdown-link" style="font-size: 26px">{{index}}. {{plan.title}}</a>
{% assign index = index | plus: 1 %}
{% endfor %}
