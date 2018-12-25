---
layout: "post"
title: "搭建 Github.io 个人博客"
subtitle: "使用 HEXO 框架教程"
description: "The tutorial of HEXO"
date: 2018-12-25 12:46:17
author: DIO
catalog: true
header-img: "HEXO-Tutorial.jpg"
tags: 
    - Windows
    - Tutorial
---

博客搭建有一段时间了,将安排好久的教程拎出来进行整理,亦是备忘,亦是教程  
愿取一瓢饮,留予后来人  

***  

# 基本知识  

既然是教程,面向的人群是基础较为薄弱的开发者,再次浅显地解释一下各个名词的含义  
* Github  
这个名词是个码农应该都不陌生,Github是个面向开源及私有软件项目的托管平台,那么它有什么用呢?  
很简单,比如你在学校实验室或者公司,代码没有敲完,回家要接着写,从前来说应该拿个U盘存着,现在不用了,放到Github上,下班前上传到Github的服务器,晚上回去下载到你家的电脑上接着写,Github就是帮你保管代码的地方,但是免费用户的代码都是公开的,所以Github也是一个汇聚了很多优秀开源软件的聚宝盆,各路优秀的开发者为我们带来了无数优秀的软件,当然,你也可以修改源码后提交给他们看,他们看了觉得不错就会采纳你的方案,全世界的网友都可以共同维护.  
* Github.io  
想做自己的博客的朋友们有两条路可以选择:  
一是自己买域名,自己租服务器,然后上传网站让大家从世界各地访问,如果你想用这种方式,那么这篇教程不适合你,请自行搜索 `WordPress`  
二是用一些托管的网站,使用别人送给你的服务器,那么这样一来域名就不可以自己定义了,就得跟着人家的规定走,比如本文的 `Github.io`  
这样的平台在国内有CSDN,简书等,国外就是Github为我们提供的 `Github.io`,用了它就可以不花钱拥有自己的博客,而且服务器很稳定,只不过代码完全开源和不能自定义域名  
说白了, `Github.io` 就是QQ空间高级版  
* 静态网页  
那么 `Github.io` 是怎么工作的呢?  
大多数市面上的商业网站都是动态网页,他们是包含数据库交互,JAVA编程地网站  
静态网页是相对于动态网页而言,是指没有后台数据库,不含程序和不可交互的网页.  
并不是说静态网页就不能动,动态网页就是活蹦乱跳的.  
`Github.io` 就是你把你想要给大家看的 **静态网页** 源码上传上去,它会自动解析,你输入给你分配好的域名,就可以访问了  
* HEXO  
顺理成章地,静态网页怎么制作呢?  
如果你是个Web高手,当然可以自己写  
如果你并不是,那么可以用好用的框架,市面上有很多免费的好用的框架,能帮助你自动生成静态网页,你只需要写文章,选好网页主题,一键生成就可以了  
Github原生支持 `jekyll`,除此之外,你还可以使用 `HEXO`,`Hugo` 等等  
我最终选择了 `HEXO`,至于为什么,往下看  
* 如果你坚定了要跟我一样用 `Github.io` 和 `HEXO` 搭建自己的博客,那么请准备好充分的自信和耐心,因为一下的过程,需要良好的动手能力和好的心态,如果没有好的心态,那么你可能需要一台结实的电脑  
请放心,本文尽可能少地敲命令行(笑,不过还是建议上网查查学会命令行,这是基础  

***  

# 准备工作  

下列工具是你必须要准备好的:  
* Github账号一个  
官方网站:https://github.com/join?source=experiment-header-dropdowns-home  
按提示注册就好  
* Node.js环境  
中文版下载页面:http://nodejs.cn/download/  
英文版下载界面:https://nodejs.org/en/download/  
{% asset_img NodeDownload.jpg NodeDownload %}  
* GitHub Desktop(或者Git,二选一)  
官方网站:https://desktop.github.com/  
{% asset_img GithubDesktopIntro.png GithubDesktopIntro %}  
* 文本编辑器(推荐Visual Studio Code,自己用着顺手就行)  
Visual Studio Code:https://code.visualstudio.com/  
* 浏览器一个(方便本地预览)  

# 环境搭建  

1. 打开Github官网并登录账号,新建一个仓库(repository)  
仓库名称不是随便起的,必须是 `用户名.GitHub.io`  
新建完成后,这个时候其实就可以输入https://用户名.github.io查看了
{% asset_img HEXOIntro.png HEXOIntro %}  