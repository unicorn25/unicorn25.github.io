---
layout: post
title: 为什么选择Sublime Text 3作为修仙方向
date: 2017-09-21
---
  
# 1 使用理由

## 1.1 辅助查找

goto anything功能，支持模糊匹配，与重量级IDE（如Visual Studio）相比，查找速度不是一个量级的。

* 通过关键字查文本
* 通过路径配置查文件并打开
* 模糊查找

举例：

任务描述：通过 ***xml*** 或 ***xdb*** 文件中配置的 ***path*** 查找对应文件并打开。   
操作：~ctrl~ + ~c~ -- ~ctrl~ + ~p~ -- ~ctrl~ + ~v~ -- ~down~ ~up~ 选择 -- ~enter~

## 1.2 辅助显示

只要能找到对应的支持插件，就能够对各种语言和协议的文本进行高亮显示。尤其对于个人的各种不常用格式文本，可以集中用st浏览编辑。

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

强大的命令模式：
~ctrl~ + ~shift~ + ~p~

取词：
~ctrl~ + ~shift~ + ~right~

多游标：
双击一个词，~ctrl~ + ~d~

添加新行：
~ctrl~ + ~enter~
~ctrl~ + ~shift~ + ~enter~

相关文章：
[Sublime Text3 快捷键汇总及设置快捷键配置环境变量](http://blog.csdn.net/moyan_min/article/details/11530751)

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

~ctrl~ + ~shift~ + ~p~ -- package control: install package（模糊查找输入pci）

模糊查找对应的插件名，然后安装

---

# 5 相关网站

[官网](http://www.sublimetext.com/blog/)
[注册码](http://www.jianshu.com/p/04e1b65dd2c0)
[插件安装教程，插件介绍](https://packagecontrol.io/installation)