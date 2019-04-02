# PHP 面试问答 v2.0

> PHP 面试问答 v2.0 版本正在努力撰写中，你可以查看v1.0完成版
> [v1.0传送门](https://github.com/colinlet/PHP-Interview-QA/tree/1.0)

## 面试流程

![面试流程](./assets/interview.png)

## 技能树

![skill tree](./skill-tree.png)

## 前言

> 从事软件开发，已经接近五个年头了，去年面试中，发现自己依然处于尴尬的位置。简单重复，缺乏挑战的工作，已经没有多大吸引力了，优秀的平台，面试缺屡次碰壁。人上年纪之后，思维敏感度、记忆力都明显有所下滑。

> 程序开发不要被限制在语言层面，这是大家都懂的道理。但是作为一个 PHP 开发者，很多时候都是缠绕在业务的沟壑，理想和现实总是相差甚大。去年由于部门重组，本来将近十余人负责的项目，之后只剩两三人负责，各种坑只能靠人肉解决，深感无力。

> 工作可能只是你的一部分，你必须有自己的能力定位。以前总觉得学什么，做什么都无所谓，需要学习的技术，花点时间快速学习就行，有新的技术出来，赶紧紧跟了解下。但这些年下来，发现自己却没有一样能够拿的出手的，甚至连一个像样的作品也没有。其实 PHP 的技术栈还是比较广的，在对整个技术栈有一定的掌握之后，可能还需要深挖几个自己喜欢的领域，否则在现今的就业市场里面，没有任何的竞争力。所以可以看到很多招聘者都在感慨，中高级工程师都去哪里了。

> 面试或者面试他人，无法逃避，那就选择面对。撰写《 PHP 面试问答》，构建一个面试体系，而不必慌张的临时准备，时时刻刻都充分准备好，对自己负责，也对别人负责。

> 结合实际 PHP 面试，系统的汇总面试中的各种各样的问题，尝试提供简洁准确的答案。如果你在 PHP 面试中遇到问题，欢迎提 Issues 交流。包含网络协议、数据结构与算法、PHP、Web、MySQL、Redis、Linux、安全、设计模式、架构、自我介绍、离职原因、职业规划、准备问题等部分。

> 最后，祝愿大家在日后的求职中，都能拿到满意的 offer~~

## 术语对照表

> [术语对照表](./术语对照表.md)：顾名思义，帮助联想知识点

## 交流讨论组

<p align="left"><img width="320" src="./assets/wechat-groups.jpg" alt="wechat groups"></a></p>

## 问题列表

### [网络协议](./QA.md#网络协议)

- [计算机网络体系结构](./QA.md#计算机网络体系结构)

- [UDP 的主要特点](./QA.md#udp-的主要特点)

- [TCP 的主要特点](./QA.md#tcp-的主要特点)

- [如何让不可靠的 UDP 可靠(了解)](./QA.md#如何让不可靠的-UDP-可靠了解)

- [TCP 握手三次，断开四次，TIME-WAIT](./QA.md#tcp-握手三次断开四次time-wait)

- [TCP 粘包如何解决](./QA.md#tcp-粘包如何解决)

- [UDP、TCP 区别，适用场景](./QA.md#udptcp-区别适用场景)

- 建立 socket 需要哪些步骤

- TCP socket 和 UNIX socket 区别

- 本地 socket 与 网络 socket

- socket 如何实现多进程之间通信的

- [HTTP 状态码](./QA.md#http-状态码)

- [HTTP 请求报文构成](./QA.md#http-请求报文构成)

- [HTTP 优缺点](./QA.md#http-优缺点)

- [HTTPS 通信原理](./QA.md#http-通信原理)

- [HTTP 2.0](./QA.md#http-2.0)

- [DNS 主要作用是什么](./QA.md#dns-主要作用是什么)

- [IPv6 与 IPv4 有什么变化](./QA.md#ipv6-与-ipv4-有什么变化)

- [为什么是心跳机制](./QA.md#为什么是心跳机制)

- [什么是长连接](./QA.md#什么是长连接)

- [epoll](./QA.md#epoll)

### [数据结构与算法](./QA.md#数据结构与算法)

- [衡量、比较算法优劣的指标](./QA.md#衡量比较算法优劣的指标)

- [链表有哪些](./QA.md#链表有哪些)

- [线性结构](./QA.md#线性结构)

- [树](./QA.md#树)

- [散列查找](./QA.md#散列查找)

- [排序](./QA.md#排序)

- [其他](./QA.md#其他)

### PHP

- [echo、print、print_r、var_dump 的区别](./QA.md#echoprintprint_rvar_dump-的区别)

- [单引号和双引号的区别](./QA.md#单引号和双引号的区别)

- [isset 和 empty 的区别](./QA.md#isset-和-empty-的区别)

- [static、self、$this 的区别](./QA.md#staticselfthis-的区别)

- [include、require、include_once、require_once 的区别](./QA.md#includerequireinclude_oncerequire_once-的区别)

- 数组处理函数

- [Cookie 和 Session](./QA.md#cookie-和-session)

- [预定义变量](./QA.md#预定义变量)

- [传值和传引用的区别](./QA.md#传值和传引用的区别)

- [构造函数和析构函数](./QA.md#构造函数和析构函数)

- [魔术方法](./QA.md#魔术方法)

- [public、protected、private、final 区别](./QA.md#publicprotectedprivatefinal-区别)

- [客户端/服务端 IP 获取，了解代理透传 实际IP 的概念](./QA.md#客户端服务端-ip-获取了解代理透传-实际ip-的概念)

- [类的静态调用和实例化调用](./QA.md#类的静态调用和实例化调用)

- [PHP 不实例化调用方法](./QA.md#php-不实例化调用方法)

- [php.ini 配置选项，ini_set 动态设置](./QA.md#phpini-配置选项ini_set-动态设置)

- [如何返回一个301重定向](./QA.md#如何返回一个301重定向)

- [PHP 与 MySQL 连接方式](./QA.md#php-与-mysql-连接方式)

- [MySQL、MySQLi、PDO 区别](./QA.md#mysqlmysqlipdo-区别)

- [MySQL 连接池](./QA.md#mysql-连接池)

- [代码执行过程](./QA.md#代码执行过程)

- [base64 编码原理](./QA.md#base64-编码原理)

- [ip2long 实现](./QA.md#ip2long-实现)

- [MVC 的理解](./QA.md#mvc-的理解)

- [主流 PHP 框架特点](./QA.md#主流-php-框架特点)

- [对象关系映射/ORM](./QA.md#对象关系映射orm)

### Web

- [SEO 有哪些需要注意的](./QA.md#seo-有哪些需要注意的)

- [img 标签的 title 和 alt 有什么区别](./QA.md#img-标签的-title-和-alt-有什么区别)

- [CSS 选择器的分类及优先级](./QA.md#css选择器的分类及优先级)

- [渐进增强](./QA.md#css-选择器优先级)

### MySQL

### Redis

### Linux

### 安全

### 设计模式

### 架构

## 声明

> 本资料仅供参考，水平有限，难免存在纰漏错误之处

> 欢迎转载，转载请标明来源出处，谢谢~~

> 作者：凌枫 Email：colinlets@gmail.com 链接：https://github.com/colinlet/PHP-Interview-QA