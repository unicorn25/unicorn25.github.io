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
当前的log列表变为：
![](/images/linkinmama/Bisect6.png)
这是因为git会自动将head移动到处在good commit和bad commit中间位置的commit;   
此时，右键菜单会多出Bisect相关选项；
我们检查“+4.txt”的commit，发现没有问题。于是我们将其设为good;
![](/images/linkinmama/Bisect7.png)
log列表多了两次commit ,这是因为当我们把当前head 所在的commit 设置为good时，git又自动把head移动到bad commit 与good commit的中值;  
检查“+6”的commit，发现有问题。我们将其设为bad;   
![](/images/linkinmama/Bisect8.png)  
再检查“+6.txt” commit bug就锁定了。


选择有bug的最早一次commit;
![](/images/linkinmama/Bisect2.png)

 
待续......

