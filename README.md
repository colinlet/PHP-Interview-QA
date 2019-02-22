# PHP面试问答

> 结合实际PHP面试，汇总自己遇到的问题，以及网上其他人遇到的问题，尝试提供简洁准确的答案

> 包含MySQL、Redis、Web、安全、网络协议、PHP、服务器、业务设计、线上故障、个人简历、自我介绍、离职原因、职业规划、准备问题等部分

# 一般面试流程

![面试流程](./assets/interview.png)

# 目录 - [阅读](./PHP-Interview-QA.md)

MySQL

- MySQL 体系结构
- 字段类型
- char 和 varchar 数据类型区别
- 存储引擎
- 常见索引
- 聚族索引和非聚族索引的区别
- 事务机制
- BTree 与 BTree-/BTree+ 索引原理
- 参考资料

Redis

- Redis 主要特点
- Redis 数据类型
- 跳跃表与 Redis
- 一致性哈希
- 分布式锁
- 参考资料

Web

- JavaScript事件的三个阶段
- 闭包原理及应用
- 跨域
- JSONP 原理
- CSS 选择器的优先级
- CSS 盒子模型
- CSS 清除浮动
- 相对定位 relative、浮动 float、绝对定位 absolute 区别
- VUE 双向绑定原理
- 性能优化
- 参考资料

安全问题

- CSRF 攻击
- XSS 攻击
- SQL 注入
- IP 地址能被伪造吗
- include 请求参数
- md5 逆向原理
- DOS 攻击
- 参考资料

网络协议

- UDP 的主要特点
- TCP 握手三次，断开四次，TIME-WAIT
- socket
- HTTP 协议
- HTTPS 通信原理
- websocket 协议
- GET 与 POST 请求方式区别
- RESTful API
- 参考资料

PHP

- echo、print、print_r、var_dump的区别
- 超全局变量
- PHP 支持回调的函数，实现一个
- 发起 HTTP 请求有哪几种方式，它们有何区别
- 对象关系映射/ORM(Object Relational Mapping)
- MVC 的理解
- 类的静态调用和实例化调用
- 常见 PHP 框架特点
- 设计模式(design pattern)
- 工厂方法模式与抽象工厂模式区别
- base64 编码原理
- ip2long 实现
- 代码执行过程
- 弱类型变量如何实现
- 垃圾回收机制
- 进程间通信方式
- 链式调用实现
- 多进程同时写一个文件
- PHP 拓展
- PHP7 新特性
- PHP7 底层优化
- 构造函数和析构函数
- PHP 不实例化调用方法
- 参考资料

服务器

- 进程、线程、协程区别
- Linux 进程
- 反向代理
- 负载均衡
- nginx 中 fastcgi_pass 监听，unix socket 和 tcp socket 的区别
- 消息队列
- 参考资料

业务设计

- 网易盖楼
- 秒杀设计
- 消息队列
- 共享 SESSION
- 下单后30分钟未支付取消订单
- IP对应省市效率尽可能高
- 详细描述输入地址到打开网页过程
- 参考资料

线上故障

- 客户端热更新失败
- Redis 实例 used_memory 达到80%
- 游戏任务完成了进度未更新
- 测试服 HTTP 请求未响应
- 游戏账号被盗

个人简历

自我介绍

离职原因

- 跳槽频繁
- 这次换工作原因

职业规划

准备问题

- 工作挑战大不大?
- 项目开发是否写测试用例，项目上线先是否会进行压力测试
- 业务前景如何?
- 技术氛围如何?
- 根据这次面试，对个人进行评价，帮助成长
- 融资计划
- 是否有加班费/调休，公司福利，社保公积金缴纳基数

# 声明

> 本资料仅供参考，不保证正确性

> 作者：凌枫 Email：colinlets@gmail.com 链接：https://github.com/colinlet/PHP-Interview-QA

# 参考

- [这几天找工作遇到的面试题目，20 多家公司 100 多道题目](https://laravel-china.org/articles/9983/over-the-past-few-days-i-have-interviewed-100-topics-for-more-than-20-companies)
- [2016十家公司前端面试小记](http://www.cnblogs.com/xxcanghai/p/5205998.html)
- [3年PHPer的面试总结](https://juejin.im/post/59c8f4d55188257e8f03ab80)
- [八年phper的高级工程师面试之路](https://zhuanlan.zhihu.com/p/27493130)