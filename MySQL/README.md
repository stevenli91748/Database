
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




# MySQL基础部分


[MySQL Linux安装](https://github.com/stevenli91748/Database/blob/master/MySQL/MySQL%20Linux安装/README.md)|[MySQL Docker安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)|[Percona Server 5.7 源码安装](https://www.cnblogs.com/knmax/p/9211450.html)|
---|---|---|


# MySQL高级部分

* [MySQL主从复制](#MySQL主从复制)
* [MySQL分库分表](#MySQL分库分表)
* [Mysql读写分离](#Mysql读写分离)
* [MySQL索引](#MySQL索引)
* [SQL优化](#SQL优化)
* [MySQL集群](#MySQL集群)

## MySQL主从复制

[MySQL主从结构](https://www.bilibili.com/video/av61935013?from=search&seid=11244131792888282581)|[打造基于Docker的MySQL主从复制](https://www.bilibili.com/video/BV1kp411R7uF)|[MySQL主从复制，每秒完成30万订单](https://www.bilibili.com/video/BV1Q4411X7y8)|
---|---|---|

## MySQL分库分表

[2020最新技术ShardingJDBC 分库分表 -吊打MyCat](https://www.bilibili.com/video/BV1nT4y157Xp/?spm_id_from=333.788.videocard.1)|[2020面试一线大厂必问的数据库分库分表教程全集（mysql+mycat)](https://www.bilibili.com/video/BV1vJ41187E1/?spm_id_from=333.788.videocard.1)|
---|---|

## Mysql读写分离

[Mysql读写分离](https://www.bilibili.com/video/BV1r4411B7pv/?spm_id_from=333.788.videocard.0)|[基于MyCat实现MySQL读写分离](https://www.bilibili.com/video/BV1BE411e7w3/?spm_id_from=333.788.videocard.0)|[100分钟掌握高可用架构实战MySQL读写分离技术全集](https://www.bilibili.com/video/BV1J4411o7y4/?spm_id_from=333.788.videocard.3)|
---|---|---|

## MySQL索引

[阿里P8架构师，100分钟讲透MySQL索引底层原理！](https://www.bilibili.com/video/BV1BJ411i7WR/?spm_id_from=333.788.videocard.5)|
---|

## SQL优化

[SQL优化（MySQL版；不适合初学者，需有数据库基础）](https://www.bilibili.com/video/BV1es411u7we?from=search&seid=13358875494782349964)|[基于案例学SQL优化 15课](https://www.bilibili.com/video/BV1Wt41177g6?from=search&seid=13358875494782349964)|
---|---|

## MySQL集群

[MySQL集群解决方案（主从复制、PXC集群、MyCat、HAProxy）](https://www.bilibili.com/video/BV1R4411s7zi/?spm_id_from=333.788.videocard.17)|
---|


## MySQL Tools
[SQLyog](https://github.com/stevenli91748/Database/blob/master/SQLyog/README.md)|Navicat|
---|---|



# Mysql视频
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
