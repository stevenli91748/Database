
# [Redis面试](https://github.com/stevenli91748/Database/blob/master/Redis/Interview/README.md)

[精尽 Redis 学习指南](http://svip.iocoder.cn/Redis/tutorials/)|[中华石杉---100讲带你实战基于Redis的高并发预约抢购系统](https://apppukyptrl1086.pc.xiaoe-tech.com/detail/p_6017ef53e4b035d3cdb58eac/6)|
---|---|

[Redis linux系统安装](https://github.com/stevenli91748/Database/blob/master/Redis/Redis%20linux系统安装/README.md)|[Redis Docker系统安装](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/在Docker安装Redis/README.md)|[Redis 的完整安装过程](https://www.chensongxia.cn/265.html)|[redis集群搭建](https://www.kancloud.cn/suixiaofeng/linux/873408)|
---|---|---|---|

[阿里官方Redis开发规范！](https://zhuanlan.zhihu.com/p/149370312?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)|
---|

[手把手教你搭建 Redis 集群](https://mp.weixin.qq.com/s/EW2jl3WOLQWyfeBUk3JFnQ)|[使用redis-exporter对redis集群进行性能监控](https://www.kubernetes.org.cn/7616.html)|[100讲带你实战基于Redis的高并发预约抢购系统](https://apppukyptrl1086.pc.xiaoe-tech.com/detail/p_6017ef53e4b035d3cdb58eac/6)|
---|---|---|

[redis如何打造，实时统计分析平台](https://www.bilibili.com/video/BV17p411R7E9)|[系统架构基础组件开发，手写Redis连接池](https://www.bilibili.com/video/BV1Ls411p7jM)|
---|---|

[Spring Data Redis 最佳实践](https://www.jianshu.com/p/6eb4306ef365)|[Docker环境下秒建Redis集群，连SpringBoot也整上了](https://www.jianshu.com/p/ca06e437614f)|
---|---|

# 目录
* [Redis概述](#Redis概述)
* [Redis缺点](#Redis缺点)
* [Redis 数据结构和底层实现](#Redis-数据结构和底层实现)
  * [Redis从基础命令到实战之字符串类型](https://blog.csdn.net/autfish/article/details/51680004)
  * [Redis从基础命令到实战之散列类型(Hash)](https://blog.csdn.net/autfish/article/details/51684954)
  * [Redis从基础命令到实战之列表类型(List)](https://blog.csdn.net/autfish/article/details/51719263)
  * [Redis从基础命令到实战之集合类型(Set)](https://blog.csdn.net/autfish/article/details/51734686)
  * [Redis从基础命令到实战之有序集合类型(SortedSet)](https://blog.csdn.net/autfish/article/details/51743446)
* [redis存储对象与对象序列化详解](https://www.shuzhiduo.com/A/A7zgRDmPd4/)
* [持久化方式](#持久化方式)
* [分布式方案](#分布式方案)
* [Redis集群]()
  * [基于Redis5的集群搭建和使用](https://blog.csdn.net/autfish/article/details/89521682)
  * [集群模式]()
    * [主从模式]()
    * [sentinel（哨兵）模式]()
    * [cluster模式]()
  * [redis集群性能监控  ](https://www.kubernetes.org.cn/7616.html)

# 已安装Redis
安装目录
c:\redis-2.4.5-win32-win64

# 问题

* Redis缓存穿透原理与解决方案



# 内容

## Redis概述

目前使用Redis，我看到有的公司使用的是memcache，这个10年前，就这屌样，功能非常的简陋不说，主要一个问题是会有死缓存，就是缓存怎么也清空不了，这个你想想就知道多悲剧了，商家修改了价格，怎么也改不了，最后只能关闭机器重启。还有的公司使用的还是hibernate提供的ehcache，这个大家自行了解即可，关键是他做集群有问题，搞电商不可能是单机的，刚上线至少是2台服务器。K-V 存储的全称是Key-Value 存储，其中Key 是数据的标识，和关系数据库中的主键含义一样， Value
就是具体的数据。Red is 是K-V 存储的典型代表，它是一款开源（基于BSD 许可）的高性能K-V 缓存和存储系统。Redi s 的Value 是具体的数据结构，包括stri ng 、hash 、li st 、set 、sorted set 、bitmap 和hyperloglog ,所以常常被称为数据结构服务器。

## Redis缺点

      Red is 的缺点主要体现在并不支持完整的ACID 事务， Redis 虽然提供事务功能，但Redis的事务和关系数据库的事务不可同日而语， Redis 的事务只能保
      证隔离性和一致性CI 和C ），无法保证原子性和持久’1生CA 和D ）。具体实现原理如下：
      
      • 原子性
      
          Red is 事务不支持原子性， Redis 不支持回滚操作，事务中间一条命令执行失败，既不会导致前面己经执行的命令被回跤，也不会中断后面的命令的
          执行。
      
      • 一致性Red is 事务能够保证事务开始之前和事务结束以后，数据库的完整性没有被破坏。
      
      • 隔离性
          
          Redis 不存在多个事务的问题，因为Red is 是单进程单线程的工作模式。这种隔离性的方式也带来一个隐含的问题： 如果某个客户端通过事务提交了大
          
          量的命令，那么会阻塞其他客户端进行任何操作。
          
      • 持久性
          
          Red is 提供两种持久化的方式，即RDB 和AOF 。
          
          RDB 持久化只备份当前内存中的数据集，事务执行完毕时，其数据还在内存中，并未立即写入到磁盘，所以RDB 持久化不能保证Red is 事务的持久性。
          
          AOF 持久化是先执行命令，执行成功后再将命令追加到日志文件中。即使AOF 每次执行命令后立刻将日志文件刷盘，也可能丢失l 条命令数据，因此AOF 
          也不能严格保证Red is 事务的持久性

## Redis 数据结构和底层实现

   
## 持久化方式

   持久化方式主要分两种，aof和rdb, 前者基于追加日志的方式来实实现日志持久化，后者则是使用备份数据的方式来实现持久化

## 分布式方案

   Redis可以使用主从的方式部署，其中“哨兵”这一组件用于故障切换。
   基于哨兵的主从部署后来发展为Redis cluster的部署方式，也就是Redis集群，通过分片的方式来部署Redis集群，并集群中任一节点都可用来对外提供服务。
   当然，除了Redis集群外，还有codis的分布式方案，codis基于代理的方式来实现，表面上还是使用原来的Redis API,但实际上访问的却是一个Redis集群。



# Redis 视频
 * [千锋微服务2019最新Redis教程](https://www.bilibili.com/video/av49517046?from=search&seid=10204331567303013188)
 * [Redis-尚硅谷](https://www.bilibili.com/video/av51139549/?spm_id_from=333.788.videocard.3)
 * [Redis从入门到精通高级进阶精讲](https://www.bilibili.com/video/av64175711/?spm_id_from=333.788.videocard.7)
 * [一线互联网公司Redis应用场景及实例分析全集](https://www.bilibili.com/video/av65345121/?spm_id_from=333.788.videocard.7)
 * [最通俗易懂的Redis实战教程全套学习视频](https://www.bilibili.com/video/av69077771/?spm_id_from=333.788.videocard.10)
 * [Session复制与 Redis Session共享解决方案](https://www.bilibili.com/video/av24880545/?spm_id_from=333.788.videocard.0)
 * [Redis实现高并发分布式锁](https://www.bilibili.com/video/av50734378/?spm_id_from=333.788.videocard.13)
 * [Redis分布式锁实战,代码超详细剖析高并发多场景可能存在的问题](https://www.bilibili.com/video/av73272760)
 * [Redis源码分析分布式架构下带你看透分布式锁](https://www.bilibili.com/video/av73390230)
 * [80分钟彻底搞懂Java分布式Redis高并发分布式锁实战](https://www.bilibili.com/video/av65046089)
 * [分布式架构专题- Redis高并发分布式锁实站](https://www.bilibili.com/video/av60449651/?spm_id_from=333.788.videocard.7)
# 有用的参考
* [我是如何用Redis做实时订阅推送的](https://developer.51cto.com/art/202103/651593.htm)
* [Redis GEO 功能使用场景](https://www.chensongxia.cn/262.html)
* [Redis系列：高可用哨兵方案部署](https://cloud.tencent.com/developer/article/1720754?from=article.detail.1026003)
* [redis知识点汇总](https://www.cnblogs.com/Jtianlin/p/10259062.html)
* [redis的三种启动方式](https://blog.csdn.net/qq_36850813/article/details/91352284?utm_medium=distribute.pc_relevant.none-task-blog-baidulandingword-2&spm=1001.2101.3001.4242)
* [这可能是目前最全的Redis高可用技术解决方案](https://www.jianshu.com/p/7a6a7d20e9ad)
* [使用redis实现5万人同服的“相位技术”](https://zhuanlan.zhihu.com/p/166347236?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
* [面试中关于Redis的问题看这篇就够了](https://juejin.im/post/5ad6e4066fb9a028d82c4b66)
* [Redis官网](https://redis.io/)
* [面试官看了赞不绝口的Redis笔记](https://blog.csdn.net/qq_42322103/article/details/104159919?depth_1-utm_source=distribute.pc_feed.none-task&request_id=&utm_source=distribute.pc_feed.none-task)
* [一分钟搞定Windoｗs10下安装Redis 及如何使用redis可视化管理工具](https://blog.csdn.net/WYpersist/article/details/81211345)
* [十分钟搞定SpringBoot 和Redis 实战整合](https://blog.csdn.net/WYpersist/article/details/81221100)
* [Redis作者的网站](http://antirez.com/latest/0)
* [Redis 展模块](https://redis.io/modules)
* [Redis: under the hood--高质量的文章 带你一步步的阅读Redis源代码](https://pauladamsmith.com/articles/redis-under-the-hood.html)
* [Redis 的 4 大法宝，必学中间件！](https://mp.weixin.qq.com/s/nNBqaePFY2H9fR8KhyNigg)
* [史上最全 Redis 高可用解决方案总结](https://mp.weixin.qq.com/s/VjjEFyVOo2krICWBV3kEsg)
* [Redis 的 8 大应用场景！](https://mp.weixin.qq.com/s/dM3sMeWvTswAjG8WwtL0Rw)
* [Redis 为什么这么快？](https://mp.weixin.qq.com/s/75uewvZWpSzxRbVvOrcOcg)
* [Redis 常用操作命令，非常详细！](https://mp.weixin.qq.com/s/k-yBobqsm0kOzdhcrM-jmg)
* [为什么分布式一定要有Redis?](https://mp.weixin.qq.com/s/mmDo7_ogqxtoxwfKpe9cYg)
* [深度历险：Redis 内存模型详解](https://mp.weixin.qq.com/s/Gp6Ur7omGY6ZqDWygU2meQ)
* [Redis 高可用特性之 “持久化” 详解](https://mp.weixin.qq.com/s/_p9y8-s12TMqvg-vBohTRA)
* [Redis PK Memcached 哪个更牛叉？](https://mp.weixin.qq.com/s/2G8x80EkOsoZorRuWy9Udw)
* [Redis Linux 安装运行实战全记录](https://mp.weixin.qq.com/s/LPYtARH7gatQV8_WUm55hg)
* [Spring Data Redis 详解及实战](https://mp.weixin.qq.com/s/dFnP3URKidfwwFU5gCYAHw)
* [Redis 再牛逼，也得设置密码！](https://mp.weixin.qq.com/s/0rkyDbQL7AnR5qlYRpjP9Q)
* [Redis Cluster 官方集群搭建指南](https://mp.weixin.qq.com/s/JovHvVnNDWUwCF09UuWSeA)
* [Spring Boot Redis Cluster 实战干货](https://mp.weixin.qq.com/s/K0q8brB1ZAFz_bU50yu4NA)
* [Redis 如何分析慢查询操作？](https://mp.weixin.qq.com/s/VOmNjBQzzk3Tibyvse7T6A)
* [3 台机器搞定一个 Redis 高可用架构](https://mp.weixin.qq.com/s/fwmC4TM593SG25wl58Vpqg)
* [一个致命 Redis 命令，损失 400 万！](https://mp.weixin.qq.com/s/MzkvQG2mFyvTNegFX52ztg)
* [Redis 这么火，它都解决了哪些问题？](https://mp.weixin.qq.com/s/vzIJ9jlaQGcarNAAH2tkNg)
* [Redis中文网](http://www.redis.cn/)
* [redis 菜鸟教程](http://www.runoob.com/redis/redis-tutorial.html)
* [Redis集群实现原理探讨](https://tech.youzan.com/redisji-qun-shi-xian-yuan-li-tan-tao/)
* [拜托，面试请不要再问我Redis分布式锁的实现原理！](https://juejin.im/post/5bf3f15851882526a643e207)
* [为什么一定要有redis](https://zhuanlan.zhihu.com/p/59168140?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [Redis 入门到分布式实践](https://gitbook.cn/m/mazi/comp/column?columnId=5a55d8e232c7126d8482f5d2&utm_source=columnweixinshare&utm_campaign=Redis%20%E5%85%A5%E9%97%A8%E5%88%B0%E5%88%86%E5%B8%83%E5%BC%8F%E5%AE%9E%E8%B7%B5)
* [非常值得一看的35个Redis面试题总结](https://zhuanlan.zhihu.com/p/63209388?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
* [Spring-Boot-操作-Redis，三种方案全解析！](https://blog.csdn.net/u012702547/article/details/90746640)
* [Redis 主从集群搭建及哨兵模式配置](https://www.cnblogs.com/qinxu/p/9633418.html)
* [redis主从集群搭建及容灾部署(哨兵sentinel)](https://www.cnblogs.com/linuxbug/p/5131504.html)
* [你需要知道的那些 redis 数据结构（前篇）](https://blog.csdn.net/lpd_tech/article/details/92812425)
* [Redis 和 Memcached 有什么区别？Redis 的线程模型是什么？为什么单线程的 Redis 比多线程的 Memcached 效率要高得多？](https://www.javazhiyin.com/22943.html)
* [Redis 集群模式的工作原理能说一下么？在集群模式下，Redis 的 key 是如何寻址的？分布式寻址都有哪些算法？了解一致性 hash 算法吗？如何动态增加和删除一个节点？](https://www.javazhiyin.com/22957.html)
* [2019最详细的Redis集群架构视频教程](https://www.bilibili.com/video/av56352332/?spm_id_from=333.788.videocard.7)
* [你知道要用 Redis，却不知道怎么用 Redis](https://www.jianshu.com/p/9f338430da26)
* [介绍Redis的各种用途以及使用场景](https://blog.csdn.net/u011277123/article/details/78692603)
### 实战

* [企业级nosql数据库应用与实战-redis](https://www.cnblogs.com/keerya/p/8127716.html)
* [项目实战11—企业级nosql数据库应用与实战-redis的主从和集群](https://www.cnblogs.com/along21/p/8027206.html)
* [redis超强超详细的入门教程](https://blog.csdn.net/miss_mindada/article/details/79598704)
* [从单机到2000万QPS并发的Redis高性能缓存实践之路](http://www.52im.net/thread-1968-1-1.html)
