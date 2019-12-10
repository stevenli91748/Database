# [Database 面试](https://github.com/stevenli91748/Database/blob/master/Interview.md)


# 目录
* [数据库概述](#数据库概述)
* [JDBC](https://github.com/stevenli91748/Database/blob/master/JDBC/README.md)
* [关系数据库](https://github.com/stevenli91748/Database/blob/master/关系数据库/README.md)
  * MySQL
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
* Distribute Database
* [缓存系统](https://github.com/stevenli91748/Database/blob/master/缓存系统/README.md)
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
 * [如何设计能支撑百万并发的数据库架构？](http://www.52im.net/thread-2510-1-1.html)
 
 * [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [学习数据库从入门到进阶书籍pdf版吐血整理推荐（珍藏版）](https://pymlovelyq.github.io/2018/10/12/database/)

* [如何设计一个数据库中间件](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483731&idx=1&sn=becba16988f25998d910bc27016de015&chksm=a69dac6d91ea257bea56e75e41c5fd06a3dee892c2a2f57e22202402b68931463adf471bcb13&scene=21#wechat_redirect)

* [无限容量数据库架构设计](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651960378&idx=1&sn=971a8db3251a232e3feeb7ff6235c96b&chksm=bd2d01e68a5a88f0f05c184340bcda81125ed1de772b35ef12b34c1f5f81c7b5a60cb8047f3c&scene=25#wechat_redirect)

* [支撑日活百万用户的高并发系统，应该如何设计其数据库架构](https://juejin.im/post/5c6a9f25518825787e69e70a)
