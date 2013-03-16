
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

![How to use markdown](./figures/1.1.png)

## Markdown 格式简介
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
* 星号
	- 减号

## 
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

##
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
### md->html
* pandoc --ascii -f markdown -t html -o demo.html demo.md

### md->doc
* pandoc demo.md -o demo.doc

### md->doc->pdf
* unoconv -f pdf demo.doc 

### md->ppt->pdf
* pandoc -t beamer --slide-level 2 demo.md -o demo.tex
* xelatex main.tex

## 参考资料
* http://johnmacfarlane.net/pandoc/demos.html
* http://yanping.me/cn/blog/2012/03/13/pandoc/
* http://www.yangzhiping.com/tech/pandoc.html
* http://linux-wiki.cn/wiki/zh-hans/文档格式批量转换(doc,txt,pdf等)

## Thanks
![Questions](./figures/1.2.jpg)

