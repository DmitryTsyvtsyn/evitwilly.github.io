---
layout: page
title: Ключевые слова
order: 4
---

# Ключевые слова

Во всех языках программирования есть специальные слова, которые называются ключевыми.

Посмотрите на табличку, здесь приведены ключевые слова языка программирования **Java**:

<table width="100%" cellpadding="0" summary="" class="table-keywords">
<tbody><tr class="table-keywords__tr">
<td width="20%" align="left" class="table-keywords__td"><code>abstract</code></td>
<td width="20%" align="left"><code>continue</code></td>
<td width="20%" align="left"><code>for</code></td>
<td width="20%" align="left"><code>new</code></td>
<td width="20%" align="left" class="table-keywords__td"><code>switch</code></td>
</tr>
<tr>
<td width="20%"><code>assert</code></td>
<td width="20%" align="left"><code>default</code></td>
<td width="20%" align="left"><code>goto</code></td>
<td width="20%" align="left"><code>package</code></td>
<td width="20%" align="left"><code>synchronized</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>boolean</code></td>
<td width="20%" align="left"><code>do</code></td>
<td width="20%" align="left"><code>if</code></td>
<td width="20%" align="left"><code>private</code></td>
<td width="20%" align="left"><code>this</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>break</code></td>
<td width="20%" align="left"><code>double</code></td>
<td width="20%" align="left"><code>implements</code></td>
<td width="20%" align="left"><code>protected</code></td>
<td width="20%" align="left"><code>throw</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>byte</code></td>
<td width="20%" align="left"><code>else</code></td>
<td width="20%" align="left"><code>import</code></td>
<td width="20%" align="left"><code>public</code></td>
<td width="20%" align="left"><code>throws</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>case</code></td>
<td width="20%" align="left"><code>enum</code></td>
<td width="20%" align="left"><code>instanceof</code></td>
<td width="20%" align="left"><code>return</code></td>
<td width="20%" align="left"><code>transient</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>catch</code></td>
<td width="20%" align="left"><code>extends</code></td>
<td width="20%" align="left"><code>int</code></td>
<td width="20%" align="left"><code>short</code></td>
<td width="20%" align="left"><code>try</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>char</code></td>
<td width="20%" align="left"><code>final</code></td>
<td width="20%" align="left"><code>interface</code></td>
<td width="20%" align="left"><code>static</code></td>
<td width="20%" align="left"><code>void</code></td>
</tr>
<tr>
<td width="20%" align="left"><code>class</code></td>
<td width="20%" align="left"><code>finally</code></td>
<td width="20%" align="left"><code>long</code></td>
<td width="20%" align="left"><code>strictfp</code></td>
<td width="20%" align="left"><code>volatile</code></td>
</tr>
<tr class="table-keywords__tr">
<td width="20%" align="left" class="table-keywords__td"><code>const</code></td>
<td width="20%" align="left"><code>float</code></td>
<td width="20%" align="left"><code>native</code></td>
<td width="20%" align="left"><code>super</code></td>
<td width="20%" align="left" class="table-keywords__td"><code>while</code></td>
</tr>
</tbody></table>

Как вы думаете почему именно эти слова являются ключевыми? 

Потому что создатели самого языка программирования так решили. Их еще называют зарезервированными, то есть заранее определеными.

А зачем они нужны?

Элементарно, чтобы строить различные конструкции на языке программирования, которые в будущем станут программой или приложением.

Каждое слово имеет определенное значение.

Например: <code>for</code>:

<pre class="prettyprint">
// создание цикла:
// 1. создаем переменную number с начальным значением 0
// 2. сравниваем значение number с числом 10, если меньше то переходим к
// следующему шагу, иначе завершаем выполнение цикла 
// 3. выполняем код в блоке, который размещен между скобками { код }
// 4. прибавляем к number единицу и переходим на второй шаг
for (int number = 0; number < 10; number++) {
  // выполнить код 10 раз
}	
</pre>

Обратите внимание, ключевое слово не существует само по себе, оно объединяется в определенные конструкции.

Простыми словами, вы комбинируете ключевые слова языка программирования, объединяя их в конструкции и создаете программу.

**Тут важно отметить, что любой код это не просто комбинации ключевых слов языка программирования, это еще работа с различными данными, потому что программирование - это создание программ, которые работают с информацией.**

**Например:** практически в любом мобильном приложении есть текст и картинки.

Давайте еще раз вернёмся к коду, который мы уже рассматривали выше:

<pre class="prettyprint">
for (int number = 0; number < 10; number++) {
  // выполнить код 10 раз
}
</pre>

Ключевое или зарезервированное (если вам так больше нравится) слово <code>for</code> является частью конструкции:

<pre class="prettyprint">
for (создание переменной счетчика; условие; изменение переменной счетчика) {
  // код, который выполняется в цикле
}
</pre>

Мы не можем просто написать <code>for</code> и запустить программу, это будет некорректно, потому что
любое **ключевое слово в языке программирования используется в какой-то конструкции, операции или еще где-то**.

**Важная заметка: в каждом примере вы можете заметить ключевое слово, оно подсвечивается определенным светом**

## Практика

Посмотрите какие есть ключевые слова в **Kotlin'е.**

*Глоссарий:*

1. *Ключевое слово в языке программирования - специальное слово, которое определенно создателями языка программирования и которое используется для построения различных языковых конструкций*