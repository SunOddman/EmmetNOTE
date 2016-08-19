# CSS使用Emmet



## 参考



### [Emmet文档](http://docs.emmet.io/cheat-sheet/)



[Josh Medeski](http://webdesign.tutsplus.com/author/josh-medeski/)的《[Turbo-Charge Your CSS With Emmet](http://webdesign.tutsplus.com/tutorials/applications/writing-turbo-charged-css-with-emmet/)》一文详细介绍了Emmet和CSS之间的实现方式。



## 属性



CSS提供了属性的值，比如 `font-size` ， `margin` 和 `padding` 等等。



Emmet定义了所有已知CSS属性和缩写：



属性 | 缩写

---- | ----

font-size | fz

border-bottom | bdb

border-top | bdt



##属性值



通过一个组合缩写和所需要的值一起来完成。例如 `fz18` 将输出 `font-size:18px`



## 单位



* `[空]` → `px`

* `p` → `%`

* `e` → `em`

* `r` → `rem`

* `x` → `ex`



## 多个单位



每个值之间用破折号 `-` 即可。

如：



```

body {

 m10-20-30-40

}

⬇️

body {

 margin: 10px 20px 30px 40px;

}

```



## 颜色



使用 `#` 前缀，后面紧跟颜色值，Emmet会重复该数值生成相应的颜色，如：



* `＃1` → `＃111`

* `＃E0` → `＃e0e0e0`

* `＃FC0` → `＃FC0`



## !important



`!important` 可以用 `!` 来自动生成



## 多属性



可以使用 `+` 来创建多个属性。

如：



```

body {

 mt10+pt30+mb50+mb10

}

⬇️

body {

 margin-top: 10px;

 padding-top: 30px;

 margin-bottom: 50px;

 margin-bottom: 10px;

}



<!-- 给 div.panel 创建一些样式 -->

.panel {

 bd2-solid-#3+mb10+p20+c#e

}

⬇️

.panel {

 border: 2px solid #333;

 margin-bottom: 10px;

 padding: 20px;

 color: #eee;

}

```




