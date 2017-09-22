---
layout: post
title: GIT的一些技术盲点(2)
date: 2017-09-21
author: Linkinmama
---


### Bisect(2等分)
当你需要定位一个BUG，面对的却是茫茫多的commit。bisect 可以解你燃眉之急;你只需要不断用Bisect good告诉这个commit之前都是是好的，bisect bad 告诉GIT这个commit之后都是坏的。直到定位到BUG。
git-bisect 的命令很简单
bisect start ：开始bisect, ,和一个你
Bisect good：告诉GIT,这个commit之前的提交都是好的。
Bisect bad:告诉GIT,这个commit之后的提交都是坏的。
Bisect reset:停止bisect。
下面我们实际操作一下：
当前项目状态如下：
![](/images/linkinmama/Bisect1.png)     
在工作目录下右击选择Bisect start：
![](/images/linkinmama/Bisect2.png)     
你需要将能够确定的最晚一次没有BUG的commit设置为Good;    
将能够确认的最早出现bug的commit设置为bad;     
![](/images/linkinmama/Bisect3.png)   
设置good:
![](/images/linkinmama/Bisect4.png)  
设置bad:
![](/images/linkinmama/Bisect5.png)
这里我们选择

选择有bug的最早一次commit;
![](/images/linkinmama/Bisect2.png)

 
待续......

