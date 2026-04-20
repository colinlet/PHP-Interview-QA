# PHP 面试问答

> 一份面向 PHP 工程师的面试问答手册 —— 覆盖 PHP 语言、运行原理、数据结构与算法、计算机网络、操作系统、存储与中间件、设计模式、架构与分布式、安全、Web、AI 时代的 PHP 工程师、职业发展等方向，按"初学者 → 架构师"的学习路径组织，力求用简洁准确的答案帮你从容应对从初级到架构师的各级面试。

## 使用指南

### 适用人群

- **初学者（0~1 年）**：从第一章 PHP 语言基础入手，优先看 `Lv1` 🟢 ~ `Lv2` 🔵 条目；
- **中级工程师（1~3 年）**：补齐 OOP、常用生态、常见陷阱，重点攻 `Lv3` 🟡 条目；
- **高级工程师（3~5 年）**：攻克运行原理、MySQL 45 讲、Redis、分布式基础，重点 `Lv4` 🟠 条目；
- **资深工程师 / 架构师（5 年+）**：系统设计、分布式一致性、性能优化、PHP 内核与源码，重点 `Lv5` 🔴 条目。

### 难度分级

| 等级 | 徽标 | 难度 | 目标岗位 | 关键字 |
| --- | --- | --- | --- | --- |
| `Lv1` | 🟢 | 入门 | 助理工程师 | 基础知识 |
| `Lv2` | 🔵 | 进阶 | 工程师 | 灵活使用 |
| `Lv3` | 🟡 | 深入 | 高级工程师 | 深入原理 |
| `Lv4` | 🟠 | 精通 | 资深工程师 | 疑难杂症 |
| `Lv5` | 🔴 | 宗师 | 架构师 / 专家 | 领域话语权 |

> 标有【试读】的条目为完全公开的示例篇，用于展示答题模板与行文风格。

### Q&A 条目模板

每一篇 Q&A 统一按以下结构组织，便于读者对比记忆：

1. **问题陈述** —— 一句话问题；
2. **考察意图** —— 面试官想听到什么；
3. **参考答案** —— 基础回答 / 进阶补充 / 加分项，分三层；
4. **常见追问** —— 面试中常见的 2~3 个追问；
5. **代码 / 图示** —— 尽量用最小可运行示例；
6. **延伸阅读** —— 官方文档 / RFC / 经典文章。

---

## 一、PHP 语言篇

### 1.1 语言与生态概览

- `Lv1` 🟢 [【试读】AI 时代的 PHP 开发者](./docs/php/ai时代的php开发者.md)
- `Lv1` 🟢 [【试读】编程语言基础](./docs/php/编程语言简介.md)
- `Lv2` 🔵 PHP 的定位：解释型、弱类型、动态、单请求生命周期
- `Lv2` 🔵 PHP 版本演进地图（5.x → 7.x → 8.x）
- `Lv2` 🔵 [当下最流行的 PHP 本地环境搭建方式](./docs/php/当下最流行的PHP本地环境搭建方式.md)
- `Lv2` 🔵 [主流 PHP 框架特点](./docs/php/主流PHP框架特点.md)
- `Lv2` 🔵 2025 年有哪些流行的框架（Laravel / Symfony / Hyperf / Webman / ThinkPHP）

### 1.2 基础语法

- `Lv1` 🟢 [单引号和双引号的区别](./docs/php/单引号和双引号的区别.md)
- `Lv1` 🟢 [php 支持哪些注释风格](./docs/php/php支持哪些注释风格.md)
- `Lv1` 🟢 [将变量打印出来，你知道哪些方式](./docs/php/将变量打印出来你知道哪些方式.md)
- `Lv1` 🟢 [预定义变量（超全局变量）](./docs/php/预定义变量.md)
- `Lv2` 🔵 [isset 和 empty 的区别之如何判空](./docs/php/isset和empty的区别之如何判空.md)
- `Lv2` 🔵 [include、require、include_once、require_once 的区别](./docs/php/include-require-include_once-require_once的区别.md)
- `Lv2` 🔵 [数组处理函数](./docs/php/常见数组函数.md)
- `Lv2` 🔵 [传值和传引用的区别](./docs/php/传值和传引用的区别.md)
- `Lv3` 🟡 [【试读】`==` 与 `===` 的区别（弱类型比较陷阱与 PHP 8 改动）](./docs/php/松散比较与严格比较的区别.md)
- `Lv2` 🔵 数据类型与类型转换基础（`0 == 'abc'`、`"0" == false`、PHP 8 比较改动）
- `Lv2` 🔵 字符串处理与多字节函数（`mb_*`）
- `Lv2` 🔵 日期、时间与时区（DateTimeImmutable、Carbon）
- `Lv2` 🔵 请使用 UTF-8 编码 / 乱码排查
- `Lv2` 🔵 本地化与国际化（i18n / l10n）
- `Lv3` 🟡 foreach 中引用 `&$value` 的常见坑

### 1.3 面向对象

- `Lv2` 🔵 [构造函数和析构函数](./docs/php/构造函数和析构函数.md)
- `Lv2` 🔵 [public、protected、private、final 区别](./docs/php/public-protected-private-final区别.md)
- `Lv2` 🔵 [static、self、$this 的区别](./docs/php/static-self-this的区别.md)
- `Lv2` 🔵 [类的静态调用和实例化调用](./docs/php/类的静态调用和实例化调用.md)
- `Lv2` 🔵 [接口类和抽象类的区别](./docs/php/接口类和抽象类的区别.md)
- `Lv2` 🔵 [PHP 不实例化调用方法](./docs/php/PHP不实例化调用方法.md)
- `Lv3` 🟡 [魔术方法](./docs/php/魔术方法.md)
- `Lv3` 🟡 魔术常量（`__CLASS__` / `__METHOD__` / `::class`）
- `Lv3` 🟡 Trait 与菱形继承
- `Lv3` 🟡 后期静态绑定（late static binding）
- `Lv3` 🟡 克隆与 `__clone`：深拷贝与浅拷贝
- `Lv3` 🟡 命名空间与 PSR-4 自动加载

