---
layout: post
title: 一些比较实用的Git和TortoiseGit的技巧
date: 2017-10-19
author: Unicorn25
---
  
Q：
> 同事请你帮他做一些调整，但你并不想在本地由你提交服务器，而是想打成patch发给同事，让他完全整个步骤后总体提交（走commit--format patch--reset步骤要对本地仓库进行修改和还原，一不小心就有可能污染远程仓库）。相对简洁的操作方式是什么？

问题本质：
* 不经过commit和reset，将工作区修改打成patch

A：
git bash
git diff > xxx.patch

or

git add ***Not Versioned Files***
git stash save
Format Patch...

---

Q：
> 想要stash的一些修改内容中有新增文件，stash save时默认不会加入这些文件，用include untracked选项又会保存很多应该被忽略的文件，如何只保存想保存的文件而又不漏掉新增文件？

问题本质：
* 避免使用include untracked参数来stash指定内容

A：
用Add选项将Not Versioned Files加入暂存区
git stash save

---

Q：
> 你在某一时期多次使用stash来保存一些功能未全部完成的修改记录，这些修改记录中的内容大部分是重复的，但是每一个修改记录又有可能有比较重要的工作片段。时间越长，你越有可能忘记具体的修改内容，你需要把这些重要的片段都提取到主分支里，该如何操作直至对stash list完成清理？

问题本质：
* 清理stash记录

A：
stash list
cherry pick this commit
compare with working tree
pick to working tree
重复以上操作

---

Q：
> 工作过程中比较随性的看到需要重构的内容就先改为敬，如此多次以后，却因为有的功能短时间难以完成而无法总体提交，如何把无bug的单元功能修改提取出来分部提交，最后再把未完成的功能修改stash？

问题本质：
* 将一次量很大的修改或提交分解成为若干次独立的事务提交

A：
reset ***branch*** to this
stash save
stash list
cherry pick this commit
compare with working tree
pick to working tree
commit
cherry pick this commit
compare with working tree
pick to working tree
commit
cherry pick this commit
compare with working tree
pick to working tree
commit