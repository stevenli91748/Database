# [Database 面试](https://github.com/stevenli91748/Database/blob/master/Interview.md)

[芋道源码---数据库实体设计](http://svip.iocoder.cn/categories/%E6%95%B0%E6%8D%AE%E5%BA%93%E5%AE%9E%E4%BD%93%E8%AE%BE%E8%AE%A1/)|[数据库设计](https://www.cnblogs.com/zping/category/147365.html)|[数据库架构设计的三种模式：share nothing , share everythong , share disk](https://www.cnblogs.com/kzwrcom/p/6397709.html)|
---|---|---|

 [微服务手册：分库分表从分析到实践，不再停留只会说分库分表](https://www.toutiao.com/a6897352881528177164/?log_from=94599671e8ca6_1630132174661)|[redis的7种类型100个方法全解析](https://www.toutiao.com/a6833638765508952588/?log_from=30b1b82b18ef6_1630173323928)|
 ---|---|

[Database Design Course - Learn how to design and plan a database for beginners](https://www.youtube.com/watch?v=ztHopE5Wnpc&t=43s)|
---|

[SQL Tutorial - Full Database Course for Beginners](https://www.youtube.com/watch?v=HXV3zeQKqGY)|
---|

[动态数据源例子---基于springboot的快速集成多数据源的启动器 已付费](https://www.kancloud.cn/tracy5546/dynamic-datasource/2344619)|
---|


[常用数据库建模工具](https://blog.csdn.net/wren2004/article/details/79554817)|[关于电商网站数据库的设计](https://www.zhihu.com/question/27607346)|[研发库表设计规范](https://www.jianshu.com/p/4b0d82c817fa)|
---|---|---|

[超给力，一键生成数据库文档-数据库表结构逆向工程](http://www.zimug.com/java/spring/%e8%b6%85%e7%bb%99%e5%8a%9b%ef%bc%8c%e4%b8%80%e9%94%ae%e7%94%9f%e6%88%90%e6%95%b0%e6%8d%ae%e5%ba%93%e6%96%87%e6%a1%a3-%e6%95%b0%e6%8d%ae%e5%ba%93%e8%a1%a8%e7%bb%93%e6%9e%84%e9%80%86%e5%90%91%e5%b7%a5/.html)|[一文快速入门分库分表（必修课）](https://my.oschina.net/u/4455409/blog/4649313)|
---|---|



# 目录
* [数据库概述](#数据库概述)
* [数据库设计](https://github.com/stevenli91748/Database/blob/master/%E6%95%B0%E6%8D%AE%E5%BA%93%E8%AE%BE%E8%AE%A1/README.md)
  * [一步步带你了解分布式数据库的架构演变之路](https://zhuanlan.zhihu.com/p/57907022)
  * [支撑百万并发的数据库架构如何设计？](https://zhuanlan.zhihu.com/p/57802566)
  * 需求建模
    * 需求分析---就是要明确系统的数据存储需求
    * 概念设计
      * 1. E-R图
      * 2. 表结构设计
        * 2.1  表结构设计工具
          * MySQL workbench
          * Navicat
          * phpMyAdmin
      * 3. 列的约束，限制
      * 4. 索引的设计
* [关系数据库](https://github.com/stevenli91748/Database/blob/master/关系数据库/README.md)
  * 数据库系统
    * [MySQL](https://github.com/stevenli91748/Database/blob/master/MySQL/README.md)
    * [Mariadb](https://github.com/stevenli91748/Database/blob/master/Mariadb/README.md)
    * PostgreSQL
    * ORACLE
    * [Mybatis](https://github.com/stevenli91748/Database/blob/master/Mybatis/README.md)
    * [SQLite](https://github.com/stevenli91748/Database/blob/master/SQLite/README.md)
   * [SQL语言](https://github.com/stevenli91748/Database/tree/master/SQL)
  * 数据库访问技术 
    * [JDBC](https://github.com/stevenli91748/Database/blob/master/JDBC/README.md) 
    * ODBC
    * DAO
    * OLE DB
    * ADO
    * ADO.NET
    * PDO
    * PyMySQL
    * MySQL 2
    * GO-SQL-Driver
* NoSQL数据库
  * 内存数据库
    * [Redis---内存数据库，redis只支持kv不支持sql](https://github.com/stevenli91748/Database/blob/master/Redis/README.md)
    * Apache Ignite---内存数据库，数据网格，计算网格，服务网格，sql网格，数据结构，流计算，文件系统，高级集群等模块，都是放在内存操作
    * sqlite---内存sql数据库，但不支持分布式 
  * [NON-SQL Database](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/NoSQL数据库集群.md)
    * K-V存储---解决关系数据库无法存储数据结构的问题，以Redis 为代表
      * [Redis---内存数据库，redis只支持kv不支持sql](https://github.com/stevenli91748/Database/blob/master/Redis/README.md)
    * 文档数据库---解决关系数据库强schema 约束的问题，以MongoDB 为代表
      * [MongoDB](https://github.com/stevenli91748/Database/blob/master/MongoDB/README.md)  
    * 列式数据库： 解决关系数据库大数据场景下的I/O 问题，以HBase 为代表
      * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
    * 全文搜索引擎：解决关系数据库的全文搜索性能问题，以Elasticsearch 为代表
      * [Elasticsearch](https://github.com/stevenli91748/Database/blob/master/Elasticsearch/README.md)
    * Memcache
    * [图数据库 Neo4j](https://github.com/stevenli91748/Database/tree/master/Neo4j%E5%9B%BE%E5%BD%A2%E6%95%B0%E6%8D%AE%E5%BA%93)
* Distribute Database
  * [缓存系统](https://github.com/stevenli91748/Database/blob/master/缓存系统/README.md)
  * [数据库连接池](https://github.com/stevenli91748/Database/blob/master/%E6%95%B0%E6%8D%AE%E5%BA%93%E8%BF%9E%E6%8E%A5%E6%B1%A0/README.md)
  * 文件存储
    * 小文件存储
      * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
      * Hadoop
      * Hypertable
      * FastDFS
      * TFS(taobao)
      * JFS(JD)
      * Haystack(facebook)
    * 大文件存储
      * Hadoop
      * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
      * Storm
      * Hive
* Cloud Database
* Database Tools
  * [navicat](https://github.com/stevenli91748/Database/blob/master/Navicat/README.md)

## 数据库概述

数据库的高性能方案有：优化当前数据库，和建立集群。
当数据库开始出现性能下降的时候，最优先的方案是：优化当前数据库的性能，而非立刻建立集群。应该保持简单原则，毕竟会增加很大复杂度。

**对于数据量不是很大，关联性不是很复杂的数据，可以使用传统的关系数据库，如MySQL或者Oracle。对于数据量较大，更新不是很频繁的数据，可以使用MongoDB等NoSQL数据库。对于一些关系复杂，关联比较多的数据，则可以使用图数据库，如Neo4j等。这样针对不同的业务特性，使用合适的数据库**



1.当前数据库优化策略：

建立索引
优化sql
使用效率更高的操作方式。如大量数据批量插入。

2.建立集群：

读写分离
从库的负载均衡
分片、分库、分表（sharding）

3.mysql集群搭建方案：

使用官方推荐：Mysql Cluster方案
使用mysql中间件atlas方案
其他集群方案

# Database视频

 * [数据库面试选择题精讲（第一期）（001-100）](https://edu.51cto.com/center/course/lesson/index?id=684264)
 * [数据库面试选择题精讲（第二期）（101-200）](https://edu.51cto.com/center/course/lesson/index?id=734912)
 * [ 58沈剑谈数据库架构典型设计方案 --实战案例讲数据库架构设计玩法](https://edu.51cto.com/center/course/lesson/index?id=249944)
 * [一堂课带你精通~数据库连接池编程思想与实现](https://www.bilibili.com/video/av58455529)

# 有用的参考
 * [为什么不建议把数据库部署在Docker容器内](https://www.jianshu.com/p/8540704fa4d1)
 * [面试官扎心一问：数据量很大，分页查询很慢，有什么优化方案？](https://zhuanlan.zhihu.com/p/169599922?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
 * [数据库并发控制](https://zhuanlan.zhihu.com/p/168672853?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
 * [如何设计能支撑百万并发的数据库架构？](http://www.52im.net/thread-2510-1-1.html)
 * [不用找了，大厂在用的分库分表方案，都在这里！](https://www.jianshu.com/p/5b2bb76d26d6)
 * [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [学习数据库从入门到进阶书籍pdf版吐血整理推荐（珍藏版）](https://pymlovelyq.github.io/2018/10/12/database/)

* [如何设计一个数据库中间件](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483731&idx=1&sn=becba16988f25998d910bc27016de015&chksm=a69dac6d91ea257bea56e75e41c5fd06a3dee892c2a2f57e22202402b68931463adf471bcb13&scene=21#wechat_redirect)

* [基于Hash散列，数据库路由组件设计](https://bugstack.cn/itstack-ark-middleware/2021/08/19/%E5%9F%BA%E4%BA%8EHash%E6%95%A3%E5%88%97-%E6%95%B0%E6%8D%AE%E5%BA%93%E8%B7%AF%E7%94%B1%E7%BB%84%E4%BB%B6%E8%AE%BE%E8%AE%A1.html)

* [无限容量数据库架构设计](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651960378&idx=1&sn=971a8db3251a232e3feeb7ff6235c96b&chksm=bd2d01e68a5a88f0f05c184340bcda81125ed1de772b35ef12b34c1f5f81c7b5a60cb8047f3c&scene=25#wechat_redirect)

* [支撑日活百万用户的高并发系统，应该如何设计其数据库架构](https://juejin.im/post/5c6a9f25518825787e69e70a)
* [史上最全近百条Oracle DBA日常维护SQL脚本指令](https://mp.weixin.qq.com/s?__biz=MjM5MDAxOTk2MQ==&mid=2650281305&idx=1&sn=0acc5cd128667d9bd21eabd90bfcc90d&chksm=be478d4f893004596a9c203d43184f7aa74f64955f9f3659dc206a06233a6fdd2c3217d49958&scene=21#wechat_redirect)
* [为什么这么设计系列----为什么数据库不应该使用外键](https://draveness.me/whys-the-design-database-foreign-key/)
