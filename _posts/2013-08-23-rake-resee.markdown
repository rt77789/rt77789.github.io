--- 
date: 2013-08-23 20:19:19
categories: "代码"
title: "代码高亮"
layout: post
---

Jekyll 代码高亮，需要修改_config.yml文件。修改相应内容：

``` ruby
pygments: true
markdown: redcarpet
redcarpet:
 	extensions: ["fenced_code_blocks", "autolink", "tabl
```

这样就完事了，够简单，够省事。

以下给出几个highlighted的代码snippets.

1. Perl code:
	
	``` perl
	#!/usr/bin/perl
	
	use XML::DOM;
	use DB_File;
	
	my @brr = ();
	print "equals\n" if @arr ~~ [];
	print "hello perl!\n";
	
	#read file
	open FP , "black.list.txt";
	$reg = <FP>;
	chomp $reg;
	close FP;
	#substitute
	$x = "aaabbb";
	$x =~ s/$reg/ /g;
	print "$x\n";
	```
	
2. C code:
	
	``` c
	#include "header.h"
	#include <stdio.h>
	
	void print_hello() {
		printf("hello\n");
	}
	
	void print_ok() {
		printf("ok\n");
	}
	```

3. C++ code:
	
	``` c++
	#include <iostream>
	#include <vector>
	
	using namespace std;
	
	void
	foo() {
		int sig;
	
		cout << "hello" << "" << endl;
		cout << "nice to meet u" << endl;
	}
	
	int main (int argc, char * const argv[]) {
	    // insert code here...
	    std::cout << "Hello, World!\n";
		foo();
	    return 0;
	}
	```

