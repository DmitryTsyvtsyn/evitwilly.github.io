---
layout: page
title: RecyclerView внутри NestedScrollView
---

<h1>RecyclerView внутри NestedScrollView</h1>

Начнем с тезиса: 

**Никогда не используйте RecyclerView вместе с NestedScrollView.**

Проведем небольшой эксперимент.

Напишим вот такой код:

<pre class="prettyprint lang-kotlin">
class MainActivity : AppCompatActivity() {

    @SuppressLint("Range")
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        val list = RecyclerView(this)
        list.layoutManager = LinearLayoutManager(this, LinearLayoutManager.VERTICAL, false)
        list.adapter = object: RecyclerView.Adapter&lt;RecyclerView.ViewHolder&gt;() {
            override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): RecyclerView.ViewHolder {
                Log.d(TAG, "onCreateViewHolder() called")
                val text = AppCompatTextView(parent.context).apply {
                    val sixteenDp = (resources.displayMetrics.density * 16).roundToInt()
                    setPadding(sixteenDp, sixteenDp, sixteenDp, sixteenDp)
                    setTextSize(TypedValue.COMPLEX_UNIT_SP, 20f)
                }
                return object: RecyclerView.ViewHolder(text) {}
            }

            override fun onBindViewHolder(holder: RecyclerView.ViewHolder, position: Int) {
                Log.d(TAG, "onBindViewHolder() called, position -> $position")
                (holder.itemView as TextView).text = "RecyclerView item $position"
            }

            override fun getItemCount() = 50

        }
        val linear = LinearLayoutCompat(this)
        linear.orientation = LinearLayoutCompat.VERTICAL

        val textView = AppCompatTextView(this).apply {
            val thirtyTwo = (resources.displayMetrics.density * 32).roundToInt()
            setPadding(thirtyTwo, thirtyTwo, thirtyTwo, thirtyTwo)
            text = "RecyclerView + NestedScrollView!"
            setTextSize(TypedValue.COMPLEX_UNIT_SP, 48f)
        }

        linear.addView(textView)
        linear.addView(list)

        setContentView(linear)


    }

    companion object {
        private const val TAG = "MainActivity/I"
    }

}
</pre>

Здесь мы создаем типичный <code>RecyclerView</code> и заполняем его тестовыми данными.

Смотрим консоль:

<img src="/articles/recyclerview_and_nestedscrollview/img1.png" />

Скроллим список:

<img src="/articles/recyclerview_and_nestedscrollview/img2.png" />

Как видете ничего необычного, <code>RecyclerView</code> делает то, для чего он был создан: **переиспользует вьюшки.**

Давай положим его в <code>NestedScrollView</code>:

<pre class="prettyprint lang-kotlin">
class MainActivity : AppCompatActivity() {

    @SuppressLint("Range")
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        val list = RecyclerView(this)
        list.layoutManager = LinearLayoutManager(this, LinearLayoutManager.VERTICAL, false)
        list.adapter = object: RecyclerView.Adapter&lt;RecyclerView.ViewHolder&gt;() {
            override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): RecyclerView.ViewHolder {
                Log.d(TAG, "onCreateViewHolder() called")
                val text = AppCompatTextView(parent.context).apply {
                    val sixteenDp = (resources.displayMetrics.density * 16).roundToInt()
                    setPadding(sixteenDp, sixteenDp, sixteenDp, sixteenDp)
                    setTextSize(TypedValue.COMPLEX_UNIT_SP, 20f)
                }
                return object: RecyclerView.ViewHolder(text) {}
            }

            override fun onBindViewHolder(holder: RecyclerView.ViewHolder, position: Int) {
                Log.d(TAG, "onBindViewHolder() called, position -> $position")
                (holder.itemView as TextView).text = "RecyclerView item $position"
            }

            override fun getItemCount() = 50

        }
        val linear = LinearLayoutCompat(this)
        linear.orientation = LinearLayoutCompat.VERTICAL

        val textView = AppCompatTextView(this).apply {
            val thirtyTwo = (resources.displayMetrics.density * 32).roundToInt()
            setPadding(thirtyTwo, thirtyTwo, thirtyTwo, thirtyTwo)
            text = "RecyclerView + NestedScrollView!"
            setTextSize(TypedValue.COMPLEX_UNIT_SP, 48f)
        }

        linear.addView(textView)
        linear.addView(list)

        val nestedScrollView = NestedScrollView(this)
        nestedScrollView.addView(linear)

        setContentView(nestedScrollView)


    }

    companion object {
        private const val TAG = "MainActivity/I"
    }

}
</pre>

Запускаем и смотрим в консоль:

<img src="/articles/recyclerview_and_nestedscrollview/img3.png" />

Были созданы сразу все вьюшки и ни одна не была переиспользована!

Вы просто могли использовать <code>LinearLayout</code> без всяких адаптеров и получили бы такой же результат.

И в заключении я повторюсь: **никогда не используйте RecyclerView вместе с NestedScrollView!**