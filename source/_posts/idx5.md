---
title: HTTP协议
date: 2018-05-11 23:39:00
tags: http
---
## HTTP 请求包括哪些部分，如何用Chrome开发者工具查看 HTTP 请求内容
1. http请求格式：
   - 第一部分
   如：GET / HTTP/1.1  
   第一个部分包含动作（GET或POST）,请求路径，必须以'/'开头，包含参数但不包含锚点，以及最后的协议及版本
   - 第二部分
   是发送给服务器的各种信息，以'键: 值'的格式发送，如Host: www.baidu.com等，可以有多个这样的键值对。
   特别说明：Content-Type: Application/x-www-form-urlencoded
   Application是应用数据的意思，x-表示尚不列入标准规范的规范的格式，www是万维网的意思，form是表单的意思，而urlencoded表示中文用特殊方式编码。
   - 第三部分
     回车空行，用于分隔第四部分的请求数据
   - 第四部分
     是请求时发送的数据，一般只有以'POST'方式请求是才发送数据。
   - Chrome开发者工具查看 HTTP 请求内容
     打开开发者工具，点击Network选项卡，再刷新页面时会将所有的请求显示出来。点击要查看的某个请求，点击其中的Request Header，再点view source可以以原始请求格式显示。
## HTTP 响应包括哪些部分，如何用Chrome开发者工具查看 HTTP 响应内容
2. http响应格式：
   - 第一部分
     如：HTTP/1.1 200 OK
     第一部分包含协议及它的版本，http状态码以及状态码解释
   - 第二部分
     是服务器发送给浏览器的各种信息，以'键: 值'的格式发送，如Content-Type: text/html等，可以有多个这样的键值对。
   - 第三部分
     回车空行，用于分隔第四部分的响应数据
   - 第四部分
     是响应返回的数据，一般是html页面内容或css以及其他外部文件内容。
   - Chrome开发者工具查看 HTTP 请求内容
     打开开发者工具，点击Network选项卡，再刷新页面时会将所有的请求显示出来。点击要查看的某个请求，点击其中的Response Header，再点view source可以以原始请求格式显示。
3. 如何使用 curl 命令
   curl命令使用的形式和参数：
   ```
   curl -s -v -H 'xxx:yyy' -- 'http://www.baidu.com'
   ```
   -s 表示不显示进度条，-v表示提供更多的输出信息，交互性更好，-H表示设置请求头信息，默认以GET方式请求，若以POST方式请求，使用
   ```
   curl -X POST [-d '12345'] -s -v -H 'xxx:yyy' -- 'http://www.baidu.com'
   ```
   -d表示请求时发送的数据，可以不写。