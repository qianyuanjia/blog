---
title: CSS布局技巧总结
date: 2018-05-14 20:02:46
tags: css
---
### 1. 左右布局
左右布局实现方法有很多，常用的就是给块元素添加浮动，而父元素需要清除浮动，不然会高度塌缩。常见的左右布局实现方法如下，[效果链接](http://js.jirengu.com/dijamacamo/3/)
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
  <style>
    .clearfix::after{
      content:'';
      display:block;
      clear:both;
    }
    .left {
      width:25%;
      height:600px;
      background: green;
      float:left;
    }
    .right{
      width:75%;
      height:600px;
      background: blue;
      float:left;
    }
  </style>
</head>
<body>
  <div class="box clearfix">
    <div class="left">侧边栏</div>
    <div class="right">主体区</div>
  </div>
</body>
</html>
```
### 2. 左中右布局
可以使用浮动的方式实现，也可以用弹性盒布局的方式实现，代码如下,[展示链接](http://js.jirengu.com/coxux/2/)
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
  <style>
     .clearfix::after{
      content: '';
      display: block;
      clear: both;
    }
    .box{
      display:flex;
    }
    .left,.right,.mid{
      float: left;
      flex:1;
      height:600px;
    }
    .left{
      background: green;
    }
    .mid{
      background: red;
    }
    .right{
      background: blue;
    }
  </style>
</head>
<body>
<div class="box clearfix">
  <div class="left">左边</div>
  <div class="mid">中部</div>
  <div class="right">右边</div>
</div>
</body>
</html>
```
### 3. 水平居中的方法
- 使块元素中的内联元素居中使用text-align:center就可以实现，因此如果在不要影响其他的情况下，将块元素中的元素的display设为inline或inline-block，然后给块元素加上text-align:center就可以了。比如：
```
<div style="text-align:center;">
    <span>hello</span>
    <p style="display:inline">how are you</p> 
    <!--或设置为inline-block,如果需要设置宽高的话-->
</div>
```
- 使块元素居中的方法，给块元素设置宽度，之后左右margin设为auto就可以啦。

### 4. 垂直居中的方法
- 内联元素垂直居中可以通过line-height搭配上下padding实现，只要上下padding+行高的总和与父元素高度相等，就能实现垂直居中。比如：
```
<div style="height:30px;line-height:20px;">
    <span style="font-size:16px;padding:5px 0;">hello</span>
</div>
```
- 块元素实现水平垂直居中可以通过绝对定位实现,然后top和left各回退自身宽高的一半。比如：
```
<style>
    .out{
        width:400px;
        height:400px;
        background:red;
        position:relative;
    }
    .in{
        width:200px;
        height:200px;
        position:absolute;
        top:50%;
        left:50%;
        margin-top:-100px;
        margin-left:-100px;
    }
</style>
<div class="out">
    <div class="in"></div>
</div>
```

### 5. 其他注意点
当为元素设置display：inline-block时，最好搭配vertical-align:top一起设置，因为有时会出现底部空白间距的bug。能不对元素设置宽高就不要设置，宽高是很多bug的源头，尽量提高内部文档流元素宽高实现自适应。


