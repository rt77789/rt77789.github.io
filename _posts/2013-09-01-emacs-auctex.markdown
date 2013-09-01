--- 
date: 2013-09-01 14:22:29
title: "配置emacs-auctex"
categories: "技术"
layout: post
---

如果打算用latex写论文写slides，那么auctex是非常好的一个工具。

安装这个auctex依然很简单，调用 M - x package-install RET，然后输入auctex即可。或者，你也可以手动下载auctex的压缩包，然后解压到.emacs.d/的相应文件夹中。

接下来，需要对auctex进行配置，因为我习惯用pdflatex命令来生成pdf文件，所以相应的修改init.el文件，添加如下内容：{% highlight common-lisp %}; Config latex mode.
(add-hook 'LaTeX-mode-hook 
          (lambda () 
            (turn-on-reftex) 
            (setq reftex-plug-into-AUCTeX t))) 
;; Set output format.
(setq TeX-PDF-mode t) 

;; Set viewer.
(setq TeX-view-program-selection 
      '(((output-dvi style-pstricks) 
         "dvips and PDF Viewer") 
        (output-dvi "PDF Viewer") 
        (output-pdf "PDF Viewer") 
        (output-html "Safari"))) 
(setq TeX-view-program-list 
      '(("dvips and PDF Viewer" "%(o?)dvips %d -o && open %f") 
        ("PDF Viewer" "open %o")
        ("Safari" "open %o"))) {% endhighlight %}

需要注意的是，网上一些帖子给出的配置有这么两行代码：{% highlight common-lisp %}(load "auctex.el" nil t t)
(load "preview-latex.el" nil t t){% endhighlight %}

如果你是使用 M - x package-install RET 安装，那么这两行配置是不需要的，只有手动下载解压auctex压缩包的情况下，这两行配置才是需要的 ([参见] [1])。

对应的命令：     
1. 编译：C - c C - c Latex RET     
2. View：C - c C - v 或者 C - c C - c View RET     
3. 其他诸如Bibtex、Print等命令也可用 C - c C - c Command RET 来调用

References：      
1. [AUCTeX](http://www.emacswiki.org/emacs/AUCTeX)    
2. [lists.gun.org](https://lists.gnu.org/archive/html/auctex/2012-11/msg00039.html)   

[1]: https://lists.gnu.org/archive/html/auctex/2012-11/msg00039.html "auctex config issue"
