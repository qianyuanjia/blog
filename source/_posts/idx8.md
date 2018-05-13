---
title: HTML常用标签介绍
date: 2018-05-13 15:23:18
tags: html
---
## 1. HTML是什么，HTML5是什么？
HTML是一种被广泛使用的用来创建网页的超文本标记语言。它用各种不同的标签描述了一个网页的结构和内容。HTML不短更新，从最开始的HTML2.0发展到最新的HTML5。HTML5最主要的目的是为了提高语义化，改善开发者和用户对万维网的体验。HTML5提供了许多新的标签和功能强大的API。
## 2. HTML有哪些常用的标签？
HTML中的元素类型可以划分为两类，一类是区块元素（block）,另一类是内联元素（inline）。
**区块元素：效果上回独占一行的元素。**
**内联元素：不会折行。**
- ### 文本样式相关的标签
```
<b></b>文字加粗，已经废弃，不推荐使用
<strong></strong>文字加粗并且有语义上的强调，推荐使用
<i></i>文字倾斜。
<em></em>文字倾斜，并且有强调的语气。
h1~h6标签，描述语义的标签，并且为block元素，不同浏览器中这些标签的margin样式可能不同。
<p></P>段落标签，典型的block标签。
<br>换行标签
<hr>输出分割线
```
- ### 分区元素
分区元素常用语页面布局，主要有div和span，这两个标签没有默认的样式，并且分别为块元素和内联元素，因为没有特殊语义，常常需要加class属性用于标识。
- 页面中显示图片
```
<img src="图片路径" alt="图片信息">，这个标签会想服务器发起一个请求，并且加载
图片。它是特殊的inline-block元素，可以设置宽高，但是不会折行显示。alt属性用于
图片加载失败是给用户的提示信息。
```
- ### 链接元素
> a是inline元素，其中href属性制定了要跳转的url和邮箱（
> mailto:3126731@qq.com）、javascript的代码。target属性指定了在哪个页面中打开新
> 内容。还可以定位锚点href="#xxx"，跳转到XXX锚点的位置。
- ### 列表元素
> 有序列表ol,列表项li
> 无序列表ul，列表项li
> 定义列表dl，dt是类型定义，dd是类型详情
- ### 表单元素
form的作用是收集用户的信息，并将其提交给动态页面与后台程序进行交互。
<form > </form > 典型的区块元素,form本身没有任何的显示效果，只有语义性的概念。action属性指定处理数据的动态页面，action属性基本在任何情况下都不可省略。 method属性也要指定：get（获取资源）、post（向服务器提交）等。enctype的全名是：Encoded Type（表单中提交数据的编码类型），可取值总共有三个：text/plain（表单数据不做任何处理直接上传），application/x-www-form-urlencoded（默认值，把表单中的数据（比如中文字符）编码后再上传，只能对字符进行编码，也就是说只能提交字符数据，如果想提交的是字节数据，必须使用第三项）、multipart/form-data（以一种特殊的格式上传字符/字节数据） 
<input / > 必须要用type来指定类型，类型分别有：submit、text、password、radio（单选按钮，典型内联元素）、checkbox（复选框），默认是text类型。 典型的内联（inline）元素。 name属性绝对不能省略，name表示的是输入的内容含义。 value属性：在输入框中显示的文字提示，提示用户需要输入的可能值：比如用户名、邮箱等。 maxlength：限制最大输入的字符个数 。更加复杂的设置智能根据JS来做。 readonly：只读属性，关于boolean属性在html 5中有特别的说明，这种属性会提交给服务器。 disabled属性表示禁用（表现形式是相应的框会变成灰色），这种属性的特点是不能提交给服务器。 在其中指定一个id，和下面将要讲到的label标签中的for属性配合使用。 checked写上就表示默认被选择。 