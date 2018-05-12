---
title: 什么是可替换元素
date: 2018-05-12 16:54:59
tags: html
---
### MDN的解释
CSS 里，可替换元素（replaced element）的展现不是由CSS来控制的。这些元素是一类 外观渲染独立于CSS的 外部对象。 典型的可替换元素有 &lt;img&gt;、 &lt;object&gt;、&lt;vedio&gt; 和 表单元素，如&lt;textarea&gt;、 &lt;input&gt; 。 某些元素只在一些特殊情况下表现为可替换元素，例如 &lt;audio&gt; 和 &lt;canvas&gt; 。 通过 CSS content 属性来插入的对象 被称作 匿名可替换元素（anonymous replaced elements）。这个解释看的我一脸懵逼，所以还是自己找资料来说明一下。
### 我的理解
当我们使用div,span等元素时，它们的具体内容是由元素标签标签之间所添加的内容决定的。当我们使用img时，它的内容是由src指向的资源决定；当我们使用input时，它所表现的形式是由type以及value属性决定的，现在你差不多理解了吧，所谓可替换元素是指浏览器可以根据标签的类型以及属性来呈现不同的表现形式，而非替换元素是指它们的内容是直接写在标签之间的，所见即所得。 &lt;img&gt;、&lt;input&gt;、&lt;textarea&gt;、&lt;select&gt;、&lt;object&gt;等元素是可替换元素，可替换元素一般具有src或type属性，可以指向不同的类型和资源。