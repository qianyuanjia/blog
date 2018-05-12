---
title: HTML几个重要标签细节问题
date: 2018-05-12 21:57:00
tags: html
---
### a标签
a标签取名于是'anchor'的第一个字母，它的主要属性有href(不可少)以及target(可省)，
当href属性值以#开头时，主要用于页面内锚点跳转；当值以'//'开头时，为省略协议的写法，浏览器在地址栏会自动补全协议，补全的协议与当前页面协议相同；当值以'http://'开头时，就会访问外部资源；还可以使用javascript伪协议阻止a标签的默认跳转，写法可以是'javascript:;'以及'javascript:void(0);',还可以在'javascript:'之后加一个javascript语句，点击a标签就会执行这个语句。
target的常见属性值为'_self,_blank,_parent,_top','_self'是默认值，在当前页面完成跳转，'_blank'会打开一个新窗口跳转，后两个只有当页面中存在嵌套的iframe才能显示效果，分别表示在父窗口跳转和顶级窗口跳转，当父窗口就是顶级窗口时，两个值没什么区别。如果要修改a标签的默认跳转方式，可以在head中加一句'&lt;base target="_blank"&gt;',就会将默认跳转方式设为在新窗口中跳转。当页面中存在iframe,并且iframe设置了name属性，a标签的target值可以设置为iframe的name属性值，这样的话点击a标签就会在ifame中显示跳转的内容。
### iframe标签
iframe默认会带一个丑陋的边框，所以要去掉的话最好加上frameborder="0"属性。ifame有一个比较特殊的sandbox属性，读作‘沙盒’属性比较好记。它主要是限制嵌套页面的一些权限，IE9以下不支持。它的主要属性如下：
![](sandbox.jpg)
一般我们使用的话设置sandbox=''就可以了，主要出于安全策略的考虑，防止我们的页面收到嵌套页面的攻击，脚本攻击以及表单提交，DOM内容窃取等。
### table标签
table标签的直接子元素只有thead、tbody、tfoot以及colgroup四个，没有其他的。thead主要用于放置表头内容，tbody是表格的主体部分，tfoot是表格的结尾部分，三个在位置上应该排列有先后，但是即使你打乱顺序排列，浏览器在渲染是还是会根据表头，主体，结尾的顺序展示。这三个标签都是可以省略的，但是缺少tbody的话，浏览器会自动加上。并且不在这三个标签的元素会自动并入到tbody中。colgroup用于设置每列的一些属性，搭配col标签使用，写法如下：
![](col.jpg)
测试了下只有width以及bgcolor属性支持的比较好，因此主要用于设置每列的宽度或背景颜色。
### 如何用a标签下载资源
通常有两种方式，一种是需要后端的配合。后端向客户端发送数据时在响应头中设置Content-Type属性值为application/octet-stream。另一种是强制a标签进行下载，只要a标签设置一个download属性就可以啦，是不是很简单！
### form标签
form表单提交方式有两种，一种是通过js代码实现，另一种是通过提交按钮实现。提交按钮有两种，一种是input类型的按钮，一定要设置type=submit属性，另一种是button类型的按钮，不写type的话默认是submit按钮，可以给它设置type=submit强调下。form表单的method属性只能设置为post或get，其他的put，patch等不能设置，没有效果。当设置为get时，表单中的数据以请求参数的方式发送，在地址栏中显示。而采用post方式时，表单中的数据以Form Data的形式放在请求头的第四部分。并且可以在action属性值后加'?xxx=yyy'的形式添加请求参数。所以get方式只有请求参数，而post方式既可以有请求参数，也可有Form Data第四部分。好啦，今天就写到这儿！
