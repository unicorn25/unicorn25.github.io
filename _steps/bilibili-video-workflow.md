---
layout: post
title: 从录制到上传——我的B站视频制作流程
date: 2017-09-20
author: Sam
---

整个制作流程即为：录制、（特效）剪辑、压制、上传。

----
### 用到的工具软件
* [OBS Studio](https://obsproject.com/download)：视频录制（免费开源）
* [Adobe Premiere Pro CC 2017](http://www.adobe.com/cn/products/premiere/free-trial-download.html)：视频剪辑、简单特效（需付费，BUT你懂的）
* [小丸压制工具原版](http://maruko.appinn.me/#)：视频压制(免费)
* [哔哩哔哩投稿工具](https://member.bilibili.com/video/resubmit.html)：上传工具（免费，官方出品） 

----
### 1，OBS Studio

>个人经验：录像时，配置尽可能调高，录制高清晰的视频，到最后再去压制符合上传要求的视频。

我的OBS视频输出配置如下：

![](/images/sam/bili/obs-video-cfg.png)

![](/images/sam/bili/obs-output-video.png)

----
### 2，Adobe Premiere Pro CC 2017

推荐几个视频教程，这里就不班门弄斧了
* [Premiere CC 基础入门教程（b站）](https://www.bilibili.com/video/av8703816/)
*  [![](/images/sam/bili/doyoudo_logo.png)](http://doyoudo.com/)

我的 pr 导出配置如下：

![](/images/sam/bili/pr-output-cfg.png)

ps：导出的视频配置，可以保存为『预设』。再次导出时，就可以直接选择该预设而不用逐项配置了。


----
### 3，B站视频要求

#### (1) 视频码率要求

>下图来自B站官网

![](/images/sam/bili/b-video-requirement.png)

#### (2) 投稿要求
* 稿件封面图片大小不能超过1.5Mb，**图片高宽比为 1.6 ：1** 。 (实测，虽然官方推荐的尺寸是900x600)
* 一个稿件可以包含若干P（一集、二集、三集。。。）  

如何添加p见下图

![](/images/sam/bili/add-p.png)

----
### 4，小丸工具箱压制参数

首先给小丸工具箱点个赞！目前只用到了『视频压制』功能，目测其他的功能也非常实用，虽然自己还没用过。。。。。。

![](/images/sam/bili/xiaow-v-config.png)

ps: 设置 1760 kbps，是因为B站码率上限的红线是 1800 kbps，还是离红线一点距离安全点（事实是设为 1800 kbps 压制后，有时候B站还是会二压）


