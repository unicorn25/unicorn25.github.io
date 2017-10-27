---
layout: post
title: 怎样给英雄添加英雄特长
date: 2017-10-26
author: linkinmama
---

---  


# **在代码中添加新的英雄特长的ID**    
    
打开PublicID文件，枚举EHeroSpec的末尾添加HERO_SPEC_DISCIPLE_OF_DARKNESS。（必须在末尾添加，不能在中间插入。）                

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-27b3949a1ad5ffe1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)     

---  

     
# **修改英雄初始信息表**        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-ea0533be0c765109.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-4fa0bfdc0e615510.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        


---  


# **修改英雄特长的名称与描述**            
配置相关文本信息路径        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-640c256b93549023.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-413684e87c6f36e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        
在对应路径下新建文件，并修改信息。        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-1716faf5ffbb9d69.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-d074ce57d5eee9ee.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

---  


# **添加图标**        

## 修改图标配置文件        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-68a892d484162928.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-43576536adbc01bd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        



## 将头像打入图集        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-42d46b5884a448c9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-ed7d535f28dae98f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-b5c5cc66ba2cb6ba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-2deb851892c9f8b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-9bacf8f0302dd6f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-5229892579cfa7ed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        


![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-bfa827617a1c9fb6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        



## 在Unity内删除icon_hero_Merikh.png 文件        

这时可以在游戏内看到该英雄特长了。        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-fba33cfd8c87ca03.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        

---  


# **实现特长效果**        
在UnISpellInfo类476行插入代码：        
```
  if (buffs.Contains(EHeroSpec.HERO_SPEC_DISCIPLE_OF_DARKNESS.ToString()))
   {//暗之信徒：使英雄使用黑暗魔法时的施法法力+3。
        AddBuff(EHeroSpec.HERO_SPEC_DISCIPLE_OF_DARKNESS.ToString());
        AddBonus(BonusT.SpellpowerOfS_A_B(6));
   }
```
为了测试下效果，我们给梅瑞初始添加一个 延时大法 魔法。        

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-0ef9c94b00f91fe5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        
这时，我们就可以在英雄的魔法书面板看到英雄特长已经生效了。        
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2854160-e3d1a18f25430d24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)        