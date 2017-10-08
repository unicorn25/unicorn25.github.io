---
layout: post
title: SCUT游戏服务器快速搭建
date: 2017-10-08
author: Sam
---

前言：本文章介绍的是 SCUT 在 Windows 平台运行流程。

### SCUT 简介

[SCUT](http://www.scutgame.com/) 包含从网络消息收发，到数据缓存，到数据库，一整套服务器解决方案。

特点：

* 免费开源的游戏服务器引擎，适用于开发AVG、SLGRPG、MMOG等类型的网络游戏
* 同时支持Http、WebSocket和Socket协议通讯
* 支持Window、Mac和Linux多种平台部署
* 支持Redis内存数据库和Microsoft SQL、MySql数据库
* 服务器引擎框架基于C#编写
* 支持热更新的方式部署
* 客户端可以使用Coscos2d、Unity3d、FlashAir与服务器引擎对接
* 提供了丰富的中间件，可以简单快捷的搭建您的游戏

相关网址：
* [官网 scutgame.com](http://www.scutgame.com/)
* [WiKi 帮助文档](https://github.com/ScutGame/Scut/wiki)
* [oschina 码云](https://gitee.com/scutgame/Scut) (源码仓库)
* [Github](https://github.com/ScutGame/Scut) (源码仓库)
* [redis](https://github.com/MicrosoftArchive/redis) (Windows平台)
* [MySql](https://dev.mysql.com/)
* [Navicat for MySQL](https://www.navicat.com/en/products/navicat-for-mysql) (MySql 管理工具)

### 1、配置运行环境

#### (1) 下载并配置 redis

redis 是SCUT的主要数据库。而 MySql 只是相当于 redis 的备份。
redis 下载参考上文的相关网址。redis目录如下：

```
└─redis
    │   redis-cli.exe
    │   redis-server.exe
    │   redis.windows.conf
```
其中，redis.windows.conf 为 redis 的配置文件，详细介绍可以参考：

[MicrosoftArchive/redis/wiki/redis.conf](https://github.com/MicrosoftArchive/redis/wiki/redis.conf)

#### (2) 下载并配置 MySql

**注意：**

>若只测试运行 SCUT，此步骤不是必须。但是若需要在数据库建立表格来存取数据，则必须先执行此步骤。

MySQL Community Server 下载地址 : [dev.mysql.com/downloads/mysql](https://dev.mysql.com/downloads/mysql/)

安装好 MySql 后，修改 ```Console/GameServer.exe.config```文件中，数据库的账号、密码（uid，pwd）。

![](/images/sam/scut/mysql-config.png)

然后，在数据库中创建以下三个对应的 database (可以用 Navicat 来执行)：
* snscenter
* phdata
* paydb


#### (3) 下载并配置 SCUT 服务程序

从源码仓库拉取源代码后，进入```\Scut\Release\6.7.9.11\Console``` 目录，点击```Install.bat```

![](/images/sam/scut/install.png)

完成后Console文件夹目录如下：
```
──Console
    │  GameServer.exe
    │  GameServer.exe.config
    │  GameServer.pdb
    │  ICSharpCode.SharpZipLib.dll
    │  Install.bat
    │  IronPython.dll
    │  IronPython.Modules.dll
    │  KopiLua.dll
    │  Microsoft.Dynamic.dll
    │  Microsoft.Scripting.dll
    │  Mono.Cecil.dll
    │  Mono.Cecil.Mdb.dll
    │  Mono.Cecil.Pdb.dll
    │  MySql.Data.dll
    │  Newtonsoft.Json.dll
    │  NLog.config
    │  NLog.dll
    │  NLua.dll
    │  protobuf-net.dll
    │  ScutSecurity.dll
    │  ScutSMS Readme.chm
    │  ScutSMS.exe
    │  ServiceStack.Common.dll
    │  ServiceStack.Interfaces.dll
    │  ServiceStack.Redis.dll
    │  ServiceStack.Text.dll
    │  ZyGames.Framework.Common.dll
    │  ZyGames.Framework.dll
    │  ZyGames.Framework.Game.dll
    │  
    └─Script
        ├─CsScript
        │  │  MainClass.cs
        │  │  
        │  ├─Action
        │  │      Action1000.cs
        │  │      Action1001.cs
        │  │      
        │  └─Locale
        │          SimplifiedLanguage.cs
        │          
        ├─LuaScript
        │  └─Action
        │          Action1001.lua
        │          
        └─Model
                GuestUser.cs
                UserRanking.cs
```

其中
* GameServer.exe 为服务器启动程序（双击运行即启动服务器）
* GameServer.exe.config 服务器配置文件
* NLog.config   NLog输出日志配置文件
* /Script/CsScript 目录为 C# 源代码存放目录
* /Script/Model 目录对应数据库表的类文件，且只能存放此类型文件

### 2、启动服务器

#### (1) 先启动 redis

注意：若有修改 redis.windows.conf 文件，redis启动需要加载它。

>可以写一个bat文件来启动redis，bat命令如下：

```
start redis-server.exe  redis.windows.conf 
```

启动成功后如下图：

![](/images/sam/scut/redis-ok.png)

#### (2) 再启动 GameServer.exe

启动成功后如下图：

![](/images/sam/scut/scut-ok.png)


### 3、关闭服务器

关闭服务器请反序启动流程。
