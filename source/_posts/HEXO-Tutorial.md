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
Github原生支持 `Jekyll`,除此之外,你还可以使用 `HEXO`,`Hugo` 等等  
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

***  

# 环境搭建  

1. 打开Github官网并登录账号,新建一个仓库(repository)  
仓库名称不是随便起的,必须是 `用户名.GitHub.io`  
新建完成后,这个时候其实就可以输入 https://用户名.github.io 查看了,只不过页面是空的  
2. 安装Github Desktop  
默认是不让你选择安装位置的,默认安装位置是 C:\Users\用户名\AppData\Local\GitHubDesktop\  
你可以把它提取出来,然后在环境变量中添加软件中自带的git的地址就可以了 X:\*\GitHubDesktop\app-0.7.0\resources\app\git\cmd  
以后每次重装系统都需要添加此环境变量  
配置完成后运行 `cmd`,输入 `git version` 看到版本号说明配置成功  
然后将你的仓库Clone到本地  
{% asset_img GithubDesktopClone.png GithubDesktopClone %}  
3. 配置Node.JS  
解压缩刚才下好的Node.JS压缩包,在根目录创建 `node_global` 和 `node_cache` 两个文件夹  
添加环境变量 X:\*\NodeJS\node_global\ 和 X:\*\NodeJS\  
运行 `cmd`,输入 `node -v` 和 `npm -v` 看到版本号说明配置成功  
* 新建记事本文件,将下列代码粘贴进去并保存,文件名重命名为 `.npmrc`  
然后将这个文件复制到 `C:\Users\用户名\` 下面  

```
prefix=D:\node-v6.11.0-win-x64\node_global
cache=D:\node-v6.11.0-win-x64\node_cache
```

* 或者管理员方式运行 `cmd`,依次输入如下命令(自行更换文件路径)  

```
npm config set prefix "D:\node-v6.11.0-win-x64\node_global"
npm config set cache "D:\node-v6.11.0-win-x64\node_cache"
```

4. 配置HEXO  
管理员方式运行 `cmd`,输入如下命令  
`npm install hexo-cli -g`  
等待安装完成  
配置完成后输入 `hexo version` 看到版本号说明配置成功  

至此,环境搭建完成,下面开始正式生成我们的网页  

***  

# 制作网页  

## 安装HEXO依赖包  

1. 在纯英文路径新建一个文件夹  
按住 `Shift + 右键` 打开命令行(Win10是PowerShell,都一样)  
输入 `hexo init`  
等待进度结束之后就可以关闭窗口了,这个时候文件夹里会生成一大堆文件,不要惊慌,一个一个来看  
> node_modules:   是HEXO依赖包  
public:         是生成的静态网页们,现在它是空的,是因为我们还没有生成,待会儿我们配好各项设置生成之后这个文件夹就出现很多文件了,我们要的就是这个  
scaffolds:      命令生成文章等的模板  
source:         文章资源文件夹,文章内容,所用到的图片都在这里面  
themes:         主题文件夹,可以存放多个主题,想用哪个就选哪个,多放几个不冲突  
_config.yml:    整个博客重要的配置文件,细化设置都在这里面  
db.json:        source解析所得到的  
package.json:   项目所需模块项目的配置信息  

## 安装主题  

1. 选择主题  
进入 `HEXO` 官网  
https://hexo.io/zh-cn/  
{% asset_img HEXOIntro.png HEXOIntro %}  
点击 `主题`  
{% asset_img HEXOTheme.png HEXOTheme %}  
很多好看的主题!自己选一个!下载下来之后将文件夹放在 `themes` 文件夹下  
打开 `_config.yml` ,找到 `theme:`,把后面的名字改成下载的主题的文件夹的名字(或者看作者的文档说明)  

## 自定义网页其他设置  

1. 依旧是 `_config.yml` ,里面的配置都是以键值对形式出现的,各自的作用基本上都有注释标注出来了,自行查看,大胆修改  

## 新建文章  

1. 在博客目录新建终端,输入 `hexo new post 文章名字(英文)`  
这个时候在 `source\_posts` 文件夹下就有 `文章名字.md` 的文件  
看到这里有的朋友就懂了  
对, `HEXO` 原生支持 `Markdown`  

2. 至于 `Markdown` 怎么写,请参考下面文章  
http://www.markdown.cn/#editor  
https://sspai.com/post/25137  
http://younghz.github.io/Markdown/  
这里也有一些免费的在线编辑器  
https://dillinger.io/  
https://pandao.github.io/editor.md/  
http://md.barretlee.com/  
总之,写好文章保存即可,发挥你的创造力,人人都是灵感师  

## 生成网页  

1. 在博客目录新建终端,输入  
```
hexo clean      //清除旧生成文件,其实就是删除public文件夹和清除db.json文件里无用的内容
hexo generate   //也可简写成hexo g,这一步就是生成我们要的静态网页,这一步执行成功后去public文件夹下看就有很多网页了
hexo server     //也可简写成hexo s,这一步是用来本地预览我们做好的网站
```

2. `hexo server` 命令执行成功后,就可在浏览器中输入以下网址本地预览  
http://localhost:4000/  

> 这个时候来解释一下为什么用 HEXO 不用 Jekyll  
Jekyll 写的文章多的时候太慢了,HEXO 更快一点  
Jekyll 环境比较难搭建  
Jekyll 对 Markdown 支持得并不是很好  
但是 Github.io 原生支持 Jekyll,也就是说不需要我们自己生成(免去了hexo generate这一步,直接把源码粘贴到仓库目录下就会被自动解析,更省事儿)  
所以其中的利害各位自己权衡  

***  

# 上传  

> 激动人心的时刻马上就要来临!  

1. 刚才 `hexo generate` 执行成功过后,把博客目录下 `public` 文件夹里的东西复制出来  
粘贴到你创建的仓库的根目录  
大胆地粘贴  
这个时候Github Desktop会自动检测到你的文件有改动,这时填写 `Summary` 并 `Push` 就可以了!就像这样:  
{% asset_img GithubDesktopPush.png GithubDesktopPush %}  

2. 网速状况时好时坏,稍等一会儿输入你的博客网址(https://用户名.github.io)就能看到属于自己的网站了!  
至于详细的其他的各种配置,自行查阅[官方文档](https://hexo.io/zh-cn/docs/)是最佳选择,也可广泛借助互联网的力量  

***  

# 参考文献  
> HEXO https://hexo.io/zh-cn/docs/  

