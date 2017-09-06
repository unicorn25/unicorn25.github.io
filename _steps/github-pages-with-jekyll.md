---
layout: post
title: 一步步搭建个人博客----基于GitHub Pages & Jekyll
date: 2017-08-31
---

### GitHub Pages 是什么  
>[GitHub Pages](https://pages.github.com/)是GitHub提供的一项服务，可以用来免费搭建静态网站。    

可以把GitHub Pages理解为一个网页服务器，通过以下三步:   
1. 本地编写好对应的网页文件（通过Jekyll + MarkDown，甚至只需要关注每篇blog文章）。
2. 上传网页文件到GitHub。
3. GitHub编译通过，然后即可随意浏览发布的网页。

### 为什么要用GitHub Pages 搭建Blog
*关键词 :*
>Git、免费托管、静态网页、自定义网页

优点：
1. 免费
2. Blog有了基于Git的版本管理
3. 网站不在墙内
4. 支持MarkDown
5. 可以自定义主题、网页
6. 可以绑定自定义域名
7. 利用Jekyll，可以实现许多动态网页效果

----
### 搭建流程
#### 1，注册GitHub账号（[GitHub注册界面](https://github.com/)）
  ![](/images/sam/github-create-btn.png)  
      
#### 2, 创建一个仓库(Repository)
>注意：仓库名请保持同Owner名一致，如下图红色矩形框，不然之后无法绑定自定义域名。另外，README、.gitignore、license等文件选项可随意，不是重点)  

![](/images/sam/github-create-repo.png)

#### 3, 进入Settings，查看网站发布状态  
至此，一个空白的网站创建完成
>下图中的仓库已绑定了域名[ughorse.com](http://ughorse.com)，跟实际新建仓库有不同。  

![](/images/sam/github-repo-settings.png)   
![](/images/sam/github-settings-pages.png)  

#### 4，克隆仓库到本地
仓库地址如下图 ：
![](/images/sam/github-clone-url.png) 

然后克隆到本地 :
```
$ git clone git@github.com:username/username.github.com.git 
```

 #### Jekyll使用流程


 #### 自定义域名绑定流程
 什么是CNAME？
>CNAME是DNS的别名记录，可以理解为一个跳转。  
>例如，域名www.abc.com, 对应的真实源站IP为1.1.1.1，对应的CNAME为sam453.github.com。  
>那么，使用A记录时，DNS将www.abc.com A记录解析到 1.1.1.1；  
>使用CNAME记录时，DNS将www.abc.com CNAME记录到 sam453.github.com。  
>后者对应的真实IP是您不需要关心也不需要配置的，客户端会自动查询这个CNAME记录，最终得到一个IP（1.1.1.1）。
  
 ![](/images/sam/github-cname.png) 
