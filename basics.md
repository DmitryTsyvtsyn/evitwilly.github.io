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


<!-- <a href="/basics/introduction/" class="markdown-link" style="font-size: 26px">1. Введение</a>

<a href="/basics/coding_process/" class="markdown-link" style="font-size: 26px">2. Процесс кодинга</a>

<a href="/basics/work_environment" class="markdown-link" style="font-size: 26px">3. Рабочее окружение</a>

<a href="/basics/keywords" class="markdown-link" style="font-size: 26px">4. Ключевые слова</a>

<a href="/basics/variables/" class="markdown-link" style="font-size: 26px">5. Переменные</a>

<a href="/basics/logic_datatype/" class="markdown-link" style="font-size: 26px">6. Логический тип данных</a>

<a href="/basics/constructions_language" class="markdown-link" style="font-size: 26px">7. Основные конструкции языка</a> -->

<!-- 
<a href="" class="markdown-link" style="font-size: 26px">4. Типы программирования</a>

<a href="" class="markdown-link" style="font-size: 26px">5. Процедурное программирование</a>

<a href="" class="markdown-link" style="font-size: 26px">5. Объектно-ориентированное программирование</a>

<a href="" class="markdown-link" style="font-size: 26px">6. Git</a>

<a href="" class="markdown-link" style="font-size: 26px">7. Командная строка</a>

<a href="" class="markdown-link" style="font-size: 26px">7. Hello, World!</a> -->





