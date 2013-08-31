--- 
categories: "技术"
title: "在emacs中用R"
layout: post
date: 2013-08-31 23:31:47
---

我经常需要写一些R的代码，至于为什么用R这么一门非主流语言，暂且不表，当前我只记录一下怎么在emacs中使用ess plugin方便写代码以及执行。

1. 安装ess plugin：
   最简单的安装方式就是在emacs中安装。调用 M - x package-install RET，然后输入ess即可。或者，你也可以手动下载[ess package] [ess]，然后解压缩到指定的文件夹。

2. 配置ess plugin：
   打开配置文件~/.emacs.d/init.el，加入如下代码：{% highlight common-lisp %}(add-to-list 'load-path "ess所在目录")
   (require 'ess-site) {% endhighlight %}

3. 执行代码：
   在打开的R源码文件对应的buffer中，C - c C - n 命令执行光标当前行的代码，
   C - c C - b 命令执行当前buffer的代码。更详细的命令参加ess文档。

我希望明年这个时候，我依然能够坚持使用emacs，并且很高兴我能一路坚持下来。

References：  

1. [jekyll.math.byuh.edu](http://jekyll.math.byuh.edu/other/howto/R/RE.shtml)
2. [blog.crackcell.com](http://blog.crackcell.com/posts/2012/04/03/setup_emacs_for_r.html)
3. [feime.net](http://www.feime.net/2011/emacs%E4%B8%8B%E4%BD%BF%E7%94%A8r%E7%9A%84%E5%88%A9%E5%99%A8/)

[ess]: http://ess.r-project.org/index.php?Section=download "ess package"
