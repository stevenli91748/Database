
# [MySQL数据库面试题](https://github.com/stevenli91748/Database/blob/master/MySQL/Interview/README.md)

windows mysql8 安装目录

c:\mysql\mysql server 8.0

connectivity:
  PROTOCOL: TCP/IP            PORT : 3306         X protocol port : 33060
  
  windows service:  MySQL81
  
  account 1 : root          
  password : gz19731108

  account 2 : gzpengli
  
  password: gz19731108
  
  host: localhost
   
登录mysql 

方式一：

c:> cd \mysql\mysql server 8.0\bin

\mysql\mysql server 8.0\bin> mysql --user=root --password=gz19731108

mysql>


方式二：

c:> cd \mysql\mysql server 8.0\bin

\mysql\mysql server 8.0\bin> mysql -u root -p
enter password: 

mysql>


# 目录

[精尽 MySQL 学习指南](http://svip.iocoder.cn/MySQL/tutorials/)|
---|

* [1. MySQL基础部分](#1-MySQL基础部分)
* [2. MySQL高级部分](#2-MySQL高级部分)
* [3 MySQL故障处理](#3-MySQL故障处理)
* [4 MySQL Tools](#4-MySQL-Tools)

# 1 MySQL基础部分
  * [1a MySQL内部架构](#1a-MySQL内部架构)
  * [1b MySQL索引](#1b-MySQL索引)

[MySQL Linux安装](https://github.com/stevenli91748/Database/blob/master/MySQL/MySQL%20Linux安装/README.md)|[MySQL Docker安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)|[Percona Server 5.7 源码安装](https://www.cnblogs.com/knmax/p/9211450.html)|
---|---|---|

## 1a MySQL内部架构

[MySQL 内核的架构设计](https://zhuanlan.zhihu.com/p/150583672?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|[Mysql之架构设计](https://www.jianshu.com/p/192bc46c7fb2)|[支撑百万并发的数据库架构如何设计？](https://zhuanlan.zhihu.com/p/57802566?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|---|---|

[mySql的执行顺序和执行计划](https://zhuanlan.zhihu.com/p/174837654?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|

[MySQL8.0 的配置文件](https://blog.csdn.net/wm3tcw28/article/details/78942693?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.nonecase)|[MySQL 启动 登录 停止](https://github.com/stevenli91748/Database/blob/master/MySQL/MySQL%20%E5%90%AF%E5%8A%A8%20%E7%99%BB%E5%BD%95%20%E5%81%9C%E6%AD%A2.md)| [应用程序跟MySQL数据库连接的知识点](https://github.com/stevenli91748/Database/blob/master/MySQL/%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F%E8%B7%9FMySQL%E6%95%B0%E6%8D%AE%E5%BA%93%E8%BF%9E%E6%8E%A5%E7%9A%84%E7%9F%A5%E8%AF%86%E7%82%B9.md)|[MySQL核心知识点](https://zhuanlan.zhihu.com/p/64786634?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|---|---|---|

[SQL语法](https://github.com/stevenli91748/Database/blob/master/MySQL/SQL%E8%AF%AD%E6%B3%95.md)|[面试官突然问我MySQL存储过程，我竟然连基础都不会！（详细）](https://zhuanlan.zhihu.com/p/148939731?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|---|

[MySql数据库锁机制详解](https://zhuanlan.zhihu.com/p/65076956?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|[MySql连接数与线程池](https://cloud.tencent.com/developer/article/1502887)|
---|---|

##  1b MySQL索引

[MySQL索引优化，explain讲得非常清楚了](https://www.jianshu.com/p/4f8ab1b85059)|[Mysql篇之索引原理](https://www.jianshu.com/p/73cd9288a652)|[无语，我差点被面试官怼坏了，又给我问到MySQL索引](https://www.jianshu.com/p/c82148473235)|
---|---|---|

[数据库两大神器【索引和锁】](https://juejin.im/post/5b55b842f265da0f9e589e79)|
---|

---

# 2 MySQL高级部分

* [2a MySQL主从复制](#2a-MySQL主从复制)
* [2b MySQL分库分表](#2b-MySQL分库分表)
* [2c Mysql读写分离](#2c-Mysql读写分离)
* [2d MySQL之备份与恢复](#2d-MySQL之备份与恢复)
* [2e MySQL索引](#2e-MySQL索引)
* [2f MySQL优化](#2f-MySQL优化)
* [2g MySQL架构设计](#2g-MySQL架构设计)

## 2g MySQL架构设计
* [2ga MySQL集群](#2ga-MySQL集群)
* [2gb MySQL高可用架构设计](#2gb-MySQL高可用架构设计)
* [2gc MySQL高性能架构设计](#2gc-MySQL高性能架构设计)
* [2gd MySQL可展设计](#2gd-MySQL可展设计)

## 2a MySQL主从复制

[MySQL主从结构](https://www.bilibili.com/video/av61935013?from=search&seid=11244131792888282581)|[打造基于Docker的MySQL主从复制](https://www.bilibili.com/video/BV1kp411R7uF)|[MySQL主从复制，每秒完成30万订单](https://www.bilibili.com/video/BV1Q4411X7y8)|
---|---|---|

[MySQL主从同步延迟调查](https://zhuanlan.zhihu.com/p/36501637?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|

## 2b MySQL分库分表

[2020最新技术ShardingJDBC 分库分表 -吊打MyCat](https://www.bilibili.com/video/BV1nT4y157Xp/?spm_id_from=333.788.videocard.1)|[2020面试一线大厂必问的数据库分库分表教程全集（mysql+mycat)](https://www.bilibili.com/video/BV1vJ41187E1/?spm_id_from=333.788.videocard.1)|
---|---|

## 2c Mysql读写分离

[Mysql读写分离](https://www.bilibili.com/video/BV1r4411B7pv/?spm_id_from=333.788.videocard.0)|[基于MyCat实现MySQL读写分离](https://www.bilibili.com/video/BV1BE411e7w3/?spm_id_from=333.788.videocard.0)|[100分钟掌握高可用架构实战MySQL读写分离技术全集](https://www.bilibili.com/video/BV1J4411o7y4/?spm_id_from=333.788.videocard.3)|
---|---|---|

## 2d MySQL之备份与恢复

## 2e MySQL索引

[阿里P8架构师，100分钟讲透MySQL索引底层原理！](https://www.bilibili.com/video/BV1BJ411i7WR/?spm_id_from=333.788.videocard.5)|
---|

## 2f MySQL优化

[MySQL线上SQL捕获及分析](https://www.youtube.com/watch?v=s4J4j4rV510)|[Oracle 和 MySQL 的 JDBC 到底有多慢？](https://zhuanlan.zhihu.com/p/103172180?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|[MySQL性能调优笔记](https://shimo.im/docs/kTXQQpYR8YdWWtWj/read?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)|
---|---|---|

[SQL优化（MySQL版；不适合初学者，需有数据库基础）](https://www.bilibili.com/video/BV1es411u7we?from=search&seid=13358875494782349964)|[基于案例学SQL优化 15课](https://www.bilibili.com/video/BV1Wt41177g6?from=search&seid=13358875494782349964)|[MySQL千万级别大表，你要如何优化？](https://www.jianshu.com/p/1bf3196ad1ac)|
---|---|---|

[如果是MySQL引起的CPU消耗过大，你会如何优化？](https://www.jianshu.com/p/1990261fca3f)|[MySQL 大表优化方案](https://zhuanlan.zhihu.com/p/113736497?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|---|

## 2gb MySQL高可用架构设计

[MySQL 高可用案例](https://www.cnblogs.com/zping/category/182631.html)|
---|

## 2gc MySQL高性能架构设计

[20个MySQL高性能架构设计原则](https://zhuanlan.zhihu.com/p/143991793?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|

## 2gd MySQL可展设计

## 2ga MySQL集群

[MySQL集群解决方案（主从复制、PXC集群、MyCat、HAProxy）](https://www.bilibili.com/video/BV1R4411s7zi/?spm_id_from=333.788.videocard.17)|[MySQL 高可用架构之 PXC 集群](https://juejin.cn/post/6844904039063224327)|[安装PXC集群在Docker](https://www.kancloud.cn/pm1028/kubenetes/1767444)|
---|---|---|

---

# 3 MySQL故障处理

[MySQL 故障处理案例](https://www.cnblogs.com/zping/category/1239555.html)|
---|

---

# 4 MySQL Tools
[SQLyog](https://github.com/stevenli91748/Database/blob/master/SQLyog/README.md)|Navicat|
---|---|



# Mysql视频
 * [mysql 8.0](https://www.youtube.com/channel/UCDV_54xfBb4aw0eJmvWLpsQ)
 * [千锋MySQL DBA入门全套教程（价值8980元）](https://www.bilibili.com/video/av78081101?from=search&seid=16011833382632023449)
 * [尚硅谷 MySQL 基础+高级篇- 数据库 -sql](https://www.bilibili.com/video/av49181542/?spm_id_from=333.788.videocard.3)
 * [MySQL数据库视频教程老杜最新MySQL教程](https://www.bilibili.com/video/av57575364/?spm_id_from=333.788.videocard.16)
 * [数据库 MySQL 视频教程全集](https://www.bilibili.com/video/av59623481/?spm_id_from=333.788.videocard.1)
 * [MySQL 国内知名BAT级DBA大神主讲 学完25万年薪起](https://www.bilibili.com/video/av62508600/?spm_id_from=333.788.videocard.11)
 * [MySQL大型分布式集群Mycat实战-龙果](https://www.bilibili.com/video/av53909897?from=search&seid=12773160558428482344)
 * [尚硅谷】Oracle/MySQL数据库核心技术详解（完）](https://www.bilibili.com/video/av62496628?from=search&seid=6481752262698197941)
* [基于Docker架构Mysql集群实战](https://www.bilibili.com/video/av64014661/?spm_id_from=333.788.videocard.1)
* [性能调优专题-mysql索引优化与底层数据结构深入剖析](https://www.bilibili.com/video/av60391294/?spm_id_from=333.788.videocard.3)
* [打造扛得住的MySQL数据库架构](https://www.bilibili.com/video/av80478890/?spm_id_from=333.788.videocard.7)
* [MyCAT+MySQL 搭建高可用企业级数据库集群](https://www.bilibili.com/video/av80477641/?spm_id_from=333.788.videocard.4)
# 有用的参考
* [Mysql双主热备+LVS+Keepalived高可用操作记录](https://cloud.tencent.com/developer/article/1025920?from=article.detail.1026003)
* [三万字、91道MySQL面试题和答案（2020收藏版）](https://zhuanlan.zhihu.com/p/114993399?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
* [MySQL 一次奇怪的故障分析](https://zhuanlan.zhihu.com/p/86599248?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
* [一千行 MySQL 详细学习笔记（值得学习与收藏](https://mp.weixin.qq.com/s?__biz=MzUyNDkzNzczNQ==&mid=2247485440&idx=1&sn=068d918afea5b554e5d944a4dc192048&chksm=fa24f768cd537e7e055f1c5d9a2b0868f04449877d7e4a9a2d26137f1201f92a35ddbb362119&scene=21#wechat_redirect)
* [MySQL的万字总结（缓存，索引，Explain，事务，redo日志等）](https://www.jianshu.com/p/2530d1185778)
* [MySQL数据库面试题（2020最新版）](https://blog.csdn.net/thinkwon/article/details/104778621#comments)
* [使用Keepalived实现MySQL双主高可用](https://www.linuxidc.com/Linux/2019-08/160164.htm)
* [Navicat for MySQL 安装和破解（完美）](https://blog.csdn.net/wypersist/article/details/79834490)
* [Mysql分库分表方案](https://www.javazhiyin.com/10518.html)
* [Centos7中MySQL的安装并设置开机启动](https://blog.csdn.net/yin767833376/article/details/85270563)
* [Mysql的分支mariadb 与percona server 哪个更适合生产环境](https://blog.csdn.net/xuheng8600/article/details/79947595)
* [史上最全的mysql基础教程](https://blog.csdn.net/weixin_45108087/article/details/102766281)
* [史上更全的MySQL高性能优化实战总结！](https://www.jianshu.com/p/c9f1625ecbb8)
* [可能是全网最好的MySQL重要知识点](https://www.jianshu.com/p/5dd5993f981b)
* [如何造10w条测试数据，在数据库插入10w条不同数据](https://www.jianshu.com/p/c65463798554)

* [《深入精通Mysql（一）》Mysql整体架构和sql执行过程（面试高频题）](https://zhuanlan.zhihu.com/p/100026210)
* [《深入精通Mysql（二）》深入底层剖析Mysql索引（面试必问](https://mp.weixin.qq.com/s/WDeYmrfgPHqg-fGI17qLcw)
* [《深入精通Mysql（二）》深入底层剖析Mysql各种锁机制（面试必问）](https://mp.weixin.qq.com/s/WgcLdEfjFE3CsWV4FgOefw)
* [《深入精通Mysql（四）》MySQL 事务机制，中高级开发面试必问](https://mp.weixin.qq.com/s/3Zk9Np5c9K0ENz64Y6E92g)
* [《深入精通Mysql（五）》实战：Mysql实现主从复制](https://mp.weixin.qq.com/s/pVAFJWydABPcDG0UR_S90A)
* [《深入精通Mysql（六）》系列之如何通过慢查询日志进行SQL分析和优化](https://mp.weixin.qq.com/s/qfNsNgA2RklvJ69pNhze5g)
* [深入精通Mysql（七）》系列之如何通过EXPLAIN 执行计划分析SQL语句的性能瓶](https://mp.weixin.qq.com/s/JFS48kVceqQEuhO2F1OQOQ)
* [《深入精通Mysql（八）》系列之十年架构师从架构层面进行Mysql性能优化](https://mp.weixin.qq.com/s/GzrWq-OHHFuxqYQjNesZlA)
