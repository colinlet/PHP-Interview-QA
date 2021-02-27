# PHP面试问答

结合实际PHP面试，汇总自己遇到的问题，以及网上其他人遇到的问题，尝试提供简洁准确的答案

包含网络、数据结构与算法、PHP、Web、MySQL、Redis、Linux、安全、设计模式、架构、面试等部分

> 本仓库将持续更新，fork 无法看到最新内容，建议 Watch 或 Star ~~

**温馨提示**

- 分享面试遇到的问题，通过提交 Issue

- 参与项目内容完善，通过提交 PR，提交内容请尽量保证`准确性`和`可读性`

- 本仓库需要什么内容：`实际经典面试题` + `靠谱简答` + `详细深入文章(必要的话)`

## 面试流程

![面试流程](./docs/assets/interview.png)

## 问题列表

### 网络篇

- [计算机网络体系结构](./docs/01.网络.md#1-计算机网络体系结构)
- [UDP 的主要特点](./docs/01.网络.md#2-udp-的主要特点)
- [TCP 的主要特点](./docs/01.网络.md#3-tcp-的主要特点)
- [简述三报文握手建立 TCP 连接](./docs/01.网络.md#4-简述三报文握手建立-tcp-连接)
- [建立 TCP 连接为什么最后还要发送确认](./docs/01.网络.md#5-建立-tcp-连接为什么最后还要发送确认)
- [简述 TCP 连接的释放](./docs/01.网络.md#6-简述-tcp-连接的释放)
- [TIME-WAIT 是什么，为什么必须等待 2MLS](./docs/01.网络.md#7-time-wait-是什么为什么必须等待-2mls)
- [TCP 粘包问题](./docs/01.网络.md#8-tcp-粘包问题)
- [UDP、TCP 区别，适用场景](./docs/01.网络.md#9-udptcp-区别适用场景)
- [建立 socket 需要哪些步骤](./docs/01.网络.md#10-建立-socket-需要哪些步骤)
- [DNS 主要作用是什么](./docs/01.网络.md#11-dns-主要作用是什么)
- [HTTP 报文组成](./docs/01.网络.md#12-http-报文组成)
- [HTTP 状态码](./docs/01.网络.md#13-http-状态码)
- [常见的 HTTP 方法](./docs/01.网络.md#14-常见的-http-方法)
- [GET 与 POST 请求方式区别](./docs/01.网络.md#15-get-与-post-请求方式区别)
- [HTTP 优缺点](./docs/01.网络.md#16-http-优缺点)
- [HTTPS 通信原理](./docs/01.网络.md#17-https-通信原理)
- [HTTP 2.0](./docs/01.网络.md#18-http-20)
- [WebSocket](./docs/01.网络.md#19-websocket)
- [IPv6 与 IPv4 有什么变化](./docs/01.网络.md#20-ipv6-与-ipv4-有什么变化)
- [什么是心跳机制](./docs/01.网络.md#21-什么是心跳机制)
- [什么是长连接](./docs/01.网络.md#22-什么是长连接)

### 数据结构与算法篇

- [概述](./docs/02.数据结构与算法.md#1-概述)
- [实现基础](./docs/02.数据结构与算法.md#2-实现基础)
- [线性结构](./docs/02.数据结构与算法.md#3-线性结构)
- [树](./docs/02.数据结构与算法.md#4-树)
- [散列查找](./docs/02.数据结构与算法.md#5-散列查找)
- [图](./docs/02.数据结构与算法.md#6-图)
- [排序](./docs/02.数据结构与算法.md#7-排序)
- [补充](./docs/02.数据结构与算法.md#8-补充)
- [经典算法题](./docs/02.数据结构与算法.md#9-经典算法题)

### PHP 篇

- [echo、print、print_r、var_dump 区别](./docs/03.PHP/QA.md#echoprintprint_rvar_dump-区别)
- [单引号和双引号的区别](./docs/03.PHP/QA.md#单引号和双引号的区别)
- [isset 和 empty 的区别](./docs/03.PHP/QA.md#isset-和-empty-的区别)
- [static、self、$this 的区别](./docs/03.PHP/QA.md#staticselfthis-的区别)
- [include、require、include_once、require_once 的区别](./docs/03.PHP/QA.md#includerequireinclude_oncerequire_once-的区别)
- [数组处理函数](./docs/03.PHP/QA.md#常见数组函数)
- [Cookie 和 Session](./docs/03.PHP/QA.md#cookie-和-session)
- [预定义变量](./docs/03.PHP/QA.md#预定义变量)
- [传值和传引用的区别](./docs/03.PHP/QA.md#传值和传引用的区别)
- [构造函数和析构函数](./docs/03.PHP/QA.md#构造函数和析构函数)
- [魔术方法](./docs/03.PHP/QA.md#魔术方法)
- [public、protected、private、final 区别](./docs/03.PHP/QA.md#publicprotectedprivatefinal-区别)
- [客户端/服务端 IP 获取，了解代理透传 实际IP 的概念](./docs/03.PHP/QA.md#客户端服务端-ip-获取了解代理透传-实际ip-的概念)
- [类的静态调用和实例化调用](./docs/03.PHP/QA.md#类的静态调用和实例化调用)
- [接口类和抽象类的区别](./docs/03.PHP/QA.md#接口类和抽象类的区别)
- [PHP 不实例化调用方法](./docs/03.PHP/QA.md#php-不实例化调用方法)
- [php.ini 配置选项](./docs/03.PHP/QA.md#phpini-配置选项)
- [php-fpm.conf 配置](./docs/03.PHP/QA.md#php-fpmconf-配置)
- [502、504 错误产生原因及解决方式](./docs/03.PHP/QA.md#502504-错误产生原因及解决方式)
- [如何返回一个301重定向](./docs/03.PHP/QA.md#如何返回一个301重定向)
- [PHP 与 MySQL 连接方式](./docs/03.PHP/QA.md#php-与-mysql-连接方式)
- [MySQL、MySQLi、PDO 区别](./docs/03.PHP/QA.md#mysqlmysqlipdo-区别)
- [MySQL 连接池](./docs/03.PHP/QA.md#mysql-连接池)
- [代码执行过程](./docs/03.PHP/QA.md#代码执行过程)
- [base64 编码原理](./docs/03.PHP/QA.md#base64-编码原理)
- [ip2long 实现](./docs/03.PHP/QA.md#ip2long-实现)
- [MVC 的理解](./docs/03.PHP/QA.md#mvc-的理解)
- [主流 PHP 框架特点](./docs/03.PHP/QA.md#主流-php-框架特点)
- [对象关系映射/ORM](./docs/03.PHP/QA.md#对象关系映射orm)
- [串行、并行、并发的区别](./docs/03.PHP/QA.md#串行、并行、并发的区别)
- [同步与异步的理解](./docs/03.PHP/QA.md#同步与异步的理解)
- [阻塞与非阻塞的理解](./docs/03.PHP/QA.md#阻塞与非阻塞的理解)
- [同步阻塞与非同步阻塞的理解](./docs/03.PHP/QA.md#同步阻塞与非同步阻塞的理解)
- [异步阻塞与异步非阻塞的理解](./docs/03.PHP/QA.md#异步阻塞与异步非阻塞的理解)

### Web 篇

- [SEO 有哪些需要注意的](./docs/04.Web/QA.md#seo-有哪些需要注意的)
- [img 标签的 title 和 alt 有什么区别](./docs/04.Web/QA.md#img-标签的-title-和-alt-有什么区别)
- [CSS 选择器的分类](./docs/04.Web/QA.md#css-选择器的分类)
- [CSS sprite 是什么，有什么优缺点](./docs/04.Web/QA.md#css-sprite-是什么有什么优缺点)
- [display: none 与 visibility: hidden 的区别](./docs/04.Web/QA.md#display-none-与-visibility-hidden-的区别)
- [display: block 和 display: inline 的区别](./docs/04.Web/QA.md#display-block-和-display-inline-的区别)
- [CSS 文件、style 标签、行内 style 属性优先级](./docs/04.Web/QA.md#css-文件style-标签行内-style-属性优先级)
- [link 与 @import 的区别](./docs/04.Web/QA.md#link-与-import-的区别)
- [盒子模型](./docs/04.Web/QA.md#盒子模型)
- [容器包含若干浮动元素时如何清理(包含)浮动](./docs/04.Web/QA.md#容器包含若干浮动元素时如何清理包含浮动)
- [如何水平居中一个元素](./docs/04.Web/QA.md#如何水平居中一个元素)
- [如何竖直居中一个元素](./docs/04.Web/QA.md#如何竖直居中一个元素)
- [flex 与 CSS 盒子模型有什么区别](./docs/04.Web/QA.md#flex-与-css-盒子模型有什么区别)
- [Position 属性](./docs/04.Web/QA.md#position-属性)
- [PNG,GIF,JPG 的区别及如何选](./docs/04.Web/QA.md#pnggifjpg-的区别及如何选)
- [为什么把 JavaScript 文件放在 Html 底部](./docs/04.Web/QA.md#为什么把-javascript-文件放在-html-底部)
- [JavaScript 数据类型](./docs/04.Web/QA.md#javascript-数据类型)
- [JavaScript 操作 DOM 的方法有哪些](./docs/04.Web/QA.md#javascript-操作-dom-的方法有哪些)
- [JavaScript 字符串方法有哪些](./docs/04.Web/QA.md#javascript-字符串方法有哪些)
- [JavaScript 字符串截取方法有哪些？有什么区别](./docs/04.Web/QA.md#javascript-字符串截取方法有哪些有什么区别)
- [setTimeout 和 setInterval 的区别](./docs/04.Web/QA.md#settimeout-和-setinterval-的区别)
- [使用 new 操作符实例化一个对象的具体步骤](./docs/04.Web/QA.md#使用-new-操作符实例化一个对象的具体步骤)
- [如何实现 ajax 请求](./docs/04.Web/QA.md#如何实现-ajax-请求)
- [同源策略是什么](./docs/04.Web/QA.md#同源策略是什么)
- [如何解决跨域问题](./docs/04.Web/QA.md#如何解决跨域问题)
- [引起内存泄漏的操作有哪些](./docs/04.Web/QA.md#引起内存泄漏的操作有哪些)
- [闭包理解及应用](./docs/04.Web/QA.md#闭包理解及应用)
- [对 JavaScript 原型的理解](./docs/04.Web/QA.md#对-javascript-原型的理解)
- [对 JavaScript 模块化的理解](./docs/04.Web/QA.md#对-javascript-模块化的理解)
- [如何判断网页中图片加载成功或者失败](./docs/04.Web/QA.md#如何判断网页中图片加载成功或者失败)
- [如何实现懒加载](./docs/04.Web/QA.md#如何实现懒加载)
- [JSONP 原理](./docs/04.Web/QA.md#jsonp-原理)
- [Cookie 读写](./docs/04.Web/QA.md#cookie-读写)
- 从浏览器地址栏输入 URL 到显示页面的步骤
- [Vue.js 双向绑定原理](./docs/04.Web/QA.md#vuejs-双向绑定原理)
- 如何进行网站性能优化
- [渐进增强](./docs/04.Web/QA.md#渐进增强)

### MySQL 篇

- [体系结构](./docs/05.MySQL/QA.md#体系结构)
- [基础操作](./docs/05.MySQL/QA.md#基础操作)
- [数据库设计范式](./docs/05.MySQL/QA.md#数据库设计范式)
- [数据库设计原则](./docs/05.MySQL/QA.md#数据库设计原则)
- [CHAR 和 VARCHAR 数据类型区别](./docs/05.MySQL/QA.md#char-和-varchar-数据类型区别)
- [LEFT JOIN 、RIGHT JOIN、INNER JOIN](./docs/05.MySQL/QA.md#left-join-right-joininner-join)
- [UNION、UNION ALL](./docs/05.MySQL/QA.md#unionunion-all)
- [常用 MySQL 函数](./docs/05.MySQL/QA.md#常用-mysql-函数)
- [锁](./docs/05.MySQL/QA.md#锁)
- [事务](./docs/05.MySQL/QA.md#事务)
- [常见存储引擎](./docs/05.MySQL/QA.md#常见存储引擎)
- [常见索引](./docs/05.MySQL/QA.md#常见索引)
- [聚族索引与非聚族索引的区别](./docs/05.MySQL/QA.md#聚族索引与非聚族索引的区别)
- [BTree 与 BTree-/BTree+ 索引原理](./docs/05.MySQL/QA.md#btree-与-btree-btree-索引原理)
- [分表数量级](./docs/05.MySQL/QA.md#分表数量级)
- [EXPLAIN 输出格式](./docs/05.MySQL/QA.md#explain-输出格式)
- my.cnf 配置
- 慢查询

### Redis 篇

- [Redis 介绍](./docs/06.Redis/QA.md#redis-介绍)
- [Redis 特点](./docs/06.Redis/QA.md#redis-特点)
- [Redis 支持哪些数据结构](./docs/06.Redis/QA.md#redis-支持哪些数据结构)
- [Redis 与 Memcache 区别](./docs/06.Redis/QA.md#redis-与-memcache-区别)
- [发布订阅](./docs/06.Redis/QA.md#发布订阅)
- [持久化策略](./docs/06.Redis/QA.md#持久化策略)
- [Redis 事务](./docs/06.Redis/QA.md#redis-事务)
- [如何实现分布式锁](./docs/06.Redis/QA.md#如何实现分布式锁)
- [Redis 过期策略及内存淘汰机制](./docs/06.Redis/QA.md#redis-过期策略及内存淘汰机制)
- [为什么 Redis 是单线程的](./docs/06.Redis/QA.md#为什么-redis-是单线程的)
- [如何利用 CPU 多核心](./docs/06.Redis/QA.md#如何利用-cpu-多核心)
- [集合命令的实现方法](./docs/06.Redis/QA.md#集合命令的实现方法)
- [有序集合命令的实现方法](./docs/06.Redis/QA.md#有序集合命令的实现方法)
- redis.conf 配置
- 慢查询

### Linux 篇

- [Linux 目录结构](./docs/07.Linux/QA.md#linux-目录结构)
- [Linux 基础](./docs/07.Linux/QA.md#linux-基础)
- [命令与文件查找](./docs/07.Linux/QA.md#命令与文件查找)
- [数据流重定向](./docs/07.Linux/QA.md#数据流重定向)
- [sed](./docs/07.Linux/QA.md#sed)
- [awk](./docs/07.Linux/QA.md#awk)
- [计划任务](./docs/07.Linux/QA.md#计划任务)
- [Vim](./docs/07.Linux/QA.md#vim)
- [负载查看](./docs/07.Linux/QA.md#负载查看)
- Linux 内存管理
- [进程、线程、协程区别](./docs/07.Linux/QA.md#进程线程协程区别)
- 进程间通信与信号机制

### 安全篇

- [跨站脚本攻击(XSS)](./docs/08.安全/QA.md#跨站脚本攻击xss)
- [跨站点请求伪造(CSRF)](./docs/08.安全/QA.md#跨站点请求伪造csrf)
- [SQL 注入](./docs/08.安全/QA.md#sql-注入)
- [应用层拒绝服务攻击](./docs/08.安全/QA.md#应用层拒绝服务攻击)
- [PHP 安全](./docs/08.安全/QA.md#php-安全)
- [伪随机数和真随机数](./docs/08.安全/QA.md#伪随机数和真随机数)

### 设计模式篇

- [什么是设计模式](./docs/09.设计模式/QA.md#什么是设计模式)
- [如何理解框架](./docs/09.设计模式/QA.md#如何理解框架)
- [主要设计模式](./docs/09.设计模式/QA.md#主要设计模式)
- [怎样选择设计模式](./docs/09.设计模式/QA.md#怎样选择设计模式)
- [单例模式](./docs/09.设计模式/QA.md#单例模式)
- [抽象工厂模式](./docs/09.设计模式/QA.md#抽象工厂模式)
- [工厂方法模式](./docs/09.设计模式/QA.md#工厂方法模式)
- [适配器模式](./docs/09.设计模式/QA.md#适配器模式)
- [观察者模式](./docs/09.设计模式/QA.md#观察者模式)
- [策略模式](./docs/09.设计模式/QA.md#策略模式)
- [OOP 思想](./docs/09.设计模式/QA.md#oop-思想)
- [抽象类和接口](./docs/09.设计模式/QA.md#抽象类和接口)
- [控制反转](./docs/09.设计模式/QA.md#控制反转)
- [依赖注入](./docs/09.设计模式/QA.md#依赖注入)

### 架构篇

- [OAuth 2.0](./docs/10.架构/QA.md#oauth-20)
- [单点登录](./docs/10.架构/QA.md#单点登录)
- [REST](./docs/10.架构/QA.md#rest)
- [API 版本兼容](./docs/10.架构/QA.md#api-版本兼容)
- [JWT](./docs/10.架构/QA.md#jwt)
- [画出 PHP 业务架构图](./docs/10.架构/QA.md#画出-php-业务架构图)
- [LVS](./docs/10.架构/QA.md#lvs)
- [Ngnix](./docs/10.架构/QA.md#ngnix)
- 服务化
- 微服务
- 服务注册发现
- [数据库读写分离](./docs/10.架构/QA.md#数据库读写分离)
- [数据库拆分](./docs/10.架构/QA.md#数据库拆分)
- [分布式事务](./docs/10.架构/QA.md#分布式事务)
- ID 生成器
- [一致性哈希](./docs/10.架构/QA.md#一致性哈希)
- [Redis 集群](./docs/10.架构/QA.md#redis-集群)
- 消息队列
- 穿透、雪崩
- 限流(木桶、令牌桶)
- 服务降级
- 语言对比

## 为何要写这个

从事软件开发，已经接近五个年头了，去年面试中，发现自己依然处于尴尬的位置。简单重复，缺乏挑战的工作，已经没有多大吸引力了，优秀的平台，面试缺屡次碰壁。人上年纪之后，思维敏感度、记忆力都明显有所下滑。

程序开发不要被限制在语言层面，这是大家都懂的道理。但是作为一个 PHP 开发者，很多时候都是缠绕在业务的沟壑，理想和现实总是相差甚大。去年由于部门重组，本来将近十余人负责的项目，之后只剩两三人负责，各种坑只能靠人肉解决，深感无力。

工作可能只是你的一部分，你必须有自己的能力定位。以前总觉得学什么，做什么都无所谓，需要学习的技术，花点时间快速学习就行，有新的技术出来，赶紧紧跟了解下。但这些年下来，发现自己却没有一样能够拿的出手的，甚至连一个像样的作品也没有。其实 PHP 的技术栈还是比较广的，在对整个技术栈有一定的掌握之后，可能还需要深挖几个自己喜欢的领域，否则在现今的就业市场里面，没有任何的竞争力。所以可以看到很多招聘者都在感慨，中高级工程师都去哪里了。

面试或者面试他人，无法逃避，那就选择面对。撰写《PHP 面试问答》，构建一个面试体系，而不必慌张的临时准备，时时刻刻都充分准备好，对自己负责，也对别人负责。

结合实际 PHP 面试，系统的汇总面试中的各种各样的问题，尝试提供简洁准确的答案。如果你在 PHP 面试中遇到问题，欢迎提 Issues 交流。包含网络、数据结构与算法、PHP、Web、MySQL、Redis、Linux、安全、设计模式、架构、自我介绍、离职原因、职业规划、准备问题等部分。

最后，祝愿大家在日后的求职中，都能拿到满意的 offer~~

## 参考

[术语对照表](./docs/术语对照表.md)：顾名思义，帮助联想知识点

[参考资料](./docs/参考资料.md)：站在巨人的肩膀上，你将能看的更远

## 声明

本资料仅供参考，水平有限，难免存在纰漏错误之处

欢迎转载，转载请标明来源出处，谢谢~~

作者：凌枫 Email：colinlets@gmail.com

链接：https://github.com/colinlet/PHP-Interview-QA