### 1.4 进阶范式

- `Lv3` 🟡 函数式编程：闭包、箭头函数、first-class callable（`strtoupper(...)`)
- `Lv3` 🟡 元编程：Reflection、Attributes（PHP 8）
- `Lv3` 🟡 [【试读】PHP 反射详解](./docs/03.PHP/02.PHP反射详解.md)
- `Lv3` 🟡 生成器 Generator、`yield` / `yield from`
- `Lv3` 🟡 错误与异常：`Error` vs `Exception`、自定义异常体系
- `Lv4` 🟠 Fiber（PHP 8.1+）与协程生态（Swoole / Hyperf）

### 1.5 标准库与生态

- `Lv2` 🔵 PHP 标准库（SPL）：SplStack / SplQueue / SplHeap / SplObjectStorage
- `Lv2` 🔵 正则（PCRE）常见坑
- `Lv2` 🔵 [composer 包升级](./docs/php/composer包升级.md)
- `Lv3` 🟡 Composer 原理：autoload、lock、版本解析、私有仓库
- `Lv3` 🟡 依赖注入与容器（PSR-11）
- `Lv3` 🟡 PSR 规范全景（PSR-1/4/7/11/12/15/17/18）
- `Lv2` 🔵 常用 SDK/中间件：Guzzle、Monolog、PHPUnit

### 1.6 运行原理（高级 / 架构师必看）

- `Lv3` 🟡 [代码执行过程](./docs/php/代码执行过程.md)
- `Lv3` 🟡 [一条 echo 输出语句是如何执行的](./docs/php/一条echo输出语句是如何执行的.md)
- `Lv4` 🟠 Zend 引擎与 zval 结构
- `Lv4` 🟠 Opcache 工作原理与调优
- `Lv4` 🟠 JIT（PHP 8）：原理、收益边界、何时开启
- `Lv4` 🟠 垃圾回收：引用计数 + 循环引用检测
- `Lv3` 🟡 [FastCGI Process Manager](./docs/php/FastCGI-Process-Manager.md)
- `Lv3` 🟡 PHP-FPM 架构：master / worker、static / dynamic / ondemand
- `Lv3` 🟡 SAPI 生命周期（CLI / FPM / Apache Mod）

### 1.7 扩展与工程化

- `Lv2` 🔵 [PHP 与 MySQL 连接方式](./docs/php/PHP与MySQL连接方式.md)
- `Lv2` 🔵 [MySQL、MySQLi、PDO 区别](./docs/php/MySQL-MySQLi-PDO区别.md)
- `Lv3` 🟡 [MySQL 连接池](./docs/php/MySQL连接池.md)
- `Lv3` 🟡 [对象关系映射 / ORM](./docs/php/对象关系映射ORM.md)
- `Lv2` 🔵 [MVC 的理解](./docs/php/MVC的理解.md)
- `Lv2` 🔵 单元测试：PHPUnit、Pest、Mock、覆盖率
- `Lv3` 🟡 静态分析：PHPStan、Psalm、Rector
- `Lv2` 🔵 代码风格：PSR-12、PHP-CS-Fixer
- `Lv2` 🔵 Xdebug 调试入门
- `Lv2` 🔵 Postman / Apifox 接口调试
- `Lv3` 🟡 常用扩展：swoole、redis、mongodb、grpc、opentelemetry

### 1.8 PHP 数组与底层结构

- `Lv3` 🟡 [【试读】PHP 数组（HashTable 实现）](./docs/03.PHP/01.PHP数组.md)
- `Lv4` 🟠 PHP 数组既是 list 又是 map：底层 HashTable 结构
- `Lv4` 🟠 字符串的写时复制（COW）
- `Lv4` 🟠 对象属性存储与 `zend_object`

### 1.9 常见陷阱与面试热题

- `Lv2` 🔵 [502、504 错误产生原因及解决方式](./docs/php/502-504错误产生原因及解决方式.md)
- `Lv2` 🔵 [如何返回一个 301 重定向](./docs/php/如何返回一个301重定向.md)
- `Lv2` 🔵 [客户端 / 服务端 IP 获取，了解代理透传实际 IP 的概念](./docs/php/客户端服务端IP获取.md)
- `Lv3` 🟡 [php.ini 配置选项](./docs/php/php.ini配置选项.md)
- `Lv3` 🟡 [php-fpm.conf 配置](./docs/php/php-fpm.conf配置.md)
- `Lv3` 🟡 [Cookie 和 Session](./docs/php/Cookie和Session.md)
- `Lv3` 🟡 [base64 编码原理](./docs/php/base64编码原理.md)
- `Lv3` 🟡 [ip2long 实现](./docs/php/ip2long实现.md)
- `Lv3` 🟡 [串行、并行、并发的区别](./docs/php/串行-并行-并发的区别.md)
- `Lv3` 🟡 [同步与异步的理解](./docs/php/同步与异步的理解.md)
- `Lv3` 🟡 [阻塞与非阻塞的理解](./docs/php/阻塞与非阻塞的理解.md)
- `Lv3` 🟡 [同步阻塞与非同步阻塞的理解](./docs/php/同步阻塞与非同步阻塞的理解.md)
- `Lv4` 🟠 浮点数精度问题与 BCMath

