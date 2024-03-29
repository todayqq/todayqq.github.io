---
layout:     post                    # 使用的布局（不需要改）
title:      Laravel、PHPer 面试可能会遇到的问题及答案               # 标题 
subtitle:   Laravel、PHPer 面试可能会遇到的问题及答案 
date:       2017-09-24              # 时间
author:     Angkee                      # 作者
header-img:    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - PHP
    - Laravel
    - 面试题
---

### PHP模块

- PHP7 和 PHP5 的区别，具体多了哪些新特性？
  - 性能提升了两倍 
  - 结合比较运算符 (<=>)
  - 标量类型声明
  - 返回类型声明
  - `try...catch` 增加多条件判断，更多 Error 错误可以进行异常处理
  - 匿名类，现在支持通过new class 来实例化一个匿名类，这可以用来替代一些“用后即焚”的完整类定义
  - …… 了解更多文章底部有 PHP7 新特性链接
- 为什么 PHP7 比 PHP5 性能提升了？
  - 变量存储字节减小，减少内存占用，提升变量操作速度
  - 改善数组结构，数组元素和 hash 映射表被分配在同一块内存里，降低了内存占用、提升了 cpu 缓存命中率
  - 改进了函数的调用机制，通过优化参数传递的环节，减少了一些指令，提高执行效率

### laravel 模块 

- 服务提供者是什么？

服务提供者是所有 Laravel 应用程序引导启动的中心, Laravel 的核心服务器、注册服务容器绑定、事件监听、中间件、路由注册以及我们的应用程序都是由服务提供者引导启动的。

- IoC 容器是什么？

IoC（Inversion of Control）译为 「控制反转」，也被叫做「依赖注入」(DI)。什么是「控制反转」？对象 A 功能依赖于对象 B，但是控制权由对象 A 来控制，控制权被颠倒，所以叫做「控制反转」，而「依赖注入」是实现 IoC 的方法，就是由 IoC 容器在运行期间，动态地将某种依赖关系注入到对象之中。

其作用简单来讲就是利用依赖关系注入的方式，把复杂的应用程序分解为互相合作的对象，从而降低解决问题的复杂度，实现应用程序代码的低耦合、高扩展。

Laravel 中的服务容器是用于管理类的依赖和执行依赖注入的工具。

- Facades 是什么？

Facades（一种设计模式，通常翻译为外观模式）提供了一个"static"（静态）接口去访问注册到 IoC 容器中的类。提供了简单、易记的语法，而无需记住必须手动注入或配置的长长的类名。此外，由于对 PHP 动态方法的独特用法，也使测试起来非常容易。

- Contract 是什么？

Contract（契约）是 laravel  定义框架提供的核心服务的接口。Contract 和 Facades 并没有本质意义上的区别，其作用就是使接口低耦合、更简单。


- 依赖注入的原理？
 
这个就不解释了吧，这是理解 IoC 容器的前提。

- 什么是 Composer， 工作原理是什么？

Composer 是 PHP 的一个依赖管理工具。工作原理就是将已开发好的扩展包从 packagist.org composer 仓库下载到我们的应用程序中，并声明依赖关系和版本控制。

### 缓存#

- Redis、Memecached 这两者有什么区别？
  - Redis 支持更加丰富的数据存储类型，String、Hash、List、Set 和 Sorted Set。Memcached 仅支持简单的 key-value 结构。
  - Memcached key-value存储比 Redis 采用 hash 结构来做 key-value 存储的内存利用率更高。
  - Redis 提供了事务的功能，可以保证一系列命令的原子性
  - Redis 支持数据的持久化，可以将内存中的数据保持在磁盘中
  - Redis 只使用单核，而 Memcached 可以使用多核，所以平均每一个核上 Redis 在存储小数据时比 Memcached 性能更高。
- Redis 如何实现持久化？
  - RDB 持久化，将 redis 在内存中的的状态保存到硬盘中，相当于备份数据库状态。
  - AOF 持久化（Append-Only-File），AOF 持久化是通过保存 Redis 服务器锁执行的写状态来记录数据库的。相当于备份数据库接收到的命令，所有被写入 AOF 的命令都是以 redis 的协议格式来保存的。

### 数据库#

- 什么是索引，作用是什么？常见索引类型有那些？Mysql 建立索引的原则？

索引是一种特殊的文件,它们包含着对数据表里所有记录的引用指针，相当于书本的目录。其作用就是加快数据的检索效率。常见索引类型有主键、唯一索引、复合索引、全文索引。

- 索引创建的原则
  - 最左前缀原理
  - 选择区分度高的列作为索引
  - 尽量的扩展索引，不要新建索引

- 高并发如何处理？
  - 使用缓存
  - 优化数据库，提升数据库使用效率
  - 负载均衡

PHP 的设计模式就不多讲了，但是 SOLID 设计原则是每一位 PHPer 都必须要掌握的。 

### 其他问题
遗留又补充了一些 PHPer 的常见面试题留给大神们解答。

- 分库分表怎么设计
- 如何处理 MySQL 死锁？
- 谈谈你对闭包的理解
- PHP 内存回收机制
- 如何解决 PHP 内存溢出问题
- 数据库优化的方法
- 简述 Laravel 的运行原理
- Laravel 路由实现原理
- cookie 和 session 区别，session 保存在服务器的哪里？服务端是如何获取客户端的cookie？
- 服务器集群搭建、负载均衡、反向代理
- 服务器常用命令

> PS: PHPer 面试关注的技术实力仅仅只是一部分，还有一部分会关注你的内驱力、思考力以及表达能力。**其实关注最多的是你是否是妹子、还有你的颜值以及你是否单身！！！** 

答案放在了 GitHub 上，欢迎大家 Stat 和 PR.
传送门：https://github.com/todayqq/caseInterviewQuestions

码字不易，留下你的赞呗 

### 参考文章

- [php7 新特性](http://php.net/manual/zh/migration70.new-features.php)
- [浅谈IOC--说清楚IOC是什么](http://www.cnblogs.com/DebugLZQ/archive/2013/06/05/3107957.html)
- [Redis和Memcached的区别](https://www.biaodianfu.com/redis-vs-memcached.html)
- [Redis 持久化](http://www.jianshu.com/p/bedec93e5a7b)
- [Laravel 中文文档](https://d.laravel-china.org/docs/5.5)
- [MySQL索引原理及慢查询优化](https://tech.meituan.com/mysql-index.html)
