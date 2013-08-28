--- 
layout: post
date: 2013-08-28 10:50:41
categories: "代码"
title: "Lab502 Beamer Template"
---

因为需要给实验室的人做报告，索性就浏览了一下beamer，然后从别人的模板基础上修改，
为实验室做了一个简陋的beamer的[模板][ustc_beamer]。
> 注意，推荐把.sty文件以及依赖的图片logo都放在latex/beamer/themes/目录，方便长期使用。   
> Mac os X对应的路径：/Users/rt77789/Library/texmf/tex/latex/beamer/themes/   
> 对于不存在的文件夹，手动建立即可。

1. Latex beamer的整体结构: {% highlight tex %}\documentclass[pdf]{beamer} 
	\mode<presentation>{}
	%% preamble 
	\title{The title} 
	\subtitle{The subtitle} 
	\author{your name}
	\begin{document}
	\begin{frame} \titlepage
	\end{frame}
	%% normal frame \begin{frame}{Frame title}
	The body of the frame. \end{frame}
	\end{document}{% endhighlight %}
2. Title page:
	\titlepage 命令是用来生成title页面的. title页面主要包含如下内容：{% highlight tex %}\title{Latex beamer Template for Lab502@USTC}
	\subtitle{Beauty is truth, truth beauty}
	% Not support Chinese now.
	\author{Yi Zheng}
	\date{\today}
	\institute{\url{email address}\\
	\url{http://morebug.com}} {% endhighlight %}

3. Frame page:
	其余每个slides的页面都是用frame来建立的，样例如下：{% highlight tex %}\section{Introduction}
	\begin{frame}
	\frametitle{A Frame}
	\framesubtitle{Bullet points}
	\begin{itemize}
	\item First thing
	\item Second thing
	\item Third thing
	\end{itemize}
	\end{frame}{% endhighlight %}
	\frametitle 和 \framesubtitle是用来指明每一页slide的标题和副标题，itermize环境中的每个item和powerpoint是类似的。

4. Figure, Table and Theroem: 
	图片，表格和定理的插入方式基本上与latex的其他class类似。

5. 页面内容的多页显示：
	即通过多页面渐进显示来模拟powerpoint的动态展示效果。可以直接通过\pause命令来完成这个功能。
	或者通过指定item的序号更加显示的指明显示方式。{% highlight tex %}\begin{itemize}
		\item Hello, World! \pause 
		\item Hello, Mars! \pause 
		\item Hello, Alpha Centauri!
	\end{itemize}{% endhighlight %}
	通过item指定页面序号的方式完成同样的显示：{% highlight tex %}\begin{itemize}
		\item<2-> Hello, World! 
		\item<3-> Hello, Mars! 
		\item<4-> Hello, Alpha Centauri!
	\end{itemize}{% endhighlight %}
	显然，第二个可读性更好，更直观。

6. \uncover 命令在指定页面显示内容：{% highlight tex %}\begin{enumerate}[A]
		\item<2-5> James Madison 
		\item<3-5> Harry Truman 
		\item<4-> \color<6>[rgb]{0,0.6,0}Abraham Lincoln 
		\item<5-5> Calvin Coolidge
	\end{enumerate}
	%%% 
	\uncover<1-5>{Hints:}\\ 
	\uncover<2-5>{James Madison ate broccoli.}\\ 
	\uncover<3-5>{Harry Truman drank milk.}\\ 
	\uncover<4-5>{Abe Lincoln raised bees.}\\ 
	\uncover<5-5>{And Cal Coolidge grew silk.}\\{% endhighlight %}

7. 多列显示和块: {% highlight tex %}\begin{columns}
	\column{0.5\textwidth}
		\begin{block}<2->{Observation 1}
			Simmons Hall is composed of metal and concrete. 
		\end{block}
	\column{0.5\textwidth}
		\begin{block}<3->{Observation 2} 
			Simmons Dormitory is composed of brick.
		\end{block}
	\end{columns}{% endhighlight %}	

这里有两个非常好的教程，都是对应代码的样例：[tutorial 1] [], [tutorial 2] []。
了解如上内容基本上就可以开始写自己的slides了，如果需要更进一步的学习高阶的内容，beamer的文档和其他模板都是可以参考的材料。
[ustc_beamer]: https://github.com/rt77789/beamer-themes "Beamer Template of lab502@ustc."
[tutorial 1]: http://web.mit.edu/rsi/www/pdfs/beamer-tutorial.pdf "Good tutorial with samples."
[tutorial 2]: http://www.math.utah.edu/~smith/AmberSmith_GSAC_Beamer.pdf "Another tutorial."
