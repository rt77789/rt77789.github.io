--- 
title: "Emacs之配置"
categories: "技术"
layout: post
date: 2013-08-29 21:45:59
---

Emacs的配置真特么是极其复杂，并且问题频出。

我遵循某位大牛的指导意见，copy大牛的配置文件，不管三七二十一，拿来用。
但是，问题是拿来用的时候有问题啊，各种error啊。目前姑且算是可以用了把。

说说具体流程：

1. 选择emacs.d/模板：
   我选择的是[purcell] []的模板，实际上这个模板是最好的，后来我才发现直接拿过来就可以直接用，基本没有任何问题出现。

2. 复制模板到本地~/.emacs.d/目录下：
   我用的是mac os 10.6.8，对应linux的路径好像是~/.emacs/。

3. 启动emcas：
   启动之后就是自动的download各种plugins，然后完成初始化。

其实，如果没什么问题，这就完事了。但是，如果你用emacs --debug-init启动的话，其中可能出现各种的Debugger error。
如果你用的是emacs 24+，那么应该就没什么问题，否则可能会出现各种让人抓狂的messages。

另外一点，因为我真的很不适应emacs的按键，所以我也按照大牛的指导意见，选择了evil-mode来进行编辑。
这个比较简单，如果安装了evil插件，直接M - x evil-mode即可。否则，选择M - x package-install RET evil RET，进行安装。

再有一点，[purcell] []的模板默认是不显示行号的，之前用vim我已经习惯了显示行号，所以在init.el脚本里加上如下两句代码： {% highlight common-lisp %}(global-linum-mode 1) ; Always show line numbers
(setq linum-format "%d") ; set format{% endhighlight %}
至此，基本上就可以用了，如果你不喜欢[purcell] []默认的color themes，可以输入：M - x customize-theme RET 来选择你喜欢的theme。

大概内容就如此了，真是把我折腾的可以，以后尽量用emacs写代码，像latex这种东西，确实是非常方便。

ps: M - x 表示alt键加x，RET表示回车/Enter。


![图片](/images/2013-08-29-emacs-config_1.png) 

<center>Figure 1, Snapshot of this post.</center>

[purcell]: https://github.com/purcell/emacs.d "purcell's emacs.d configuration"
