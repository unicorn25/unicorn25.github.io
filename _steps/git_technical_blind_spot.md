---
layout: post
title: GIT的一些技术盲点(1)
date: 2017-09-17
author: Linkinmama
---



----
### 3个区域
Git有三个工作区域，分别为：工作区、暂存区以及历史区。三者之间的关系如图：
![](/images/linkinmama/git_1.png)

思考：远程分支有人在根目录下添加了一个文件名为s.txt的文件。而我恰巧也在本地根目录也添加了一个文件名为s.txt的文件，问:是stash save 以后，能不能pull成功？   

----
### stash pop 与 stash apply 的 区别
stash pop 成功以后会删除stash 存档
stash apply 成功以后还会保留stash 存档
  

----
### reset 3种方式的区别（soft，mixed,hard）
soft:将指定commit之后的commit信息全部并到working tree changes， 不修改文件。     
mixed:删除所有修改信息，不修改文件。   
hard:根据GIT记录的条件信息，依次对文件进行还原。（危险操作，对文件进行改动，可能无法恢复）。  
3者区别如图。
![](/images/linkinmama/git_reset_init.png)
![](/images/linkinmama/git_reset_soft.png)
![](/images/linkinmama/git_reset_mixed.png)
![](/images/linkinmama/git_reset_hard.png)

思考： 我在工作目录下新建一个文件A。 对最近一次提交进行reset- hard 操作 刚刚新建的文件是否被删除？


----

### cherry pick
重新提交指定的1个或多个commit（可以在同一分支，也可以跨分支）。
同一分支：
前面临时添加的测试文件，我觉得用不到了，所有全部删除。
![](/images/linkinmama/cherry_pick_0.png)
马上就后悔了，因为1.txt,3.txt,5.txt这3个文件很有可能以后会用到，必须还原。不要着急，我们可以利用cherry_pick 来解决这个问题。  
![](/images/linkinmama/cherry_pick_1.png)
![](/images/linkinmama/cherry_pick_2.png)
![](/images/linkinmama/cherry_pick_3.png)
如果你觉得新增了3个commit看起来冗余。那么你还可以设置 cherry_pick 参数为 Squash ALL。你可以将多个commit 合并为1个。
![](/images/linkinmama/cherry_pick_4.png)
![](/images/linkinmama/cherry_pick_5.png)

不同分支：
我新建了一个新的分支用于新功能开发，已经添加了2个功能点，这时突然发现，这时发现一个重大BUG，修改3.txt文件修复了BUG。
新功能分支如图：
![](/images/linkinmama/cherry_pick2_0.png)
主分支如图：
![](/images/linkinmama/cherry_pick2_1.png)
主分支也有这个致命的BUG，必须尽快修复。但是，新功能未开发完，不方便合并分支，那该怎么办？也可以用cherry pick来解决。
先切换到主分支。
![](/images/linkinmama/cherry_pick2_2.png)
查看当前分支的LOG信息。
![](/images/linkinmama/cherry_pick2_5.png)
将LOG信息列表切换到“新功能分支”。
![](/images/linkinmama/cherry_pick2_6.png)
cherry pick 修复BUG的commit。
![](/images/linkinmama/cherry_pick2_7.png)
cherry pick 修复BUG 的commit已经同步到了主分支了！
![](/images/linkinmama/cherry_pick2_8.png)


思考：怎么把最近的9次提交，合并为3个提交（commit1、commit2、commit3合并，commit4、commit5、commit6合并，commit7、commit8、commit9合并）。
待续......

