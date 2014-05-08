---
layout: post
title: "腾讯QQ截图功能BUG描述"
description: ""
category: bugs
tags: [bugs]
---

忍了这个BUG好久，双11的时候本来打算向必应词典反映BUG的，结果发现BUG来自腾讯，ORZ。
##系统环境
> OS：WIN 7 64bit  
> QQ: 2013SP4  
> 必应词典: 2.4.0  ,划译开/关热键:无。  
> Gmail:gmail.com版本  

##BUG描述

* 关闭必应词典的划译功能，使用QQ截图，确定截图区域之后，双击截图区域，获得截图，粘帖(Ctrl + V)到QQ聊天输入框，一切正常。

* 开启必应词典的划译功能，使用QQ截图，确定截图区域之后，双击截图区域，获得截图，粘帖(Ctrl + V)到QQ聊天输入框，一块和截图区域大小相等的黑块，如图
  ![black.jpg](/assets/images/bugs/black.jpg)

* 开启必应词典的划译功能，使用QQ截图，确定截图区域之后，右键-完成截图，获得截图，粘帖(Ctrl + V)到QQ聊天输入框，一切正常。

* QQ聊天窗口为当前活动进程时，无论开启/关闭必应词典的划译功能，使用QQ截图，确定截图区域之后，右键-完成截图，获得截图，粘帖(Ctrl + V)到QQ聊天输入框，一切正常。

##BUG发现

* 最初以为是必应词典的划译会截取双击事件，想到在网页双击一个单词区域，会有阴影区域扩展至该单词，如图 ![doubleclick.jpg](/assets/images/bugs/doubleclick.jpg)

* 当时以为必应词典预留了双击事件，将来将"划译"升级成更加强大的"双击译"，于是打开gmail给必应词典发邮件。如图: 
  ![email.png](/assets/images/bugs/email.png)

* 此时在Gmail中，显示的图片是正常的。我还以为此事QQ截图功能正常了，却发现同样的方法截图，粘帖到QQ输入框中是黑块，粘帖到Gmail中是正常的。顿时，我好像明白了什么。

##记录这个BUG

软件有各种各样的BUG，毫不奇怪，比如这种[量子力学BUG](http://ruby-china.org/topics/15510)，其中又有[地板BUG](http://www.linuxeden.com/html/itnews/20110117/106376.html)，QQ的这个，发现的过程挺有趣的。同时也警示下自己BUG一定会有原因的，曾经遇到一个BUG，无论如何调试都没发现异常，弄了一个礼拜，实在不行了，交给另外一人帮忙修复，那人卷起袖子之后问我"BUG呢？"然后就再也无法重现了，然后，就放过了，不知道哪天还会出现，大概是[Heisenbug](http://en.wikipedia.org/wiki/Heisenbug)吧。

##吐槽下WIN8
WIN7下切换输入法，是可以自定义快捷键的，拼音Ctrl + 0，日语Ctrl + 9。到了WIN8及WIN8.1里面，就只能Ctrl + shift + 数字键了。快速输入的时候Ctrl + shift不怎么好按，远不如左手小拇指Ctrl，右手数字键方便。为此之下换回了WIN7，WIN8那个求激活的水印我倒是无所谓的看了很久。




