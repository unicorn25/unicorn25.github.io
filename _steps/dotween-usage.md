---
layout: post
title: DoTween 入门简介
date: 2017-10-12
author: Sam
---


DoTween 是一个Unity3D 的动画插件，它是前身是HOTween，也是目前市面上使用比较多的一款插件。

它和iTween 性质一样，但DoTween 效率和功能更胜一筹。

而其链式代码调用，也使其更具人性化。

----

### 名词介绍

**1、Tweener**
>A tween that takes control of a value and animates it.

补间动画：管理一个值并在这个值上创建动画

 **2、Sequence**

 >A special tween that, instead of taking control of a value, takes control of other tweens and animates them as a group.

 相当于一个tweener的链表，通过Sequence来执行一串Tweener

**3、Tween**

>A generic word that indicates both a Tweener and a Sequence.

 一个笼统的单词，既可以代表补间动画也可以代表序列

----

### 命名前缀

* Do： 执行动画的方法。       eg：DoMove(),  DoKill()
* Set：设置动画的一些属性。   eg：SetLoop(), SetEase()
* On： 回调方法。  		   eg: OnStart(), OnComplete()

----

### DOTween.Init（初始化）

在第一次调用时，DOTween 会自动初始化自身，使用默认值。

若要自定义其初始化（推荐），请在创建任何补间动画之前之前调用一次此方法。

```
//recycleAllByDefault ：如果为true，则当Tween完成时就会被回收，放到一个池中；否则就会被destroy
//useSafeMode ：效率会稍微降低，但更安全
//logBehaviour ：默认值为只打印错误信息
public static IDOTweenInit Init( bool? recycleAllByDefault = null,
                                 bool? useSafeMode = null, 
                                 LogBehaviour? logBehaviour = null);
```

----

### 操作

**1、操作Tweener (有三种方法)**

1. DOTween 静态方法。    eg ： DOTween.To()
2. Tweener 方法。		  eg ： myTween.Pause()
3. object. + Do 开头方法。eg ： transform.DoPause

**2、操作Sequence 示例**

```
label.cachedTransform.localScale = new Vector3(0.01f, 0.01f, 0.01f);
Sequence seq = DOTween.Sequence();

float total = 1.5f;
float delay = 0.5f;

//1，跳跃
seq.Append(label.cachedTransform.DOLocalJump(new Vector3(60, -50, 0), 100f, 1, total)
                                .SetEase(Ease.Linear));

//1，同时放大
seq.Insert(0, label.cachedTransform.DOScale(2.0f, 0.5f)
                                   .SetEase(Ease.OutCirc));

//1，延时缩小
seq.Insert(0, label.cachedTransform.DOScale(0.3f, total - delay)
                                   .SetEase(Ease.Linear)
                                   .SetDelay(delay));

//1，延时淡出
seq.Insert(0, DOTween.To(() => label.alpha, a => label.alpha = a, 0, total - delay)
                     .SetEase(Ease.InQuint)
                     .SetDelay(delay));

seq.OnComplete(() => label.enabled = false);

seq.Play();
```
![](/images/sam/dotween/eg2.gif)

----

### 相关链接

**1、官网**

 [dotween.demigiant.com](http://dotween.demigiant.com/getstarted.php)

**2、动画参考**

Tween的移动类型有很多种，比如匀速运动、加速运动、减速运动，等等。

各移动类形式可以参考网站：

[easings.net/zh-cn](http://easings.net/zh-cn)

 ![](/images/sam/dotween/easing.png)

[robertpenner.com/easing/easing_demo.html](http://robertpenner.com/easing/easing_demo.html)

![](/images/sam/dotween/ease_demo.png)