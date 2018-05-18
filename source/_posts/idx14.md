---
title: 用Canvas实现图片裁剪和保存
date: 2018-05-18 13:31:43
tags: js练习案例
---
### 先来简单看下效果
![](clip.gif)
### 1. html结构内容
html内容十分简单，我们需要一个input:file按钮用于上传本地图片，一个连接按钮用于图片保存，一个div用作选择遮罩，一个img用于预览裁剪结果，由于内容比较简单，所以这部分放一下代码：
```
<style>
    #mark{
        background-color: rgba(255,255,255,0.5);
        position: absolute;
        display: none;
        cursor: move;
    }
    #show{
        display: none;
        margin-left: 20px;
    }
</style>
<body>
    <input type="file" name="" id="pic">
    <a href="" id="save">下载裁剪图</a>
    <br>
    <div id="mark"></div>
    <img src="" alt="" id="show">
</body>
```
### 2. 如何让选中的图片显示在页面上？
首先上传的图片存储于input:file对象的files属性中，并以数组的方式存储。接下来我们要将图片读取成文件对象，这部分需要用到FileReader API,通过FileReader对象的readAsDataURL方法可以读取input:file里的文件列表里面的图片，并将图片转换为base64格式。当FileReader对象将图片加载完之后，触发它的onload的事件，可以打印下事件对象函数的具体内容，发现其ev.target.result就是图片转成base64的一长串URI，通过创建一个Image对象并且将这串URI作为Image对象的src，这时，我们已经将上传的图片保存在内存中了，最后可以通过Canvas的上下文内容对象的drawImage方法，将Image对象画在画布中，图片就展示到页面上啦！
### 3. 如何下载和保存图片？
通过下面这个方法就搞定啦，这个方法需要两个参数，一个是图片的base64格式内容，另一个是图片名称（自定义）。这个方法看不懂没关系，把它当成一个通用的API就好啦。
```
    function saveFile(data,filename){
           var save_link=document.createElementNS('http://www.w3.org/1999/xhtml', 'a');
           save_link.href=data;
           save_link.download=filename;
           var event=document.createEvent('MouseEvents');
           event.initMouseEvent('click',true,false,window,0,0,0,0,0,false,false,false,false,0,null);
           save_link.dispatchEvent(event);
      };
```
### 4. 我已将js代码上传到github中，有兴趣的可以访问
[详细js代码](https://github.com/qianyuanjia/jsexcise/blob/master/js/haizei.js)