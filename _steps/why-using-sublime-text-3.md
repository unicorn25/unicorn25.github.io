---
layout: post
title: 为什么选择Sublime Text 3作为修仙方向
date: 2017-09-21
author: Unicorn25
---
  
# 1 使用理由

## 1.1 辅助查找

goto anything功能，支持模糊匹配，与重量级IDE（如Visual Studio）相比，查找速度不是一个量级的。

* 通过关键字查文本
* 通过路径配置查文件并打开
* 模糊查找

举例：

任务描述：通过 ***xml*** 或 ***xdb*** 文件中配置的 ***path*** 查找对应文件并打开。   
操作：Ctrl + C -- Ctrl + P -- Ctrl + V -- ↑/↓ -- Enter

## 1.2 辅助显示

只要能找到对应的支持插件，就能够对各种语言和协议的文本进行高亮显示。尤其对于个人的各种不常用格式文本，可以集中用ST3浏览编辑。

举例：

任务描述：使 ***xml*** 文件语法高亮    
操作：~ctrl~ + ~shift~ + ~p~  -- Set Syntax: XML(模糊匹配ssx就看到) -- ~enter~

## 1.3 辅助编辑（依赖插件），可依赖第三方进化

尤其是对于一些前端语言的快捷生成和编辑支持，确实令人震惊。



举例：

任务描述：安装了 ***Emmet***之后，编写一些常用的前端代码。    
操作：
自动生成标签：
输入：unicorn
按快捷键：ctrl+e
得到：
<unicorn></unicorn>

输入：unicorn.chouma
按快捷键：ctrl+e
得到：
<unicorn class="chouma"></unicorn>

输入：unicorn+sdj
按快捷键：ctrl+e
得到：
<unicorn></unicorn>
<sdj></sdj>

## 1.4 别具匠心的快捷键为超高度的键盘化操作提供支持，使效率天花板显著高于常用的IDE。

* 开启强大的命令模式：
Ctrl + Shift + P

* 多游标：
双击一个词，Ctrl + D
。。。
。。。

* 有时我们需要对一片区域的所有行进行同时编辑，Ctrl+Shift+L
可以将当前选中区域打散，然后进行同时编辑：
![SublimeText](http://upload-images.jianshu.io/upload_images/1281738-2e848ba30f101d5b.gif?imageMogr2/auto-orient/strip)

* 有打散自然就有合并，Ctrl + J可以把当前选中区域合并为一行：
![SublimeText](http://upload-images.jianshu.io/upload_images/1281738-27a0fbf1b8810691.gif?imageMogr2/auto-orient/strip)

* 在Ctrl + P匹配到文件后，我们可以进行后续输入以跳转到更精确的位置：

\@ 符号跳转：
输入@symbol
跳转到symbol符号所在的位置

\# 关键字跳转：
输入#keyword
跳转到keyword所在的位置

\: 行号跳转：
输入:12
跳转到文件的第12行。

* 在当前行下面新增一行然后跳至该行，Ctrl + Enter；在当前行上面增加一行并跳至该行，Ctrl + Shift + Enter。

* Sublime Text的查找有不同的模式：Alt + C
切换大小写敏感（Case-sensitive）模式，Alt + W切换整字匹配（Whole matching）模式，除此之外Sublime Text还支持在选中范围内搜索（Search in selection），这个功能没有对应的快捷键，但可以通过以下配置项自动开启。
“auto_find_in_selection”: true

这样之后在选中文本的状态下范围内搜索就会自动开启，配合这个功能，局部重命名（Local Renaming）变的非常方便：

![SublimeText](http://upload-images.jianshu.io/upload_images/1281738-e190b121a8c3139e.gif?imageMogr2/auto-orient/strip)

* 进行逐词移动，Ctrl + ←/→；逐词选择，Ctrl + Shift + ←/→。

![SublimeText](http://upload-images.jianshu.io/upload_images/1281738-173714c2dcf17d17.gif?imageMogr2/auto-orient/strip)

* 移动当前显示区域，Ctrl + ↑/↓；移动当前行，Ctrl + Shift + ↑/↓。

![SublimeText](http://upload-images.jianshu.io/upload_images/1281738-4d7ad1edd8f4d4d6.gif?imageMogr2/auto-orient/strip)

* 在当前窗口创建一个新标签，Ctrl + N；关闭当前标签，Ctrl + W；恢复刚刚关闭的标签，Ctrl + Shift + T。

* 编辑代码时经常需要多窗口显示，所以分屏很重要。
左右分2屏，Alt + Shift + 2；上下分2屏，Alt + Shift + 8；分4屏，Alt + Shift + 5。

* 向左缩进(等同于将一块选中Shift+Tab)，Ctrl + [；向右缩进(等同于将一块选中后Tab键)，
Ctrl + ]（Ctr+[ 和 Ctr+] 针对一块连续内容使用，无需选中）。此外Ctrl + Shift + V可以以当前缩进粘贴代码（非常实用）。


相关文章：
[Sublime Text3 快捷键汇总及设置快捷键配置环境变量](http://blog.csdn.net/moyan_min/article/details/11530751)   
[如何优雅地使用Sublime Text--Sublime不可不知的实用技巧](https://www.jeffjade.com/2015/12/15/2015-04-17-toss-sublime-text/#five)   

## 1.5 灵活的插件装卸机制能使IDE功能最大限度的与使用场景匹配，提高响应速度。

插件化，灵活性，可扩展性
配置文本化，可视，易读
（有时间再来举例）

---

# 2 不适用场合

查找函数定义和显示函数引用数不方便。

注意：
在最新的3124版本中，Sublime已经注入了函数Show Definition
功能--which will show where a symbol is defined when hovering over it with the mouse；具体可参见[Sublime Text 3 Build 3124](http://www.sublimetext.com/blog/articles/sublime-text-3-build-3124)。
（具体怎么用，好不好用，还需要挖掘一下）

---

# 3 如何浏览插件

[插件导航页](https://packagecontrol.io/browse)

### 常用的插件：

* ***AdvancedNewFile***
* ***Emmet***
* ***SideBar***
* ***ConvertToUTF8***
* ***ColorPicker***

插件介绍：
[Sublime Text3插件：增强篇](http://www.jianshu.com/p/5905f927d01b)   
[20个强大的SublimeText插件](http://www.open-open.com/news/view/26d731)   
[如何优雅地使用Sublime Text--Sublime Text 3插件推荐](https://www.jeffjade.com/2015/12/15/2015-04-17-toss-sublime-text/?jianshu#three)   

[Emmet](http://www.qianxingzhem.com/post-1940.html)   

---

# 4 如何安装插件

Ctrl + Shift + P -- package control: install package（模糊查找输入pci）

在弹出的输入框中，模糊查找对应的插件名，然后安装

---

# 5 相关网站与参考文章

[官网](http://www.sublimetext.com/blog/)   
[注册码](http://www.jianshu.com/p/04e1b65dd2c0)   
[插件安装教程，插件介绍](https://packagecontrol.io/installation)   

[如何优雅地使用Sublime Text](https://www.jeffjade.com/2015/12/15/2015-04-17-toss-sublime-text/)   