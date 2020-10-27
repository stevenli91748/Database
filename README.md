# [Database 面试](https://github.com/stevenli91748/Database/blob/master/Interview.md)

[芋道源码---数据库实体设计](http://svip.iocoder.cn/categories/%E6%95%B0%E6%8D%AE%E5%BA%93%E5%AE%9E%E4%BD%93%E8%AE%BE%E8%AE%A1/)|[数据库设计](https://www.cnblogs.com/zping/category/147365.html)|[Database Design Course - Learn how to design and plan a database for beginners](https://www.youtube.com/watch?v=ztHopE5Wnpc&t=43s)|
---|---|---|

[常用数据库建模工具](https://blog.csdn.net/wren2004/article/details/79554817)|[关于电商网站数据库的设计](https://www.zhihu.com/question/27607346)|[研发库表设计规范](https://www.jianshu.com/p/4b0d82c817fa)|
---|---|---|

[超给力，一键生成数据库文档-数据库表结构逆向工程](http://www.zimug.com/java/spring/%e8%b6%85%e7%bb%99%e5%8a%9b%ef%bc%8c%e4%b8%80%e9%94%ae%e7%94%9f%e6%88%90%e6%95%b0%e6%8d%ae%e5%ba%93%e6%96%87%e6%a1%a3-%e6%95%b0%e6%8d%ae%e5%ba%93%e8%a1%a8%e7%bb%93%e6%9e%84%e9%80%86%e5%90%91%e5%b7%a5/.html)|
---|

[Database Design Course](https://www.youtube.com/watch?v=ztHopE5Wnpc)|
---|


# 目录
* [数据库概述](#数据库概述)
* [JDBC](https://github.com/stevenli91748/Database/blob/master/JDBC/README.md)
* [关系数据库](https://github.com/stevenli91748/Database/blob/master/关系数据库/README.md)
  * [MySQL](https://github.com/stevenli91748/Database/blob/master/MySQL/README.md)
  * [Mariadb](https://github.com/stevenli91748/Database/blob/master/Mariadb/README.md)
  * PostgreSQL
  * ORACLE
  * [Mybatis](https://github.com/stevenli91748/Database/blob/master/Mybatis/README.md)
* [NON-SQL Database](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/NoSQL数据库集群.md)
  * K-V存储---解决关系数据库无法存储数据结构的问题，以Redis 为代表
    * [Redis](https://github.com/stevenli91748/Database/blob/master/Redis/README.md)
  * 文档数据库---解决关系数据库强schema 约束的问题，以MongoDB 为代表
    * [MongoDB](https://github.com/stevenli91748/Database/blob/master/MongoDB/README.md)  
  * 列式数据库： 解决关系数据库大数据场景下的I/O 问题，以HBase 为代表
    * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
  * 全文搜索引擎：解决关系数据库的全文搜索性能问题，以Elasticsearch 为代表
    * [Elasticsearch](https://github.com/stevenli91748/Database/blob/master/Elasticsearch/README.md)
  * Memcache
  * 图数据库 Neo4j
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
## 数据库概述

数据库的高性能方案有：优化当前数据库，和建立集群。
当数据库开始出现性能下降的时候，最优先的方案是：优化当前数据库的性能，而非立刻建立集群。应该保持简单原则，毕竟会增加很大复杂度。

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

 * [一堂课带你精通~数据库连接池编程思想与实现](https://www.bilibili.com/video/av58455529)

# 有用的参考
 * [面试官扎心一问：数据量很大，分页查询很慢，有什么优化方案？](https://zhuanlan.zhihu.com/p/169599922?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
 * [数据库并发控制](https://zhuanlan.zhihu.com/p/168672853?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
 * [如何设计能支撑百万并发的数据库架构？](http://www.52im.net/thread-2510-1-1.html)
 * [不用找了，大厂在用的分库分表方案，都在这里！](https://www.jianshu.com/p/5b2bb76d26d6)
 * [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [学习数据库从入门到进阶书籍pdf版吐血整理推荐（珍藏版）](https://pymlovelyq.github.io/2018/10/12/database/)

* [如何设计一个数据库中间件](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483731&idx=1&sn=becba16988f25998d910bc27016de015&chksm=a69dac6d91ea257bea56e75e41c5fd06a3dee892c2a2f57e22202402b68931463adf471bcb13&scene=21#wechat_redirect)

* [无限容量数据库架构设计](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651960378&idx=1&sn=971a8db3251a232e3feeb7ff6235c96b&chksm=bd2d01e68a5a88f0f05c184340bcda81125ed1de772b35ef12b34c1f5f81c7b5a60cb8047f3c&scene=25#wechat_redirect)

* [支撑日活百万用户的高并发系统，应该如何设计其数据库架构](https://juejin.im/post/5c6a9f25518825787e69e70a)
* [史上最全近百条Oracle DBA日常维护SQL脚本指令](https://mp.weixin.qq.com/s?__biz=MjM5MDAxOTk2MQ==&mid=2650281305&idx=1&sn=0acc5cd128667d9bd21eabd90bfcc90d&chksm=be478d4f893004596a9c203d43184f7aa74f64955f9f3659dc206a06233a6fdd2c3217d49958&scene=21#wechat_redirect)
