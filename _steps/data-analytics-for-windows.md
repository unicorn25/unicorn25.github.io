---
layout: post
title: Windows 平台数据统计的几个思路
date: 2018-3-23
author: Sam
---


### 前言
>我们的游戏即将上 steam ，而 steam 的游戏主要面对 Windows 平台的，因此这时急需一个能在 Windows 平台实施数据统计的工具。

---
### 方案一 利用现有市场上的统计平台
>现在市场上大部分数据统计平台(比如：友盟、talkingData、百度统计等)，都只有针对移动端（ios、Android）的统计功能，鲜有包含对 Windows 平台的数据统计服务。（个中原因，有点百思不得其姐）

1. [腾讯移动分析](http://developer.qq.com/wiki/mta/HTML5%E6%8E%A5%E5%85%A5/MTA%20HTML5%E7%BB%9F%E8%AE%A1API%E6%96%87%E6%A1%A3/MTA%20HTML5%E7%BB%9F%E8%AE%A1API%E6%96%87%E6%A1%A3.html) ： 腾讯移动分析之 HTML5 接入（可以用 http 传送数据，待验证）。
2. [Google Analytics](https://www.google.com/analytics/) ：可正常统计数据，然后浏览数据报表需要翻墙。另外统计数据量有限制。

**优势**
* 现成的轮子， 省了编码、运维
* 技术相对成熟，稳定性高

**缺点**
* 数据报表丰富度不够
* 更大的数据流量、更深层次的数据挖掘要花钱购买商业版本

---
### 方案二 用开源统计软件，搭建统计后台

1. [matomo](https://matomo.org/) : PHP  + MySQL
2. [Web Analytics. Open Source.](http://www.openwebanalytics.com/)
3. [AWStats](https://github.com/eldy/awstats) 日志文件分析工具

---
### 方案三 曲线救国（关注重点）

1. 利用 [消息队列云服务](https://www.aliyun.com/product/mns?spm=5176.8142029.388261.396.e939381fY1N4Z1) + 云主机， 来传递、存储数据。
2. 用 [chart.js](http://www.chartjs.org/) 图表来自定义展示各种数据报表。

**优势**
* 自定义程度高，能导出各种报表（当然前提是统计的数据要够完备）

**缺点**
* 需要购买 消息队列、云主机服务
* 需要编写数据导出、数据解析、数据报表展示功能的相关代码

---
### 附录

#### 1. 阿里云**消息服务**费用（本方案只关注 **Queue** 功能）

Queue 的费用构成： 请求次数费用 + 消息堆积费用＋外网下行流量费用 

>**免费额度**
>每个用户每月有100万次队列请求的免费额度。
>每个用户每月针对“主题”有100万次请求以及100万次推送的免费额度。
>推广期内，针对“主题实例费用”，每个用户每天有1个的免费额度。
>短信专用主题（topic 名字以“sms.”为前缀）免收实例费用。