---
layout: post
title: 怎样添加英雄的初始信息
date: 2017-10-26
author: linkinmama
---

本文以Heroes7的新英雄梅瑞为例，教大家在无敌英雄中创建一个新英雄。    

在英雄世界网站，可以找到梅瑞的英雄资料:     

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-b4c5c4e15cf87695.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

---  

# **在代码中添加新英雄的ID**     
打开PublicID文件，在枚举EHeroIDs的末尾添加新的枚举项 Merikh 作为新英雄的ID。（必须在末尾添加，不能在中间插入。）     


![addid.png](http://upload-images.jianshu.io/upload_images/2854160-8e24ae5e3af1f5cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     


---

# **配置英雄初始信息**     
在 \resNew\Data\Heroes\Heroes.xml 文件中添加英雄初始信息配置文件的路径；     
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-6d3bbe62455c29ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     
![](http://upload-images.jianshu.io/upload_images/2854160-1d710b9a5104e3c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     

在resNew\Data\Heroes\boss\ 目录下，新建文本,并重命名为Merikh.xml（与上一步配置的路径对应）。     
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-ea0533be0c765109.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     
复制同目录下的ring.xml文件的内容到Merikh.xml中,以此为模板对英雄初始信息进行修改。     
![英雄初始信息.png](http://upload-images.jianshu.io/upload_images/2854160-f6b48289a2b97249.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     


---

# **修改英雄的名称及描述**     
修改跟英雄相关的文本配置路径；     

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-29528f8340cd9ea8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     
在resNew\Text\Game\Heroes\boss目录下新建文件夹，重命名为Merikh（与上一步配置的路径对应）；     
进入新建文件夹；     
新建name.txt，设置英雄名称；     
新建description.txt，设置描述。     

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-6988e2fe170b9179.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-5e50a6865098f7eb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     


---


# **配置英雄初始兵力**     
在 resNew\Client\HeroHeadIcon.xml 设置初始兵力。     
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-43915961fde526b5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-4377bd778b39863a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     