# Markdown使用经验介绍  

## 本次讲座大纲
* Markdown格式简介
	- 标题
	- 列表
	- 内容
* 格式转换工具使用
	- pandoc
	- xelatex
	- unoconv
* 几个实用转换范例
	- md -> html, doc, pdf, ppt
	
![markdown logo](./figures/1.1.png)

## Markdown 目录结构
### 标题
* 一级/二级/三级/四级  
	# 一级标题  
	## 二级标题  
	### 三级标题  
	#### 四级标题  

* 还有一种写法  
	一级标题  
	=========  
	二级标题  
	---------  

### 列表
* 星号(实心圆点)
	- 减号(空心圆点)

## Markdown 正文内容
### 内容
* 黑体/斜体  
	这是一段 **黑体** 文字  
	这是一段 _斜体_ 文字
* 超链接  
	欢迎访问我的微博 <http://weibo.com/limingth>  
	请关注 [@亚嵌李明老师](http://weibo.com/limingth)
* 换行  
	可以在行尾输入2个空格  
	就可以实现换行功能

## Markdown 代码引用
### 代码
使用1或2个TAB可以引用大段的代码保持原有缩进格式 

	#include <stdio.h>

	int main(void)
	{
		printf("hello, world\n");
		return 0;
	}


## 格式转换工具使用
### 工具安装
* sudo apt-get install pandoc
* sudo apt-get install texlive
* sudo apt-get install xelatex
* sudo apt-get install unoconv

## 几个实用转换范例
### md -> html
	pandoc --ascii -f markdown -t html -o demo.html demo.md

### md -> doc
	pandoc demo.md -o demo.doc

### md -> doc -> pdf
	unoconv -f pdf demo.doc 

### md -> tex -> doc.pdf
	pandoc $(SRC) -o $(PREFIX)2doc.tex
	xelatex demo.doc.tex
demo.doc.tex 是自制doc tex模板文件
	
### md -> tex -> ppt.pdf
	pandoc -t beamer --slide-level 2 demo.md -o demo.tex
	xelatex demo.ppt.tex
demo.ppt.tex 是自制ppt tex模板文件

## 参考资料
* Pandoc语法详解 <http://johnmacfarlane.net/pandoc/demos.html>
* pandoc是什么 <http://yanping.me/cn/blog/2012/03/13/pandoc/>
* Markdown写作进阶 <http://www.yangzhiping.com/tech/pandoc.html>
* unoconv用法参数 <http://linux-wiki.cn/wiki/zh-hans/文档格式批量转换(doc,txt,pdf等)>
* happycasts.net latex学习视频课程 <http://www.happycasts.net/episodes/19?autoplay=true>
* beamer theme快速查看 <http://www.hartwork.org/beamer-theme-matrix/>

## Thanks
![Questions](./figures/1.2.jpg)