---

## 二、PHP 现代化专题（PHP 7 → PHP 8.x）

- `Lv3` 🟡 PHP 7 相比 5 的核心变化（zval 重构、性能提升原因）
- `Lv3` 🟡 PHP 8.0：JIT、union types、named arguments、match 表达式、attributes、nullsafe 运算符
- `Lv3` 🟡 PHP 8.1：enum、readonly 属性、first-class callable、never 返回类型、纯交集类型、Fiber
- `Lv3` 🟡 PHP 8.2：readonly class、DNF 类型、`null` / `true` / `false` 独立类型
- `Lv3` 🟡 PHP 8.3：`#[\Override]`、typed class constants、`json_validate`
- `Lv4` 🟠 PHP 8.4：property hooks、asymmetric visibility、`new` 链式调用
- `Lv4` 🟠 老项目升级策略：Rector / 灰度切流 / 性能回归

---

## 三、数据结构与算法篇

- `Lv2` 🔵 [概述：时间与空间复杂度](./docs/02.数据结构与算法.md#1-概述)
- `Lv2` 🔵 [实现基础](./docs/02.数据结构与算法.md#2-实现基础)
- `Lv2` 🔵 [线性结构：数组 / 链表 / 栈 / 队列](./docs/02.数据结构与算法.md#3-线性结构)
- `Lv3` 🟡 字符串算法：KMP、Trie、Manacher
- `Lv3` 🟡 [树：二叉树 / BST / AVL / 红黑树](./docs/02.数据结构与算法.md#4-树)
- `Lv3` 🟡 B / B+ 树（指向 MySQL 索引）、跳表（指向 Redis）、LSM
- `Lv3` 🟡 [散列查找](./docs/02.数据结构与算法.md#5-散列查找) / 开放寻址 vs 链地址 / 一致性哈希 / 布隆过滤器
- `Lv3` 🟡 [图：BFS / DFS / Dijkstra / 并查集](./docs/02.数据结构与算法.md#6-图)
- `Lv2` 🔵 [排序：十大排序对比](./docs/02.数据结构与算法.md#7-排序)
- `Lv3` 🟡 算法范式：双指针、滑动窗口、二分、分治、回溯、DP、贪心
- `Lv4` 🟠 [经典算法题](./docs/02.数据结构与算法.md#9-经典算法题)

---

## 四、计算机网络篇

### 4.1 基础与协议栈

- `Lv2` 🔵 [计算机网络体系结构](./docs/01.网络.md#1-计算机网络体系结构)
- `Lv2` 🔵 [UDP 的主要特点](./docs/01.网络.md#2-udp-的主要特点)
- `Lv2` 🔵 [TCP 的主要特点](./docs/01.网络.md#3-tcp-的主要特点)
- `Lv3` 🟡 [简述三报文握手建立 TCP 连接](./docs/01.网络.md#4-简述三报文握手建立-tcp-连接)
- `Lv3` 🟡 [建立 TCP 连接为什么最后还要发送确认](./docs/01.网络.md#5-建立-tcp-连接为什么最后还要发送确认)
- `Lv3` 🟡 [简述 TCP 连接的释放](./docs/01.网络.md#6-简述-tcp-连接的释放)
- `Lv3` 🟡 [TIME-WAIT 是什么，为什么必须等待 2MSL](./docs/01.网络.md#7-time-wait-是什么为什么必须等待-2mls)
- `Lv3` 🟡 [TCP 粘包问题](./docs/01.网络.md#8-tcp-粘包问题)
- `Lv2` 🔵 [UDP、TCP 区别，适用场景](./docs/01.网络.md#9-udptcp-区别适用场景)
- `Lv2` 🔵 [建立 socket 需要哪些步骤](./docs/01.网络.md#10-建立-socket-需要哪些步骤)
- `Lv2` 🔵 [DNS 主要作用是什么](./docs/01.网络.md#11-dns-主要作用是什么)
- `Lv2` 🔵 [IPv6 与 IPv4 有什么变化](./docs/01.网络.md#20-ipv6-与-ipv4-有什么变化)

### 4.2 HTTP / HTTPS

- `Lv2` 🔵 [HTTP 报文组成](./docs/01.网络.md#12-http-报文组成)
- `Lv2` 🔵 [HTTP 状态码](./docs/01.网络.md#13-http-状态码)
- `Lv2` 🔵 [常见的 HTTP 方法](./docs/01.网络.md#14-常见的-http-方法)
- `Lv2` 🔵 [GET 与 POST 请求方式区别](./docs/01.网络.md#15-get-与-post-请求方式区别)
- `Lv3` 🟡 [HTTP 优缺点](./docs/01.网络.md#16-http-优缺点)
- `Lv3` 🟡 [HTTPS 通信原理](./docs/01.网络.md#17-https-通信原理)
- `Lv3` 🟡 [HTTP 2.0](./docs/01.网络.md#18-http-20)
- `Lv4` 🟠 HTTP/3、QUIC 原理与收益
- `Lv4` 🟠 TLS 1.2 vs TLS 1.3、0-RTT、SNI、OCSP
- `Lv3` 🟡 [WebSocket](./docs/01.网络.md#19-websocket)
- `Lv3` 🟡 幂等性、Idempotency-Key、重试策略

### 4.3 长连接与可观测性

- `Lv2` 🔵 [什么是心跳机制](./docs/01.网络.md#21-什么是心跳机制)
- `Lv2` 🔵 [什么是长连接](./docs/01.网络.md#22-什么是长连接)
- `Lv3` 🟡 Keep-Alive、连接复用、连接池
- `Lv3` 🟡 CDN、负载均衡（L4 vs L7）
- `Lv3` 🟡 抓包排错：tcpdump / Wireshark / curl -v / ss / netstat

---

## 五、操作系统与服务器篇

- `Lv2` 🔵 [Linux 目录结构](./docs/07.Linux/QA.md#linux-目录结构)
- `Lv2` 🔵 [Linux 基础](./docs/07.Linux/QA.md#linux-基础)
- `Lv2` 🔵 [命令与文件查找](./docs/07.Linux/QA.md#命令与文件查找)
- `Lv2` 🔵 [数据流重定向](./docs/07.Linux/QA.md#数据流重定向)
- `Lv2` 🔵 [sed](./docs/07.Linux/QA.md#sed) / [awk](./docs/07.Linux/QA.md#awk) / [Vim](./docs/07.Linux/QA.md#vim)
- `Lv2` 🔵 [计划任务](./docs/07.Linux/QA.md#计划任务)
- `Lv2` 🔵 [负载查看](./docs/07.Linux/QA.md#负载查看)
- `Lv3` 🟡 [进程、线程、协程区别](./docs/07.Linux/QA.md#进程线程协程区别)
- `Lv3` 🟡 进程调度（CFS）、线程模型（1:1 / M:N）
- `Lv3` 🟡 Linux 内存管理：分页、TLB、虚拟内存、OOM
- `Lv4` 🟠 I/O 模型：BIO / NIO / I/O 多路复用 / AIO（select / poll / epoll）
- `Lv4` 🟠 零拷贝：sendfile / splice / mmap
- `Lv3` 🟡 系统调用与 strace
- `Lv3` 🟡 性能定位：top / htop / vmstat / iostat / pidstat / perf
- `Lv3` 🟡 Nginx 配置与调优：reuseport、worker_connections、upstream
- `Lv3` 🟡 Linux 网络栈与 `/proc/sys/net` 关键参数
- `Lv3` 🟡 进程间通信与信号机制

---

## 六、存储与中间件篇

### 6.1 关系型数据库（MySQL）

#### 基础与设计

- `Lv2` 🔵 [体系结构](./docs/05.MySQL/QA.md#体系结构)
- `Lv2` 🔵 [基础操作](./docs/05.MySQL/QA.md#基础操作)
- `Lv2` 🔵 [数据库设计范式](./docs/05.MySQL/QA.md#数据库设计范式)
- `Lv2` 🔵 [数据库设计原则](./docs/05.MySQL/QA.md#数据库设计原则)
- `Lv2` 🔵 [CHAR 和 VARCHAR 数据类型区别](./docs/05.MySQL/QA.md#char-和-varchar-数据类型区别)
- `Lv2` 🔵 [LEFT JOIN、RIGHT JOIN、INNER JOIN](./docs/05.MySQL/QA.md#left-join-right-joininner-join)
- `Lv2` 🔵 [UNION、UNION ALL](./docs/05.MySQL/QA.md#unionunion-all)
- `Lv2` 🔵 [常用 MySQL 函数](./docs/05.MySQL/QA.md#常用-mysql-函数)

#### 索引与存储引擎

- `Lv3` 🟡 [常见存储引擎](./docs/05.MySQL/QA.md#常见存储引擎)
- `Lv3` 🟡 [常见索引](./docs/05.MySQL/QA.md#常见索引)
- `Lv3` 🟡 [聚簇索引与非聚簇索引的区别](./docs/05.MySQL/QA.md#聚族索引与非聚族索引的区别)
- `Lv3` 🟡 [BTree 与 BTree- / BTree+ 索引原理](./docs/05.MySQL/QA.md#btree-与-btree-btree-索引原理)
- `Lv3` 🟡 [深入浅出索引（上）](./docs/存储/深入浅出索引-上.md)
- `Lv3` 🟡 [深入浅出索引（下）](./docs/存储/深入浅出索引-下.md)
- `Lv3` 🟡 [普通索引和唯一索引，应该怎么选择](./docs/存储/普通索引和唯一索引，应该怎么选择.md)
- `Lv3` 🟡 [MySQL 为什么有时候会选错索引](./docs/存储/MySQL为什么有时候会选错索引.md)
- `Lv3` 🟡 [怎么给字符串字段加索引](./docs/存储/怎么给字符串字段加索引.md)

#### 锁与事务

- `Lv3` 🟡 [锁](./docs/05.MySQL/QA.md#锁)
- `Lv3` 🟡 [事务](./docs/05.MySQL/QA.md#事务)
- `Lv3` 🟡 [事务隔离：为什么你改了我还看不见？](./docs/存储/事务隔离-为什么你改了我还看不见.md)
- `Lv3` 🟡 [事务到底是隔离的还是不隔离的](./docs/存储/事务到底是隔离的还是不隔离的.md)
- `Lv3` 🟡 [全局锁和表锁：给表加个字段怎么有这么多阻碍](./docs/存储/全局锁和表锁-给表加个字段怎么有这么多阻碍.md)
- `Lv4` 🟠 [行锁功过：怎么减少行锁对性能的影响](./docs/存储/行锁功过-怎么减少行锁对性能的影响.md)
- `Lv4` 🟠 [幻读是什么，幻读有什么问题](./docs/存储/幻读是什么，幻读有什么问题.md)
- `Lv4` 🟠 [为什么我只改一行的语句，锁这么多](./docs/存储/为什么我只改一行的语句，锁这么多.md)

#### SQL 执行与优化

- `Lv3` 🟡 [一条 SQL 查询语句是如何执行的](./docs/存储/一条SQL查询语句是如何执行的.md)
- `Lv3` 🟡 [一条 SQL 更新语句是如何执行的](./docs/存储/一条SQL更新语句是如何执行的.md)
- `Lv3` 🟡 [EXPLAIN 输出格式](./docs/05.MySQL/QA.md#explain-输出格式)
- `Lv3` 🟡 [order by 是怎么工作的](./docs/存储/order-by是怎么工作的.md)
- `Lv3` 🟡 [如何正确地显示随机消息](./docs/存储/如何正确地显示随机消息.md)
- `Lv4` 🟠 [为什么这些 SQL 语句逻辑相同，性能却差异巨大](./docs/存储/为什么这些SQL语句逻辑相同，性能却差异巨大.md)
- `Lv4` 🟠 [为什么我只查一行的语句，也执行这么慢](./docs/存储/为什么我只查一行的语句，也执行这么慢.md)
- `Lv4` 🟠 [count() 这么慢，我该怎么办](./docs/存储/count()这么慢，我该怎么办.md)
- `Lv4` 🟠 [为什么我的 MySQL 会抖一下](./docs/存储/为什么我的MySQL会抖一下.md)
- `Lv4` 🟠 [为什么表数据删掉一半，表文件大小不变](./docs/存储/为什么表数据删掉一半，表文件大小不变.md)
- `Lv4` 🟠 [MySQL 有哪些饮鸩止渴提高性能的方法](./docs/存储/MySQL有哪些饮鸩止渴提高性能的方法.md)
- `Lv3` 🟡 慢查询定位与优化套路
- `Lv3` 🟡 my.cnf 关键配置项

#### 高可用与主从

- `Lv3` 🟡 [MySQL 是怎么保证数据不丢的](./docs/存储/MySQL是怎么保证数据不丢的.md)
- `Lv4` 🟠 [MySQL 是怎么保证主备一致的](./docs/存储/MySQL是怎么保证主备一致的.md)
- `Lv4` 🟠 [MySQL 是怎么保证高可用的](./docs/存储/MySQL是怎么保证高可用的.md)
- `Lv4` 🟠 [备库为什么会延迟好几个小时](./docs/存储/备库为什么会延迟好几个小时.md)
- `Lv4` 🟠 [主库出问题了，从库怎么办](./docs/存储/主库出问题了，从库怎么办.md)
- `Lv4` 🟠 [读写分离有哪些坑](./docs/存储/读写分离有哪些坑.md)
- `Lv4` 🟠 [如何判断一个数据库是不是出问题了](./docs/存储/如何判断一个数据库是不是出问题了.md)
- `Lv4` 🟠 [分表数量级](./docs/05.MySQL/QA.md#分表数量级)
- `Lv4` 🟠 在线 DDL：gh-ost / pt-osc
- `Lv4` 🟠 MySQL vs PostgreSQL 选型

### 6.2 NoSQL 与搜索

#### Redis

- `Lv2` 🔵 [Redis 介绍](./docs/06.Redis/QA.md#redis-介绍)
- `Lv2` 🔵 [Redis 特点](./docs/06.Redis/QA.md#redis-特点)
- `Lv2` 🔵 [Redis 支持哪些数据结构](./docs/06.Redis/QA.md#redis-支持哪些数据结构)
- `Lv3` 🟡 [Redis 与 Memcache 区别](./docs/06.Redis/QA.md#redis-与-memcache-区别)
- `Lv3` 🟡 [发布订阅](./docs/06.Redis/QA.md#发布订阅)
- `Lv3` 🟡 [持久化策略](./docs/06.Redis/QA.md#持久化策略)
- `Lv3` 🟡 [Redis 事务](./docs/06.Redis/QA.md#redis-事务)
- `Lv4` 🟠 [如何实现分布式锁](./docs/06.Redis/QA.md#如何实现分布式锁)
- `Lv3` 🟡 [Redis 过期策略及内存淘汰机制](./docs/06.Redis/QA.md#redis-过期策略及内存淘汰机制)
- `Lv4` 🟠 [为什么 Redis 是单线程的](./docs/06.Redis/QA.md#为什么-redis-是单线程的)
- `Lv4` 🟠 [如何利用 CPU 多核心](./docs/06.Redis/QA.md#如何利用-cpu-多核心)
- `Lv4` 🟠 [集合命令的实现方法](./docs/06.Redis/QA.md#集合命令的实现方法)
- `Lv4` 🟠 [有序集合命令的实现方法](./docs/06.Redis/QA.md#有序集合命令的实现方法)
- `Lv3` 🟡 redis.conf 关键配置与慢查询

#### 文档型、搜索、分析

- `Lv3` 🟡 MongoDB：文档模型、索引、副本集、分片
- `Lv3` 🟡 ElasticSearch：倒排索引、分词、相关性打分（TF-IDF / BM25）
- `Lv4` 🟠 ClickHouse：列存、向量化执行（OLAP 场景）

### 6.3 消息队列

- `Lv3` 🟡 Kafka：分区、副本、ISR、消费者组、Rebalance
- `Lv3` 🟡 RabbitMQ：Exchange / Queue / Binding、确认机制
- `Lv3` 🟡 RocketMQ：事务消息、顺序消息、延迟消息
- `Lv4` 🟠 消息投递可靠性：至少一次 / 最多一次 / 恰好一次
- `Lv4` 🟠 消息幂等、顺序消费、死信队列、积压排查

---

## 七、设计模式与编程范式

### 7.1 基础概念

- `Lv3` 🟡 [什么是设计模式](./docs/09.设计模式/QA.md#什么是设计模式)
- `Lv3` 🟡 [如何解决复杂问题](./docs/09.设计模式/QA.md#什么是设计模式)
- `Lv3` 🟡 [如何理解框架](./docs/09.设计模式/QA.md#如何理解框架)
- `Lv3` 🟡 [主要设计模式](./docs/09.设计模式/QA.md#主要设计模式)
- `Lv3` 🟡 [怎样选择设计模式](./docs/09.设计模式/QA.md#怎样选择设计模式)
- `Lv3` 🟡 [OOP 思想](./docs/09.设计模式/QA.md#oop-思想)
- `Lv3` 🟡 [抽象类和接口](./docs/09.设计模式/QA.md#抽象类和接口)
- `Lv3` 🟡 [控制反转](./docs/09.设计模式/QA.md#控制反转)
- `Lv3` 🟡 [依赖注入](./docs/09.设计模式/QA.md#依赖注入)

### 7.2 创建型

- `Lv2` 🔵 [单例模式](./docs/09.设计模式/QA.md#单例模式)
- `Lv3` 🟡 [工厂方法模式](./docs/09.设计模式/QA.md#工厂方法模式)
- `Lv3` 🟡 [抽象工厂模式](./docs/09.设计模式/QA.md#抽象工厂模式)
- `Lv3` 🟡 建造者 Builder / 原型 Prototype

### 7.3 结构型

- `Lv3` 🟡 [适配器模式](./docs/09.设计模式/QA.md#适配器模式)
- `Lv3` 🟡 装饰器 / 代理（与 Laravel Facade、AOP 结合）
- `Lv3` 🟡 桥接 / 组合 / 外观 / 享元

### 7.4 行为型

- `Lv3` 🟡 [观察者模式](./docs/09.设计模式/QA.md#观察者模式)
- `Lv3` 🟡 [策略模式](./docs/09.设计模式/QA.md#策略模式)
- `Lv3` 🟡 责任链（Laravel Middleware 的本质）
- `Lv3` 🟡 模板方法 / 命令 / 迭代器 / 状态 / 备忘录 / 中介者 / 访问者

### 7.5 框架 / 架构级模式

- `Lv3` 🟡 MVC / MVP / MVVM
- `Lv4` 🟠 Repository、Service Layer、Data Mapper、Active Record
- `Lv5` 🔴 Event Sourcing、CQRS
- `Lv4` 🟠 反模式：上帝类、过度抽象、Anemic Domain Model

---

## 八、架构与分布式

### 8.1 分布式理论

- `Lv4` 🟠 CAP、BASE、PACELC
- `Lv4` 🟠 一致性模型：强 / 最终 / 因果 / 读己之写
- `Lv5` 🔴 分布式协议（概念级）：Paxos、Raft、ZAB

### 8.2 API 与鉴权

- `Lv3` 🟡 [REST](./docs/10.架构/QA.md#rest)
- `Lv3` 🟡 [API 版本兼容](./docs/10.架构/QA.md#api-版本兼容)
- `Lv3` 🟡 [OAuth 2.0](./docs/10.架构/QA.md#oauth-20)
- `Lv3` 🟡 [单点登录](./docs/10.架构/QA.md#单点登录)
- `Lv3` 🟡 [JWT](./docs/10.架构/QA.md#jwt)
- `Lv3` 🟡 GraphQL vs REST、BFF 模式

### 8.3 高并发与高可用

- `Lv3` 🟡 [画出 PHP 业务架构图](./docs/10.架构/QA.md#画出-php-业务架构图)
- `Lv3` 🟡 [LVS](./docs/10.架构/QA.md#lvs) / [Nginx](./docs/10.架构/QA.md#ngnix)
- `Lv4` 🟠 缓存：多级缓存、穿透、击穿、雪崩
- `Lv4` 🟠 限流：计数器、漏桶、令牌桶、滑动窗口
- `Lv4` 🟠 熔断、降级、隔离（Hystrix / Sentinel 思想）
- `Lv4` 🟠 异步化、削峰填谷
- `Lv4` 🟠 多活、异地容灾、蓝绿 / 灰度 / 金丝雀发布

### 8.4 数据层架构

- `Lv3` 🟡 [数据库读写分离](./docs/10.架构/QA.md#数据库读写分离)
- `Lv4` 🟠 [数据库拆分](./docs/10.架构/QA.md#数据库拆分)
- `Lv4` 🟠 [分布式事务](./docs/10.架构/QA.md#分布式事务)（2PC / TCC / SAGA / 本地消息表）
- `Lv4` 🟠 [一致性哈希](./docs/10.架构/QA.md#一致性哈希)
- `Lv4` 🟠 [Redis 集群](./docs/10.架构/QA.md#redis-集群)
- `Lv4` 🟠 分布式 ID：雪花 / Leaf / UidGenerator

### 8.5 微服务与云原生

- `Lv4` 🟠 服务化 / 微服务拆分原则
- `Lv4` 🟠 服务注册发现（Consul / Nacos / Etcd）
- `Lv4` 🟠 API Gateway 与 Service Mesh
- `Lv4` 🟠 容器化与 Kubernetes（PHP 工程师使用者视角）
- `Lv4` 🟠 CI/CD：GitHub Actions / GitLab CI / Jenkins
- `Lv4` 🟠 可观测性：Logging / Metrics / Tracing、OpenTelemetry、Prometheus、Grafana、Jaeger
- `Lv5` 🔴 DDD / 整洁架构 / 六边形架构（[【试读】领域驱动设计 DDD](./docs/10.架构/QA.md)）

### 8.6 语言选型

- `Lv3` 🟡 PHP vs Go / Java / Node 在微服务场景下的取舍

---

## 九、系统设计实战（高级 / 架构师）

每道题统一按"需求 → 容量估算 → 架构图 → 关键技术点 → 追问"组织：

- `Lv4` 🟠 设计一个短链服务
- `Lv4` 🟠 设计一个秒杀 / 抢购系统
- `Lv4` 🟠 设计一个分布式 ID 生成器
- `Lv4` 🟠 设计一个分布式限流组件
- `Lv4` 🟠 设计一个分布式任务调度系统
- `Lv5` 🔴 设计一个 IM / 聊天系统
- `Lv5` 🔴 设计一个微博 / Feed 流系统
- `Lv5` 🔴 设计一个支付对账系统
- `Lv5` 🔴 设计一个红包 / 抽奖系统

---

## 十、性能优化与排障

- `Lv3` 🟡 慢接口定位套路：日志 → APM → trace → 代码
- `Lv3` 🟡 慢查询定位与 SQL 优化
- `Lv3` 🟡 PHP 进程 CPU 飙高排查（strace / perf / gdb）
- `Lv4` 🟠 PHP 内存泄漏排查（swoole 常驻场景）
- `Lv4` 🟠 连接泄漏、句柄泄漏定位
- `Lv3` 🟡 Nginx / FPM 瓶颈分析
- `Lv4` 🟠 压测：ab / wrk / JMeter / K6 方法论

---

## 十一、安全篇

- `Lv2` 🔵 【试读】密码学简介（对称 / 非对称 / 散列 / 数字签名）
- `Lv2` 🔵 【试读】加密与编码（AES / RSA / Base64 / URL Encode）
- `Lv3` 🟡 [跨站脚本攻击 XSS](./docs/08.安全/QA.md#跨站脚本攻击xss)
- `Lv3` 🟡 [跨站点请求伪造 CSRF](./docs/08.安全/QA.md#跨站点请求伪造csrf)
- `Lv3` 🟡 [SQL 注入](./docs/08.安全/QA.md#sql-注入)
- `Lv3` 🟡 [应用层拒绝服务攻击](./docs/08.安全/QA.md#应用层拒绝服务攻击)
- `Lv3` 🟡 [PHP 安全](./docs/08.安全/QA.md#php-安全)
- `Lv3` 🟡 [伪随机数和真随机数](./docs/08.安全/QA.md#伪随机数和真随机数)
- `Lv4` 🟠 SSRF、XXE、文件上传、目录穿越
- `Lv4` 🟠 PHP 反序列化漏洞（高频必考）
- `Lv4` 🟠 命令注入、代码注入（`eval` / `assert` / `preg_replace \e`）
- `Lv3` 🟡 密码存储：`password_hash` / `password_verify` / 盐 / 慢哈希
- `Lv4` 🟠 JWT 安全：none 算法、密钥泄露、刷新策略
- `Lv4` 🟠 OWASP Top 10、代码审计思路（RIPS / Semgrep）

---

## 十二、Web 基础（PHP 工程师够用版）

### 12.1 通用 Web 题

- `Lv2` 🔵 [SEO 有哪些需要注意的](./docs/04.Web/QA.md#seo-有哪些需要注意的)
- `Lv2` 🔵 从浏览器地址栏输入 URL 到显示页面的步骤
- `Lv3` 🟡 [同源策略是什么](./docs/04.Web/QA.md#同源策略是什么) / [如何解决跨域问题](./docs/04.Web/QA.md#如何解决跨域问题)
- `Lv3` 🟡 [JSONP 原理](./docs/04.Web/QA.md#jsonp-原理)
- `Lv2` 🔵 [Cookie 读写](./docs/04.Web/QA.md#cookie-读写)
- `Lv3` 🟡 如何进行网站性能优化
- `Lv3` 🟡 SSR / SPA / BFF 架构
- `Lv3` 🟡 PWA 与 Service Worker

### 12.2 HTML / CSS 速览

- `Lv1` 🟢 [img 标签的 title 和 alt 有什么区别](./docs/04.Web/QA.md#img-标签的-title-和-alt-有什么区别)
- `Lv1` 🟢 [CSS 选择器的分类](./docs/04.Web/QA.md#css-选择器的分类)
- `Lv2` 🔵 [CSS sprite 是什么，有什么优缺点](./docs/04.Web/QA.md#css-sprite-是什么有什么优缺点)
- `Lv2` 🔵 [display: none 与 visibility: hidden 的区别](./docs/04.Web/QA.md#display-none-与-visibility-hidden-的区别)
- `Lv2` 🔵 [display: block 和 display: inline 的区别](./docs/04.Web/QA.md#display-block-和-display-inline-的区别)
- `Lv2` 🔵 [CSS 文件、style 标签、行内 style 属性优先级](./docs/04.Web/QA.md#css-文件style-标签行内-style-属性优先级)
- `Lv2` 🔵 [link 与 @import 的区别](./docs/04.Web/QA.md#link-与-import-的区别)
- `Lv2` 🔵 [盒子模型](./docs/04.Web/QA.md#盒子模型)
- `Lv2` 🔵 [容器包含若干浮动元素时如何清理（包含）浮动](./docs/04.Web/QA.md#容器包含若干浮动元素时如何清理包含浮动)
- `Lv2` 🔵 [如何水平居中一个元素](./docs/04.Web/QA.md#如何水平居中一个元素) / [如何竖直居中一个元素](./docs/04.Web/QA.md#如何竖直居中一个元素)
- `Lv2` 🔵 [flex 与 CSS 盒子模型有什么区别](./docs/04.Web/QA.md#flex-与-css-盒子模型有什么区别)
- `Lv2` 🔵 [Position 属性](./docs/04.Web/QA.md#position-属性)
- `Lv2` 🔵 [PNG、GIF、JPG 的区别及如何选](./docs/04.Web/QA.md#pnggifjpg-的区别及如何选)
- `Lv2` 🔵 [渐进增强](./docs/04.Web/QA.md#渐进增强)

### 12.3 JavaScript 速览

- `Lv2` 🔵 [为什么把 JavaScript 文件放在 Html 底部](./docs/04.Web/QA.md#为什么把-javascript-文件放在-html-底部)
- `Lv2` 🔵 [JavaScript 数据类型](./docs/04.Web/QA.md#javascript-数据类型)
- `Lv2` 🔵 [JavaScript 操作 DOM 的方法有哪些](./docs/04.Web/QA.md#javascript-操作-dom-的方法有哪些)
- `Lv2` 🔵 [JavaScript 字符串方法有哪些](./docs/04.Web/QA.md#javascript-字符串方法有哪些) / [字符串截取方法有哪些？有什么区别](./docs/04.Web/QA.md#javascript-字符串截取方法有哪些有什么区别)
- `Lv2` 🔵 [setTimeout 和 setInterval 的区别](./docs/04.Web/QA.md#settimeout-和-setinterval-的区别)
- `Lv2` 🔵 [使用 new 操作符实例化一个对象的具体步骤](./docs/04.Web/QA.md#使用-new-操作符实例化一个对象的具体步骤)
- `Lv2` 🔵 [如何实现 ajax 请求](./docs/04.Web/QA.md#如何实现-ajax-请求)
- `Lv3` 🟡 [引起内存泄漏的操作有哪些](./docs/04.Web/QA.md#引起内存泄漏的操作有哪些)
- `Lv3` 🟡 [闭包理解及应用](./docs/04.Web/QA.md#闭包理解及应用)
- `Lv3` 🟡 [对 JavaScript 原型的理解](./docs/04.Web/QA.md#对-javascript-原型的理解)
- `Lv3` 🟡 [对 JavaScript 模块化的理解](./docs/04.Web/QA.md#对-javascript-模块化的理解)
- `Lv2` 🔵 [如何判断网页中图片加载成功或者失败](./docs/04.Web/QA.md#如何判断网页中图片加载成功或者失败) / [如何实现懒加载](./docs/04.Web/QA.md#如何实现懒加载)
- `Lv3` 🟡 [Vue.js 双向绑定原理](./docs/04.Web/QA.md#vuejs-双向绑定原理)

---

## 十三、PHP 源码与内核（资深 / 架构师选修）

- `Lv4` 🟠 PHP 编译流程：Lex → Parser → AST → Opcode
- `Lv4` 🟠 zval 的演化（PHP 5 vs PHP 7/8）
- `Lv5` 🔴 HashTable：PHP 数组的底层
- `Lv4` 🟠 字符串 `zend_string` 与写时复制
- `Lv4` 🟠 对象结构 `zend_object` 与属性表
- `Lv4` 🟠 Zend VM 执行模型
- `Lv5` 🔴 Opcache 缓存结构与 SHM 管理
- `Lv5` 🔴 JIT 的实现骨架
- `Lv5` 🔴 扩展开发入门：PHP 7/8 扩展 API

---

## 十四、AI 时代的 PHP 工程师

- `Lv2` 🔵 [【试读】AI 时代的 PHP 开发者](./docs/php/ai时代的php开发者.md)
- `Lv3` 🟡 AI 辅助编码（Cursor / Copilot）在 PHP 项目中的正确姿势
- `Lv3` 🟡 Prompt Engineering 基础与在后端研发中的场景
- `Lv4` 🟠 用 PHP 做 RAG：向量库（pgvector / Milvus）+ Embedding + LLM
- `Lv4` 🟠 MCP（Model Context Protocol）与 AI Agent 对接
- `Lv4` 🟠 AI 时代的软件架构变化：AI 网关、推理缓存、成本治理
- `Lv3` 🟡 PHP 工程师的 AI 转型路径

---

## 十五、面试软技能与职业发展

- [【试读】你的编码热情是如何消退的？](./docs/番外/你的编码热情是如何消退的.md)
- [技术岗面试潜规则](./docs/面试/技术岗面试潜规则.md)
- [设计一份吸引面试官的简历](./docs/面试/设计一份吸引面试官的简历.md)
- [读懂岗位精准投递](./docs/面试/读懂岗位精准投递.md)
- [做好充分的准备去面试](./docs/面试/做好充分的准备去面试.md)
- [把握面试时的关键点](./docs/面试/把握面试时的关键点.md)
- [捕捉面试官微表情，做出应对策略](./docs/面试/捕捉面试官微表情，做出应对策略.md)
- [巧妙推销自己的 3 个技巧](./docs/面试/巧妙推销自己的3个技巧.md)
- [判断公司背景，做出合理选择](./docs/面试/判断公司背景，做出合理选择.md)
- [了解行业薪资，清晰找准定位](./docs/面试/了解行业薪资，清晰找准定位.md)
- [目标明确，阐明沟通](./docs/面试/目标明确，阐明沟通.md)
- [工作交接流程福利衔接](./docs/面试/工作交接流程福利衔接.md)
- [如何让工作年限变成优势](./docs/面试/如何让工作年限变成优势.md)
- 薪资谈判实战话术
- 背调 / 背景调查应对
- Offer 比较模型（工资 / 期权 / 成长性 / 公司 / 加班）
- 架构师简历与初级简历的差异
- 35 岁焦虑与 PHP 工程师的出路

---

## 附录

- [术语对照表](./docs/术语对照表.md)
- [技能树](./docs/技能树.md)
- [参考资料](./docs/参考资料.md)
- 面试真题实录（按公司 / 按级别收录，持续更新）
- 常用工具速查（调试 / 抓包 / 性能 / 安全）
- 推荐书单与资料
