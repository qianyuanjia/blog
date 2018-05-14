---
title: CSS布局和定位
date: 2018-05-14 14:00:52
tags: css
---
### 1. CSS布局
css通常的布局方式只有两种，横向布局以及纵向布局，当遇到非线性布局时尽量通过套div的形式拆分成横向布局和纵向布局。
### 2. CSS块元素水平排列的方法
每个子元素左浮动，给父元素加上clearfix类，用于支撑起父元素的高度。
```
.clearfix::after{
    content:'';
    display:block;
    clear:both;
}
```
虽然可以通过给块元素添加display：inline-block的方式形成水平排列，但是不推荐这样做，你想它们之间万一有回车空格是不是处理起来很麻烦。
### 3. CSS定位
CSS定位，也就是position属性，它的值有四种，分别是static(默认)，absolute，relative,fixed以及sticky。切记relative定位不会使元素脱离文档流，这个经常考到。设置固定、绝对定位的时候，没有设置宽度的块元素经常会塌缩，使宽度自适应内容，这得根据需求妥善处理。
### 4. 如何用CSS画三角形
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
  <style>
    div{
      margin-bottom:20px;
    }
    .box{
      border:30px solid transparent;
      width:0;
      border-color: red blue green yellow;
    }

    /* 向上的三角形 */

    .top{
      border:30px solid transparent;
      width:0;
      border-bottom-color:green;
      
    }

    /* 向下的三角形 */

    .bottom{
      border:30px solid transparent;
      width:0;
      border-top-color:green;
      
    }

    /* 向左的三角形 */

    .left{
      border:30px solid transparent;
      width:0;
      border-left-color:green;
      
    }
    /* 向右的三角形 */

    .right{
      border:30px solid transparent;
      width:0;
      border-right-color:green;
      
    }
  </style>
</head>
<body>
  <div class="box"></div>
  <div class="top"></div>
  <div class="bottom"></div>
  <div class="left"></div>
  <div class="right"></div>
</body>
</html>
```
### 5. 为什么border-radius设置50%和100%没有区别？
我遇到这种情况，你应该也会碰到，当将一个宽高相等的div设置border-radius为50%时，它就显示为圆形，这是我们通过常用来做圆形边框的写法。但是当你设置为大于50%时，你就会惊奇的发现，他跟你想象中的不同，没有发生任何变化，还是显示一个圆形。关于这点，是因为当浏览器发现相邻角的半径和大于元素宽或者高时，就会同时缩放相邻角的半径，直到他们的半径和与宽或高相等。
举个栗子，当你设置左上角border-radius为60%，右上角也设为60%,它们的半径和为120%,大于宽度100%，那么浏览器渲染的时候就会同时缩小两个角度半径直到50%,宽度100%恰好可以容纳。