---
layout: post
title: 用 Nancy 搭建一个简单的 HTTP Server
date: 2017-11-15
author: Sam
---

最近考虑搭建一个web后台，用于收集游戏中的数据。因为对C#较为熟悉，决定用一个轻量级的C#框架，来迅速测试思路，而 Nancy 正是不二之选。

以下是 Nancy 的官方描述：
>Nancy is a lightweight, low-ceremony, framework for building HTTP based services on .Net and Mono.

**下面的介绍的， 是用 Self-hosting 模式的搭建流程。**


### 1，创建一个控制台程序

![](/images/sam/nancy/console.jpg)

然后添加引用（相关依赖的包将会自动安装）

```
Install-Package Nancy.Hosting.Self
```


### 2， 添加NancyHost

在Main函数中加入如下代码：

```
class Program
{
    static void Main(string[] args)
    {
        string path = "http://localhost:9000/";
        var uri = new Uri(path);
        using (var host = new NancyHost(uri))
        {
            host.Start();
            Console.WriteLine("Running on " + path);
            Console.ReadLine();
        }
        Console.WriteLine("Stopped. Good bye!");
    }
}

```

运行该程序，则很有可能遇到一个错误：

![](/images/sam/nancy/error1.png)

解决方法有多种（[点我跳转](http://volkanpaksoy.com/archive/2015/11/11/building-a-simple-http-server-with-nancy/)），最快的方法是给 NancyHost 添加配置信息，如下：

```
var config = new HostConfiguration();
config.UrlReservations.CreateAutomatically = true;

string path = "http://localhost:9000/";
var uri = new Uri(path);
using (var host = new NancyHost(config, uri))
{
    host.Start();
    Console.WriteLine("Running on " + path);
    Console.ReadLine();
}

```

### 3, 添加 NancyModule

直接运行修改好的代码，程序运行成功。

![](/images/sam/nancy/ok1.jpg)

在浏览器中测试 ``` http://localhost:9000/``` 

![](/images/sam/nancy/404.jpg)

这时，即需要添加 NancyModule，用来处理路由消息。

添加一个 HomeModule.cs，代码如下：

```
 /// 注意该类必须为 public
public class HomeModule : NancyModule
{
    public HomeModule()
    {
       Get["/"] = args => "hello world !"; ;

       Get["/nancy/{name}"] = msg => "Received request from : " + msg.name;
    }
}

```

编译时，若出现如下错误：

![](/images/sam/nancy/error2.jpg)

则需要在引用中，添加程序集：
>Microsoft.CSharp


测试结果如下：

![](/images/sam/nancy/result1.jpg)

![](/images/sam/nancy/result2.jpg)
