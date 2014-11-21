---
layout: post
title: "基于 GitHub 和 Jekyll 搭建博客"
description: "test"
category: 技术杂谈
tags: [基础环境]
---
{% include JB/setup %}

这两天基于GitHub使用Jekyll搭建了一个个人Blog， 虽然网站上已经有很多文章来讲述搭建的步骤，但是我在搭建的过程中还是遇到了一些问题，所以还是希望写一篇博客来记录一下我的搭建过程和遇到的问题。

##背景介绍

GitHub是一个代码托管网站， 其提供了一项服务——GitHub pages 利用这个功能，可以为我们的项目建立网站，
当然，这也意味着我们可以通过 GitHub Pages 建立自己的网站。

Jekyll是一个简单的，针对博客设计的静态网站生成器。使用 GitHub和Jekyll，我们可以打造自己的独立博客。

##简单的博客搭建

假设有一个GitHub账户：ThreeMonkey。  

建立博客有两种方式：

  + 创建ThreeMonkey.github.com的repositories，在master分支里面加入自己的博客内容  
  + 创建任意repositories（假设为test），新建gh-pages分支，在里面加入自己的博客内容

如何一步步为自己的博客添加内容（html文件），请看[《搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门 - 阮一峰的网络日志》](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)，这篇博客很好的讲述了用Jekyll来建blog的基础知识。

如果不想自己一步步编写html文件，我们可以用Jekyll来自动生成， 因此我们需要首先按照Jekyll。 按照Jekyll还有一个好处就是可以在本地调试，调试好后，再将其发布到GitHub。

##Jekyll的安装

Jekyll是基于Ruby的，因此安装Jekyll需要先安装Ruby。可以到[官网](http://rubyinstaller.org/downloads/)下载相应的安装包，安装完之后把ruby添加到path环境变量中。

下载安装Development Kit，[下载地址](http://cdn.rubyinstaller.org/archives/devkits/DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe)

安装完成之后，进入DevKit的安装目录， 运行
	
	ruby dk.rb init
	ruby dk.rb install

最后就是安装jekyll了，jekyll并没有提供安装包之类的，需要通过ruby的包管理器进行安装（这东西有点类似于apt-get和yum或者archlinux的包管理），直接执行

	gem install jekyll

安装过程中需要的东西会自动联网下载，所以请确保在可以联网的情况下安装它。安装后把D:\ProgramFiles\Ruby21-x64\lib\ruby\gems\2.1.0\gems\jekyll-2.5.1添加到path环境变量。

至此，Jekyll安装完毕

##用Jekyll命令生成博客的基本内容
运行命令

	jekyll new project_name

就可以在当前目录下建立一个project_name的工程，里面就是基本博客的所有文件。

进入project_name目录，运行
	
	jekyll server

就可以启动本地Jekyll服务器， 在浏览器中输入：http://localhost:4000 可以本地查看生产的博客。

##使用 jekyll-bootstrap 框架优化博客

使用上面的方法可以搭建简单的博客，但是博客却没有分类和评论的功能。当然我们也可以自己修改HTML文件来添加分类的功能，添加disqus插件来添加评论的功能。更方便的，可以使用Jekyll-bootstrap来添加这些功能。

相关的使用说明，[请看这里](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)



