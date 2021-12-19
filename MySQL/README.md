**在MySQL的集群设计中，首先使用主从同步设计构建数据库集群，然后将这种集群以分组的形式通过主主同步实现高可用设计。而对数据库的访问，将使用OneProxy数据库代理中间件实现读写分离设计。最后，对OneProxy的调用，还将使用LVS（Linux Virtual Server，Linux虚拟服务器）技术构建一个双机热备的访问机制。LVS将提供一个虚拟的广播IP地址，即以VIP地址的形式对外提供服务**



# [MySQL数据库面试题](https://github.com/stevenli91748/Database/blob/master/MySQL/Interview/README.md)

# [MySQL名词解析](https://github.com/stevenli91748/Database/blob/master/MySQL/MySQL%E5%90%8D%E8%AF%8D%E8%A7%A3%E6%9E%90/README.md)

# 在线书籍
* [MySQL技术大全： 开发， 优化与运维实战---冰河  非常好 首先看 2021 ](https://weread.qq.com/web/reader/bd032100721bc56bbd056ff)
* [MySQL可扩展分布式数据库集群的搭建](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714k07e323f027707e1cd7dc674)
* [MySQL8 DBA基础教程](https://weread.qq.com/web/reader/074321d0721247d50747fbb)
* [MySQL技术内幕： SQL 编程](https://weread.qq.com/web/reader/46d32a3059335d46d02eba6)
* [MySQL技术内幕：InnoDB存储引擎（第2版）](https://weread.qq.com/web/reader/611329b059346e611427f1c)
* [深入浅出MySQL: 数据库开发，优化与管理维护 （第2版）](https://weread.qq.com/web/reader/f3e327e05b25c1f3e6d5ee2)




[公司用的 MySQL 团队开发规范，太详细了，建议收藏](https://mp.weixin.qq.com/s/Y1OTWxiYrQpihezaiydjcw)|[]()|
---|---|

[MySQL快速教程：MySQL数据库学习宝典（从入门到精通）](http://c.biancheng.net/mysql/)|[MySQL快速教程：MySQL函数大全，MySQL常用函数汇总](http://c.biancheng.net/mysql/function/)|
---|---|

[SQL快速教程](https://www.w3schools.com/sql/sql_top.asp)|[我的 MySQL 学习之路](https://mp.weixin.qq.com/s?__biz=Mzg2NzA4MTkxNQ==&mid=2247494510&idx=1&sn=437dc5527337857b1fc34fc2967643f4&chksm=ce43a0baf93429ac18176eab75eca1a6c1a2440506e71287a6b562c92cbab40c49aaaed5ff67&scene=132#wechat_redirect)|
---|---|

[精尽 MySQL 学习指南](http://svip.iocoder.cn/MySQL/tutorials/)|[Xtrabackup实现数据的备份与恢复](https://www.kancloud.cn/suixiaofeng/linux/791378)|[在线SQL测试](https://www.liaoxuefeng.com/wiki/1177760294764384/1179611432985088)|
---|---|---|

[MySQL20个高性能架构设计原则（值得收藏）](http://www.xknote.com/mysql/5swdtf.html)|[MySQL实践手册---提供Java、MySQL数据库、Web基础和Java Web开发的系统学习，提供配套的企业级项目实践案例](https://www.kancloud.cn/ynedu/mysql1/2394345)|
---|---|

[mysql数据库的免费测试数据生成器](https://www.coder.work/article/144956)|
---|


# 案例

* [我们讲解如何通过代码调用MySQL的备份还原命令实现系统备份还原的功能](https://weread.qq.com/web/reader/9593218071950312959b681kea532350240ea5d2f1c4357)


# 目录
  * [1. MySQL基础部分](#1-MySQL基础部分)
    * [MySQL三大范式](https://weread.qq.com/web/reader/bd032100721bc56bbd056ffk9bf32f301f9bf31c7ff0a60) 
    * [MySQL存储引擎---不同的存储引擎提供的存储机制、索引的存放方式和锁粒度等不同](https://weread.qq.com/web/reader/bd032100721bc56bbd056ffkc7432af0210c74d97b01b1c)
    * [SQL执行流程](https://weread.qq.com/web/reader/bd032100721bc56bbd056ffk65132ca01b6512bd43d90e3) 
  * [2. MySQL高级部分](#2-MySQL高级部分)
  * [3 MySQL故障处理](#3-MySQL故障处理)
  * [4 MySQL Tools](#4-MySQL-Tools)
  * [5 MySQL事务](#5-MySQL事务])
  * 6 MySQL 的架构设计  
    * [MySQL的架构设计](https://zhuanlan.zhihu.com/p/150583672)
    * [MySQL数据库之互联网常用架构方案（全）](https://zhuanlan.zhihu.com/p/98546065) 

# 1 MySQL基础部分

* MySQL安装
  * [MySQL Linux安装](https://github.com/stevenli91748/Database/blob/master/MySQL/MySQL%20Linux安装/README.md)
  * [MySQL Docker安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装MySQL/README.md)
  * [Percona Server 5.7 源码安装](https://www.cnblogs.com/knmax/p/9211450.html)

* linux启动 MySQL数据库的几种方式
  * 启动MySQL服务端程序的方式
    * mysqld---mysqld这个可执⾏⽂件就代表着MySQL服务器程序，运⾏这个可执⾏⽂件就可以直接启动⼀个服务器进程, 可指定自定义端口： mysqld -P3307（大写的P）,默认是3306
    * mysqld_safe---mysqld_safe是⼀个启动脚本，它会间接的调⽤mysqld，⽽且还顺便启动了另外⼀个监控进程，这个监控进程在服务器进程挂了的时候，可以帮助重启它。另外，使⽤mysqld_safe启动服务
                    器程序时，它会将服务器程序的出错信息和其他诊断信息重定向到某个⽂件中，产⽣出错⽇志，这样可以⽅便我们找出发⽣错误的原因
    * mysqld_multi---其实我们⼀台计算机上也可以运⾏多个服务器实例，也就是运⾏多个MySQL服务器进程。mysql_multi可执⾏⽂件可以对每⼀个服务器进程的启动或停⽌进⾏监控
    * mysql.server---mysql.server也是⼀个启动脚本，它会间接的调⽤mysqld_safe，在调⽤mysql.server时在后边指定start参数就可以启动服务器程序了， mysql.server start or mysql.server stop
  * 启动MySQL客户端程序的方式 
    *  mysql -h主机名 -u⽤户名 -p密码       
    *  mysql --user=root --password=gz19731108
    *  mysql -u root -p gz19731108 
* Windos启动 MySQL数据库的几种方式
  * 启动MySQL服务端程序的方式
    * 手动启动---在MySQL安装⽬录下的bin⽬录下有⼀个mysqld可执⾏⽂件，在命令⾏⾥输⼊mysqld，或者直接双击运⾏它就算启动了MySQL服务器程序了
    * 以服务的形式启动---需要在计算机启动的时候便启动它，⼀般我们都会把它注册为⼀个Windows 服务，把某个程序注册为Windows服务的⽅式挺简单:
                       "完整的可执⾏⽂件路径" --install [-manual] [服务名]，例如 "C:\Program Files\MySQL\MySQL Server5.7\bin\mysqld" --install， 在把mysqld注册为Windows服务之后，
                       我们就可以通过下边这个命令( net start MySQL )来启动MySQL服务器程序, 或 关闭 （net stop MySQL）
* MySQL启动选项和配置⽂件
  * MySQL启动选项
    * MySQL服务端启动选项
    * MySQL客户端启动选项
  * MySQL配置⽂件
    * MySQL服务端配置⽂件
    * MySQL客户端配置⽂件

* [MySQL内部架构](#MySQL内部架构)
* [MySQL索引](#MySQL索引)



## MySQL内部架构

* MySQL客户端与服务器连接的过程---MySQL⽀持下边三种客户端进程和服务器进程的通信⽅式
  * TCP/IP--- 可用命令 mysql -h127.0.0.1 -uroot -P3307 -p
  * 命名管道和共享内存---在Windows 系统中使用
                       命名管道需要在启动服务器程序的命令中加上--enable-named-pipe参数，然后在启动客户端程序的命令中加⼊--pipe或者--protocol=pipe参数
                       共享内存需要在启动服务器程序的命令中加上--shared-memory参数，在成功启动服务器后，共享内存便成为本地客户端程序的默认连接⽅式，不过我们也可以在启动客户端程序的命令中加
                       ⼊--protocol=memory参数来显式的指定使⽤共享内存进⾏通信，不过需要注意的是，使⽤共享内存的⽅式进⾏通信的服务器进程和客户端进程必须在同⼀台Windows主机中
  * Unix域套接字⽂件--- 在unix 系统中使用
                       启动服务端程序时指定socket参数： mysqld --socket=/tmp/a.txt
                       启动客户端程序： mysql -hlocalhost -uroot --socket=/tmp/a.txt -p
                       这样该客户端进程和服务器进程就可以通过路径为/tmp/a.txt的Unix域套接字⽂件进⾏通信了
* 服务器处理客户端请求
  * 连接管理---客户端进程可以采⽤我们上边介绍的TCP/IP、命名管道或共享内存、Unix域套接字这⼏种⽅式之⼀来与服务器进程建⽴连接，每当有⼀个客户端进程连接到服务器进程时，服务器进程都会创建⼀个
              线程来专⻔处理与这个客户端的交互，当该客户端退出时会与服务器断开连接，服务器并不会⽴即把与该客户端交互的线程销毁掉，⽽是把它缓存起来，在另⼀个新的客户端再进⾏连接时，把这个缓
              存的线程分配给该新客户端。这样就起到了不频繁创建和销毁线程的效果，从⽽节省开销。从这⼀点⼤家也能看出，MySQL服务器会为每⼀个连接进来的客户端分配⼀个线程，在客户端程序发起连接的
              时候，需要携带主机信息、⽤户名、密码，服务器程序会对客户端程序提供的这些信息进⾏认证，如果认证失败，服务器程序会拒绝连接。另外，如果客户端程序和服务器程序不运⾏在⼀台计算机上，
              我们还可以采⽤使⽤了SSL（安全套接字）的⽹络连接进⾏通信，来保证数据传输的安全性。当连接建⽴后，与该客户端关联的服务器线程会⼀直等待客户端发送过来的请求
  * 解析与优化
    * 查询缓存---MySQL服务器程序处理查询请求的过程也是这样，会把刚刚处理过的查询请求和结果缓存起来，如果下⼀次有⼀模⼀样的请求过来，直接从缓存中查找结果就好了，就不⽤再傻呵呵的去底层的表中查
                找了。这个查询缓存可以在不同客户端之间共享，也就是说如果客户端A刚刚查询了⼀个语句，⽽客户端B之后发送了同样的查询请求，那么客户端B的这次查询就可以直接使⽤查询缓存中的数据，如
                果两个查询请求在任何字符上的不同（例如：空格、注释、⼤⼩写），都会导致缓存不会命中。另外，如果查询请求中包含某些系统函数、⽤户⾃定义变量和函数、⼀些系统表，如 mysql 、
                information_schema、performance_schema 数据库中的表，那这个请求就不会被缓存，MySQL的缓存系统会监测涉及到的每张表，只要该表的结构或者数据被修改，如对该表使⽤了INSERT
                UPDATE、DELETE、TRUNCATE TABLE、ALTERTABLE、DROP TABLE或 DROP DATABASE语句，那使⽤该表的所有⾼速缓存查询都将变为⽆效并从⾼速缓存中删除！
    * 语法解析---如果查询缓存没有命中，接下来就需要进⼊正式的查询阶段了。因为客户端程序发送过来的请求只是⼀段⽂本⽽已，所以MySQL服务器程序⾸先要对这段⽂本做分析，判断请求的语法是否正确，然后
                从⽂本中将要查询的表、各种查询条件都提取出来放到MySQL服务器内部使⽤的⼀些数据结构上来
    * 查询优化---语法解析之后，服务器程序获得到了需要的信息，⽐如要查询的列是哪些，表是哪个，搜索条件是什么等等，但光有这些是不够的，因为我们写的MySQL语句执⾏起来效率可能并不是很⾼，MySQL的
                优化程序会对我们的语句做⼀些优化，如外连接转换为内连接、表达式简化、⼦查询转为连接吧啦吧啦的⼀堆东⻄。优化的结果就是⽣成⼀个执⾏计划，这个执⾏计划表明了应该使⽤哪些索引进⾏
                查询，表之间的连接顺序是啥样的。
  * 存储引擎
    
    为了管理⽅便，⼈们把连接管理、查询缓存、语法解析、查询优化这些并不涉及真实数据存储的功能划分为MySQL server的功能，把真实存取数据的功能划分为存储引擎的功能。各种不同的存储引擎向上边的
    MySQL server层提供统⼀的调⽤接⼝（也就是存储引擎API），包含了⼏⼗个底层函数 ， 所以在MySQL server完成了查询优化后，只需按照⽣成的执⾏计划调⽤底层存储引擎提供的API，获取到数据后返回
    给客户端就好了         
    
    * 常⽤存储引擎
      * InnoDB(默认的存储引擎)
      * MyISAM(常用)
      * Memory
    * 存储引擎的⼀些操作
      * 查看当前服务器程序⽀持的存储引擎
      * 设置表的存储引擎---我们可以为不同的表设置不同的存储引擎，也就是说不同的表可以有不同的物理存储结构，不同的提取和写⼊⽅式
        * 创建表时指定存储引擎
        * 修改表的存储引擎
    
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

---

# 2 MySQL高级部分

* [2a MySQL主从复制](#2a-MySQL主从复制)
* [2b MySQL分库分表](#2b-MySQL分库分表)
* [2c Mysql读写分离](#2c-Mysql读写分离)
* [2d MySQL之备份与恢复](#2d-MySQL之备份与恢复)
* [2e MySQL索引](#2e-MySQL索引)
* [2f MySQL优化](#2f-MySQL优化)
* [2g MySQL架构设计](#2g-MySQL架构设计)
* [2h MySQL数据库代理中间件](#2h-MySQL数据库代理中间件)

## 2g MySQL架构设计
* [2ga MySQL集群](#2ga-MySQL集群)
* [2gb MySQL高可用架构设计](#2gb-MySQL高可用架构设计)
* [2gc MySQL高性能架构设计](#2gc-MySQL高性能架构设计)
* [2gd MySQL可展设计](#2gd-MySQL可展设计)

## 2a MySQL主从复制

**MySQL的主从同步设置是将主机设定为可读写服务器，将从机设定为只读服务器，从机的数据是从主机中同步过来的**


* [可扩展分布式数据库集群的搭建](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714k07e323f027707e1cd7dc674)
* [数据库中间件详解（精品长文）](https://zhuanlan.zhihu.com/p/87144535)
* [MySQL主从集群搭建](https://juejin.cn/post/6996986472809103391)
* [MYSQL 主从同步详解](https://juejin.cn/post/6920477753368117261)

[MySQL主从结构](https://www.bilibili.com/video/av61935013?from=search&seid=11244131792888282581)|[打造基于Docker的MySQL主从复制](https://www.bilibili.com/video/BV1kp411R7uF)|[MySQL主从复制，每秒完成30万订单](https://www.bilibili.com/video/BV1Q4411X7y8)|
---|---|---|




[MySQL主从同步延迟调查](https://zhuanlan.zhihu.com/p/36501637?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|

## 2b MySQL分库分表

* [数据库中间件详解（精品长文）](https://zhuanlan.zhihu.com/p/87144535)
* [如何实现多数据源读写分离？这是我看过最详细的一篇！！](https://zhuanlan.zhihu.com/p/309314866)

[2020最新技术ShardingJDBC 分库分表 -吊打MyCat](https://www.bilibili.com/video/BV1nT4y157Xp/?spm_id_from=333.788.videocard.1)|[2020面试一线大厂必问的数据库分库分表教程全集（mysql+mycat)](https://www.bilibili.com/video/BV1vJ41187E1/?spm_id_from=333.788.videocard.1)|
---|---|

## 2c Mysql读写分离

* [数据库中间件详解（精品长文）](https://zhuanlan.zhihu.com/p/87144535)

[Mysql读写分离](https://www.bilibili.com/video/BV1r4411B7pv/?spm_id_from=333.788.videocard.0)|[基于MyCat实现MySQL读写分离](https://www.bilibili.com/video/BV1BE411e7w3/?spm_id_from=333.788.videocard.0)|[100分钟掌握高可用架构实战MySQL读写分离技术全集](https://www.bilibili.com/video/BV1J4411o7y4/?spm_id_from=333.788.videocard.3)|
---|---|---|

## 2d MySQL之备份与恢复

## 2e MySQL索引

[阿里P8架构师，100分钟讲透MySQL索引底层原理！](https://www.bilibili.com/video/BV1BJ411i7WR/?spm_id_from=333.788.videocard.5)|[MySQL索引背后的数据结构及算法原理](https://www.kancloud.cn/kancloud/theory-of-mysql-index/41846)|
---|---|

[MySQL索引优化，explain讲得非常清楚了](https://www.jianshu.com/p/4f8ab1b85059)|[Mysql篇之索引原理](https://www.jianshu.com/p/73cd9288a652)|[无语，我差点被面试官怼坏了，又给我问到MySQL索引](https://www.jianshu.com/p/c82148473235)|
---|---|---|

[数据库两大神器【索引和锁】](https://juejin.im/post/5b55b842f265da0f9e589e79)|[MySql大表分页(附独门秘技)](http://ifeve.com/mysql%e5%a4%a7%e8%a1%a8%e5%88%86%e9%a1%b5%e9%99%84%e7%8b%ac%e9%97%a8%e7%a7%98%e6%8a%80/)|
---|---|



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


## 2h MySQL数据库代理中间件

* [MySQL数据库代理中间件选择](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714k2023270027b202cb962a56f)
  * Mycat---MyCat在大流量访问中有极佳的性能表现，它是用Java语言开发的，配置文件使用XML的形式，稍显复杂，特别是它的分区表的配置有点累赘。另外，一些用户对它的稳定性也颇有微词
  * [OneProxy---OneProxy是一款基于MySQL官方的Proxy中间件的设计思想开发的，运行稳定性好，配置也较为简单，分区表的概念与MySQL分区表的设置在根本上是一致的](https://weread.qq.com/web/reader/ca932ea071d7c798ca9a714kc8f3245027cc8ffe9a588b8)
  * [MySql DAL中间件总结](https://zhuanlan.zhihu.com/p/91742429)
---

# 3 MySQL故障处理

[MySQL 故障处理案例](https://www.cnblogs.com/zping/category/1239555.html)|
---|

---

# 4 MySQL Tools
[SQLyog](https://github.com/stevenli91748/Database/blob/master/SQLyog/README.md)|Navicat|
---|---|

# 5 MySQL事务

 * [面试官：你说对MySQL事务很熟？那我问你10个问题](https://mp.weixin.qq.com/s/gAttYA4XfZHwOcYkzyMRZQ)

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
* [数据库中间件详解（精品长文）](https://zhuanlan.zhihu.com/p/87144535)
* [MySQL进阶及优化](https://www.cnblogs.com/Courage129/category/1890813.html)
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

