---
layout: post
title: DoTween 使用体会
date: 2017-09-20
author: Sam
---


介绍
名词
初始化

使用（最好有gif动图）


### 命名前缀
* DO： 就是动画的方法。    例如：DoMove(),  DoKill()
* Set: 设置动画的一些属性。例如：SetLoop(), SetEase()
* On： 回调方法。  		   例如: OnStart(), OnComplete()

### DOTween.Init（初始化）

第一次在创建补间，DOTween 会自动初始化自身，使用默认值。

若要自定义其初始化（推荐），请在创建任何补间动画之前之前调用一次此方法

```
//recycleAllByDefault ：如果为true，则当Tween完成时就会被回收，放到一个池中；否则就会被destroy
//useSafeMode ：效率会稍微降低，但更安全
//logBehaviour ：默认值为只打印错误信息
public static IDOTweenInit Init( bool? recycleAllByDefault = null,
                                 bool? useSafeMode = null, 
                                 LogBehaviour? logBehaviour = null);
```

### 名词

**Tweener**
>A tween that takes control of a value and animates it.

补间动画：管理一个值并在这个值上创建动画


 **Sequence**

 >A special tween that, instead of taking control of a value, takes control of other tweens and animates them as a group.

 相当于一个tweener的链表，通过Sequence来执行一串Tweener

**Tween**

>A generic word that indicates both a Tweener and a Sequence.

 一个笼统的单词，既可以代表补间动画也可以代表序列


### 操作Tweener(有三种方法)

1. DOTween静态方法
2. Tweener 方法			myTween.Pause()
3. object. + Do开头方法 transform.DoPause

使用DoTween制作NGUI界面动画

可通过编辑器可视化定义动画

http://www.jianshu.com/p/8984fc4767c7










