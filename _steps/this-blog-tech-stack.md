---
layout: post
title: 我们博客用到的技术概述
date: 2017-09-12
---

### Jekyll
Jekyll 是一个静态网站生成器，一个用于将模版和内容合并到一起从而创建网站的命令行工具。ekyll 将 Liquid 作为自身的模版语言，并且添加了许多对象（object）、标记（tag）和过滤器（filter）。这些新增内容包括代表内容页面的对象、用于在页面中引入内容片段的标记（tag），以及用于操作字符串和 URL 的过滤器。  
  
Jekyll 也即是 GitHub Pages 的底层引擎。
  
通常 Jekyll 项目使用的是稳定版的 Liquid，而不使用 beta 或 release candidate 版本。通过 Jekyll 的 gem 信息也 可查看 Jekyll 所依赖的所有 gem 包，从而可以了解 Jekyll 所使用的 Liquid 版本。

相关链接
>* [Jekyll英文官网](http://jekyllrb.com/)
>* [Jekyll中文网](http://jekyll.com.cn/)

----
### Liquid
Liquid是一门开源的**模板语言**，由 [Shopify](https://www.shopify.com/) 创造并用 Ruby 实现。它是 Shopify 主题的骨骼，并且被用于加载店铺系统的动态内容。
  
从 2006 年起，Liquid 就被 Shopify 所使用，现在更是被大量 web 应用所使用。

相关链接
>* [Liquid 英文官网](https://shopify.github.io/liquid/)
>* [Liquid 中文文档](https://liquid.bootcss.com/)（推荐）

----
### Bootstrap
Bootstrap 来自 Twitter，是目前很受欢迎的前端框架。  
Bootstrap 基于 HTML、CSS、Javascript，简洁灵活，使得 Web 开发更加快捷。

相关链接
>* [Bootstrap 英文官网](https://getbootstrap.com/)
>* [Bootstrap 中文网](http://www.bootcss.com/)
>* [Bootstrap 网站示例](http://expo.bootcss.com/)

----
### Font Awesome
Font-Awesome.css 提供可缩放矢量图标，它可以被定制大小、颜色、阴影，以及任何可用CSS定义的样式。

![](/images/sam/font-awesome-brief.png)

相关链接
>* [Font Awesome 英文官网](http://fontawesome.io/)
>* [Font Awesome 中文网](http://www.fontawesome.com.cn/)（推荐）

----
### BootCDN
BootCDN 是 [Bootstrap 中文网](http://www.bootcss.com/)和[又拍云](https://www.upyun.com/)共同支持并维护的前端开源项目免费 CDN 服务，由又拍云提供全部 CDN 支持，致力于为 Bootstrap、jQuery、Angular 一样优秀的前端开源项目提供稳定、快速的免费 CDN 加速服务。BootCDN 所收录的开源项目主要同步于 cdnjs 仓库。  
  
自 2013 年 10 月 31 日上线以来已经为上万家网站提供了稳定、可靠的免费 CDN 加速服务。 

![](/images/sam/bootcdn.png)

用到的css
>* [bootstrap 3.3.7](http://www.bootcdn.cn/bootstrap/)
>* [font-awesome 4.7.0](https://cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css)
  
相关链接
>* [BootCDN](http://www.bootcdn.cn/)
>* [Bootstrap 中文网](http://www.bootcss.com/)
>* [又拍云](https://www.upyun.com/)

----
### 阿里云 OSS & CDN
主要用来做资源（图片等大文件）的加速。  
**注意：不是免费的哦**

相关链接
>* [阿里云对象存储 OSS](https://www.aliyun.com/product/oss?spm=5176.8142029.388261.238.Ecx0mg)
>* [阿里云 CDN](https://www.aliyun.com/product/cdn?spm=5176.7933691.765261.248.3w7ips)


----
### 其他
#### 1、 W3Schools

W3Schools是一家WEB技术资源网站，提供全面的教程、完善的参考手册以及庞大的代码库，学习者可以直接在线阅读文档、查看代码并进行调试。W3Schools紧随WEB技术的飞速发展，把提供高品质的WEB技术资源作为自身的使命，并适时地推出重要的升级版本，为用户提供最新鲜的内容和服务。

相关链接
>* [w3school 英文官网](https://www.w3schools.com/)（要翻墙）
>* [w3school 英文版镜像](http://w3schools.bootcss.com/default.html)（国内访问友好）
>* [w3school 中文网站](http://www.w3school.com.cn/)（更新稍慢）


#### 2、编码规范
编写灵活、稳定、高质量的 HTML 和 CSS 代码的规范

相关链接
>* [html 规范](http://codeguide.bootcss.com/#html)
>* [css 规范](http://codeguide.bootcss.com/#css)