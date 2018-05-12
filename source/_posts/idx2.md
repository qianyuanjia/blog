---
title: 几个小问题
date: 2018-05-11 13:28:02
tags:   前端面试题
---
## 一、HTML是什么？
    HTML（Hyper Text Marrk-up Language），即超文本标记语言，是WWW的描述语言，由Tim-Berners-Lee提出。超文本标记语言是标准通用标记语言的下一个应用，是一种规范，也是一种标准，它通过标记符号来标记要显示的网页中的各个部分。之所以称为‘’超文本‘’,就是因为页面内不仅可以包含文本元素，也可以包含图片、视频、音频等非文字元素。

## 二、HTML5是什么？
    万维网的核心语言，标准通用标记语言的下一个应用超文本标记语言的第五次重大修改，设计的目的是为了在移动设备上支持多媒体。比HTML4新增了很多元素和属性，也废弃了一些元素和属性。HTML5增加了很多语义化的标签，还提供了很多功能化的API，极大的改进了用户与文档的交互方式。

## 三、对Web标准以及W3C的理解和认识
    标签闭合、标签小写、不乱嵌套、提高搜索机器人的搜索几率、使用外链CSS和js脚本、结构行为表现的分离、文件下载与页面速度更快、内容能被更多用户所访问，内容能被更广泛的设备所访问、更少的代码和组件、容易维护、改版方便，不需要变动页面的内容，提供打印版而不需要复制内容，提高网站易用性。

## 四、xhtml和html有什么区别
    HTML是一种基本的Web网页设计语言，XHTML是一个基于XML的置标语言，它在书写上比HTML更加规范，严格，但是由于缺乏灵活性不太受开发者的喜爱。
    最主要的不同：
        XHTML元素必须被正确的嵌套
        XHTML元素必须被关闭
        标签名必须小写
        XHTML文档必须拥有根元素

## 五、DocType？严格模式与混杂模式，如何触发这两种模式，区分他们有何意义？
    用于声明文档使用哪种规范（html/xhtml），一般为严格过度基于框架的html文档加入xml声明可触发，解析方式更改为IE5.5，拥有IE5.5的bug。

## 六、行内元素有哪些？块级元素有哪些？CSS的盒模型。
    块级元素：div、P、h1~h6、form、ul、ol等
    行内元素：a 、span、i、input等
    CSS盒模型：内容，padding，border，margin
    标准盒模型、怪异盒模型区别在于盒模型的宽高是否包含padding以及border。

## 七、CSS引入方式有哪些？link和@import的区别？
    内联、内嵌以及外链还有导入
    区别：同时加载前者无兼容性问题，后者CSS2.1以下浏览器不支持，link支持使用javascript改变样式，后者不可以。

## 八、CSS选择符有哪些？哪些属性可以继承？优先级算法如何计算？内联和important哪个优先级高？
    标签选择符、类选择符、id选择符
    文字大小、字体、字体颜色、行高等文本样式可以继承。
    important优先级最高。

## 九、前端页面有那三层构成，分别是什么？
    结构层html，表示层CSS，行为层js

## 十、主流浏览器的内核？
    ie（ie内核）、火狐（Gecko）、谷歌（webkit）,opera（Presto）