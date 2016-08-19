# HTML使用Emmet



Emmet使用定义的缩写来生成元素。

一旦定义好缩写之后，按下`tab`键就能生成你所请求的代码。



## 参考文档



### [Emmet文档](http://docs.emmet.io/cheat-sheet/)



Emmet和HTML更详尽的介绍可以阅读：[Matt West](http://blog.teamtreehouse.com/author/mattwest)的《[Using Emmet to Speed Up Front-End Web Development](http://blog.teamtreehouse.com/using-emmet-speed-front-end-web-development)》、[Zeno Rocha](http://coding.smashingmagazine.com/author/zeno-rocha)的《[Goodbye, Zen Coding. Hello, Emmet!](http://coding.smashingmagazine.com/2013/03/26/goodbye-zen-coding-hello-emmet/)》和[白牙](http://www.w3cplus.com/blogs/pet)的《[前端开发必备！Emmet使用手册](http://www.w3cplus.com/tools/emmet-cheat-sheet.html)》



## 创建初始文档



创建对应文档类型的`doctype`默认标签：如下：

* `html:5` 或 `!` ：HTML 5文档类型

* `html:xt` ：XHTML 过渡型文档类型

* `html:xs` ：XHTML 严格型文档类型

* `html:4t` ：HTML 4过渡型文档类型

* `html:4s` ：HTML 4严格型文档类型



## 子元素：>



使用 `>` 运算符可以用来生成彼此嵌套的元素。

如：



```

section>div>p

```

会生成如下代码：



```html

<section>

 <div>

 <p></p>

 </div>

</section>

```



## 相邻元素：+



使用 `+` 运算符可以用来生成彼此相邻的元素。

如：



```

section+div+p

```

会生成下面的代码：



```html

<section></section>

<div></div>

<p></p>

```



## 返回上一层：^



使用 `^` 运算符，可以让你的代码返回上一层。当你使用 `>` 嵌套元素时，想让后面的元素回到上一层，可以使用 `^` 运算符。

如：



```

section>div>p>a^p

```

这个缩写将两个段落元素都放在 `div` 内，但只有第一个段落会包含一个连接。这种写法等价于：



```

section>div>(p>a)+p

```

都会生成如下代码：



```html

<section>

 <div>

 <p><a href=""></a></p>

 <p></p>

 </div>

</section>

```



## 乘法：*



* **基本用法**



如果你想一次性生成多个相同的元素，比如列表中的li，可以使用乘法运算符 `*`。

如：



```

ul>li*5

```

上面的代码会生成5个 `li` ：



```html

<ul>

 <li></li>

 <li></li>

 <li></li>

 <li></li>

 <li></li>

</ul>

```



* **递增和递减**



还可以通过 `$` 符号做递增；通过 `$@-` 符号做递减；通过 `$@3*5` 这样的方式开始命名。

如：



```html

ul>li.item.item-$*5>a

⬇️

<ul>

 <li class="item item-1"><a href=""></a></li>

 <li class="item item-2"><a href=""></a></li>

 <li class="item item-3"><a href=""></a></li>

 <li class="item item-4"><a href=""></a></li>

 <li class="item item-5"><a href=""></a></li>

</ul>



ul>li.item.item-$@-*5

⬇️

<ul>

 <li class="item item-5"></li>

 <li class="item item-4"></li>

 <li class="item item-3"></li>

 <li class="item item-2"></li>

 <li class="item item-1"></li>

</ul>



ul>li.item.item-$@-3*5

⬇️

<ul>

 <li class="item item-7"></li>

 <li class="item item-6"></li>

 <li class="item item-5"></li>

 <li class="item item-4"></li>

 <li class="item item-3"></li>

</ul>



ul>li.item.item-$@3*5

⬇️

<ul>

 <li class="item item-3"></li>

 <li class="item item-4"></li>

 <li class="item item-5"></li>

 <li class="item item-6"></li>

 <li class="item item-7"></li>

</ul>



h$[title=item$]{Header $}*3

⬇️

<h1 title="item1">Header 1</h1>

<h2 title="item2">Header 2</h2>

<h3 title="item3">Header 3</h3>



ul>li.item$$$*5

⬇️

<ul>

 <li class="item001"></li>

 <li class="item002"></li>

 <li class="item003"></li>

 <li class="item004"></li>

 <li class="item005"></li>

</ul>

```



## 组合：()



为了更有效的利用嵌套，可以通过 `()` 将一个块组合在一起。

如：



```html

ul>(li>a)>*3

或者

ui>li*3>a

⬇️

<ul>

 <li><a href=""></a></li>

 <li><a href=""></a></li>

 <li><a href=""></a></li>

</ul>

```

快速生成网页布局（包括 页头、主体和页脚三个部分）



```html

div>header+(article>p*3)+footer>p

⬇️

<div>

 <header></header>

 <article>

 <p></p>

 <p></p>

 <p></p>

 </article>

 <footer>

 <p></p>

 </footer>

</div>

```



## 快速添加类名、ID、文本和属性



* 使用 `E#ID` 添加ID名

* 使用 `E.class` 添加类名

* 使用 `E[attr]` 添加属性

* 使用 `E{text}` 添加文本



如：



```html

div#main

⬇️

<div id="main"></div>



div.content

⬇️

<div class="content"></div>



div#main.content

⬇️

<div id="main" class="content"></div>



a[href="##"]

⬇️

<a href="##"></a>



p{Hello World!}

⬇️

<p>Hello World!</p>



(div#header[role="header"]>div.container)+div#page[role="page"]>div.container

⬇️

<div id="header" role="header">

 <div class="container"></div>

</div>

<div id="page" role="page">

 <div class="container"></div>

</div>



div#footer[role="footer" bg="footerbg"]>div.container>p{This is footer}

⬇️

<div id="footer" role="footer" bg="footerbg">

 <div class="container">

 <p>This is footer</p>

 </div>

</div>



p>{Click }+a{here}+{ to continue}

⬇️

<p>Click <a href="">here</a> to continue</p>

```



## 省略标签名



默认情况下，如下情况可以省略



* 一般情况下 `.` 等于 `div.`

* `ul` 和 `ol` 的下层中的 `.` 指的是 `li`

* `table` 、 `tbody` 、 `thead` 和 `tfoot` 的下层中的 `.` 指的是 `tr`

* `tr` 的下层中的 `.` 指的是 `td`

* `select` 和 `optgroup` 的下层中的 `.` 指的是 `option`








