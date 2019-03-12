### Abstract
&emsp;&emsp;Read The Fucking Source Code 是理解一套软件系统的最好的办法。但是，对于大型软件来说，RTFSC 往往是非常低效而又让人头疼的事。那么，有没有高效 RTFSC 的办法呢？

&emsp;&emsp;本文主要分享大牛们“高效阅读源码”的方法和总结自己在实践中的体会。随着这方面经验的增加，我会不断更新自己的心得。  

### Content
- [RTFSC Common Methods](#rtfsc_common_methods)
  - [读文档](#读文档)
  - [体验软件](#体验软件)
  - [编译和部署](#编译和部署)
  - [读日志](#读日志)
  - [梳理架构](#梳理架构)
  - [其他技巧](#其他技巧)
- [日志篇](#日志篇)
- [架构篇](#架构篇)
  - [外部架构](#外部架构)
  - [内部架构](#内部架构)
  - [模块角色](#模块角色)
- [工具篇](#工具篇)
  - [Notepad++](#notepad)
  - [OpenGrok](#opengrok)
  - [Understand](#understand)
  - [Depends.exe](#depends.exe)
  - [Meld](#meld)
- [Reference](#reference)
- 


### RTFSC_Common_Methods

下面是我根据大牛的分享和自己的实践，总结的“阅读源码”的通用方法：

1. 有文档，先读文档  
2. 体验软件，直观感受它的 Features    
3. 构建和部署软件（build and deploy）  
4. 阅读日志   
5. 自上而下摸清架构  

> “阅读程式码的重点，不在于读完每一行程式码，而是在于有效率地透过探索及阅读，从而了解系统的架构及行为模式。以便在你需要了解任何片段的细节实作时，能够很快在脑上对映到具体的程式码位置，直到那一刻，才是细读的时机。”


除了以上的通用方法，还有一些小技巧（详见 [其他技巧](#其他技巧)）：  

1. Debug，查看 CallStack
2. 建立 Abrreviation Table
3. 画 UML Graph 和 WorkFlow Graph
4. 研究 Demo
5. Rebuild，修改代码并观察结果
6. 使用 Depends.exe 查看 dll 的导出接口



#### 读文档

1. 先读用户文档（Overview, Manual Book, Quick Start），再读设计文档  
2. 快速浏览，读懂总体介绍和知道到哪找对应章节  
3. 设计文档不需要一次读懂，后面可以对照代码重读对应章节   
4. google 相关博客，利用前人的经验  


#### 体验软件

1. 掌握安装和配置  
2. （对照 Manual Book）操作各个 Features  
3. 查看安装目录，了解各个 exe 和 dll  
4. 浏览配置文档（INI and XML）和注册表（SYSTEM\Services and SOFTWARE）  
5. Procexp.exe 观察进程树


#### 编译和部署

这个步骤有两个作用：  
1. 为后面的步骤打基础  
2. 了解开发环境、框架和依赖的库

在这一步，最好将“通用框架”和“依赖的库”列出来，并 google 相关知识。


#### 读日志

对于大型软件，特别是多进程（线程）、分布式系统，单纯的 debug 并不容易，有时候效率也很低。此时，更高效的做法是“运行软件，分析日志”。  

我推荐的做法是将 “log” 和 “source code” 关联起来看。具体怎么做，请参考 [日志篇](#日志篇)。


#### 梳理架构

对于大型软件，一开始不要纠缠于具体的实现细节，而是要理清整个软件的架构，包括外部架构（运行环境）和内部架构（模块之间的关系）。具体方法，请看 [架构篇](#架构篇)


#### 其他技巧

##### Debug

这个是最常用的手段，可以查看 CallStack，非常有利于理解函数的关系和软件的层次。



#### 理解架构

自上而下摸清架构（事件驱动、MVC），理清模块的角色、层次和相互关系，画架构图
划分模块：Glue，Interface（BI），Implement（BL），Algorithm，Configuration，Task

#### 理解通用模式

编写 Demo 程序，掌握源码中用到的高深技术（IPC、callback）


#### Debug

查看 callstack and thread context


#### 归纳命名规则


#### 善于工具



### 日志篇

对于大型软件，特别是多进程（线程）、分布式系统，单纯的 debug 并不容易，有时候效率也很低。此时，更高效的做法是“运行软件，分析日志”。  

我一般选择 Notepad++ 来分析日志，基本用法参考 [工具篇](#工具篇)。

#### PID_TID

推荐在日志中打印 PID+TID （参考 glog），这样对于多进程或多线程程序，可以很方便地通过 PID+TID 进行过滤，顺着程序的执行序列去阅读 source code ，可以帮助你避免迷失在 Code 的森林中。  

此外，通过 PID+TID 还可以很轻松地找到**进程和线程的入口**。

#### FunctionName

对于嵌套层次比较深的函数，可以通过 “FunctionName” 过滤掉子函数，只看某个函数本身的执行序列。  

#### Enter_Leave

对于比较大的函数或者调用层次比较深的函数，一定要注意函数的边界。通过 “Enter >>” 和 “Leave <<” 可以确定函数的边界。


#### grep

Notepad++ 提供“正则查找”的功能。掌握“正则查找”，可以实现很多高级查找，比如 exclude 查找。关于“正则表达式”，可以参考一下资料快速学习：  

- [快速入门正在表达式](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Regular%20Expression%20for%20Python/Quick%20Start%20for%20Regular%20Expression.md)
- [Code-Reading Tools](https://www.spinellis.gr/ismr/tools/indexw.htm)

当然，如果有大批量定制化的需要，也可以自己动手，用 python 编写一个“正则表达”过滤的小程序。 



### 架构篇

对于大型软件，动则几十万行甚至百万行的 source code ，一开始不要去研究具体的模块实现代码，而是要理清它的架构，包括外部架构和内部架构。  

#### 外部架构

外部架构实际上就是你的软件的运行环境和你的软件在整个系统中的角色，特别是对于分布式的软件，更要首先认清这些情况。  
具体来说，外部架构包括：  
1. 角色  - Server/Client, Master/Slave, UserMode/KernelMode  
2. 框架  
3. 依赖的外部库  


#### 内部架构

内部架构主要是模块分层、角色和组织关系。这方面需要有相关知识的积累，包括：设计模式、软件架构。在此，我参考 [阮一峰：软件架构入门](http://www.ruanyifeng.com/blog/2016/09/software-architecture.html) ，列出几种常用的架构：  

##### 分层架构

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090302.png)

##### 事件驱动架构

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090304.png)


##### 微核架构

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090306.png)

##### 微服务架构

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090307.png)

##### 云架构

![](http://www.ruanyifeng.com/blogimg/asset/2016/bg2016090311.png)


#### 模块角色

“模块角色”主要是我的个人经验总结，特此单独拎出来，后续还会添加新的角色。


Role | Description
---|---
发起者（sender） | message/request 的发起者。例如： broswer 向 server 发起的 request，应用程序发起的数据库查询请求，IPC 消息发起者等
接收者（receiver）| 与 sender 对应。
处理者（handler） | 复杂架构中，receiver 与 handler 是分离的。其优点是：安全、资源均衡。
接口类代码（BI）| 它是模块的分界线。C++中的虚基类和PImpl类，JS 中的函数对象类等都是这种角色的典范。
连接类代码（Glue）| 它用于将各种模块粘合在一起，比如：回调函数注册，函数指针map，事件-响应绑定。这类代码，多见于模块初始化的地方。
配置文件解析模块（Cfg Parser）|专门针对配置文件读写的模块，包括 INI文件、XML 文件、JSON 文件、注册表等。
I/O模块 | 文件读写、应用层到内核层的I/O
数据库读写模块 | ORM和SQL 语句
异常处理模块 | 处理异常和Rollback
守护进程（daemon）| Windows service 程序，一般会开一个或多个线程循环






### 工具篇


#### Notepad

我首选 Notepad++ 来分析日志，在 Linux 下也可以使用 vim 等文本编辑器。Notepad++ 的 Find （Ctrl + f）的功能如下：  

![](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Read%20The%20Fuck%20Source%20Code/Images/notepad.jpg?raw=true)   

其中，文件内搜索类似 Linux - grep 命令。  

此外，掌握“正则查找”，可以实现很多高级查找，比如 exclude 查找。关于“正则表达式”，可以参考一下资料快速学习：  

- [快速入门正在表达式](https://github.com/SuperSurfing/Design-Pattern-and-Architecture/blob/master/Regular%20Expression%20for%20Python/Quick%20Start%20for%20Regular%20Expression.md)
- [Code-Reading Tools](https://www.spinellis.gr/ismr/tools/indexw.htm)

当然，如果有大批量定制化的需要，也可以自己动手，用 python 编写一个“正则表达”过滤的小程序。  


#### OpenGrok

OpenGrok 提供了一种 web app 的代码阅读方式（跨平台），它的最大好处是显示 target 所在的 Function Name 。其他的特性可以参考 [RTFSC with OpenGrok](https://mazhuang.org/2016/12/14/rtfsc-with-opengrok/) 。  

##### 安装

参考 [How to setup OpenGrok](https://github.com/oracle/opengrok/wiki/How-to-setup-OpenGrok) 和 [win7 安装 OpenGrok](https://blog.csdn.net/finewind/article/details/47362525)：  

第一步：下载并安装 [JAVA JDK8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)，然后设置环境变量

```
JAVA_HOME: C:\Program Files\Java\jdk1.8.0_191
JRE_HOEME: C:\Program Files\Java\jre1.8.0_191
```

在命令行中输入“java -version”即可查看版本信息，以验证是否安装成功。


第二步：下载并解压安装 [TomCat](http://tomcat.apache.org/) ，然后设置环境变量   

```
C:\Program Files\Java\apache-tomcat-9.0.13\bin\startup.bat
```

注意：要以“管理员身份运行” tomcat，此时访问 localhost:8080 可以打开 tomcat 首页

第三步： 下载并解压安装 [ctags-win32](https://github.com/universal-ctags/ctags-win32/releases)，

第四步： 下载并解压安装 [opengrok](https://oracle.github.io/opengrok/)

第五步： 在 OpenGrok 安装目录下新建目录 data 和 source （可以放在其他地方），再将 OpenGrok\bin\source.war 拷贝到 tomcat\whatapps\ 目录下。此时启动 tomcat ，访问 localhost:8080/source 可以打开 OpenGrok 。

第六步：输入如下命令

```
java -Xmx524m -jar E:\Code\OpenGrok\opengrok-1.1-rc80\lib\opengrok.jar -W
E:\Code\OpenGrok\opengrok-1.1-rc80\data\configuration.xml -c
E:\Code\OpenGrok\ctags2018\ctags.exe -P -S -v -s E:\Code\AI\source -d
E:\Code\OpenGrok\opengrok-1.1-rc80\data
```

第七步：参考 [RTFSC with OpenGrok](https://mazhuang.org/2016/12/14/rtfsc-with-opengrok/) 修改 tomcat。



#### Understand

参考 [Understand 安装](https://my.oschina.net/krysl/blog/2070243)





### Reference

- [7种方法，让你快速提高代码阅读能力](https://zhuanlan.zhihu.com/p/45493061)




