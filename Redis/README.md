
# 目录
* [Redis概述](#Redis概述)
* [Redis 数据结构和底层实现](#Redis-数据结构和底层实现)
* [持久化方式](#持久化方式)
* [分布式方案](#分布式方案)

# 已安装Redis
安装目录
c:\redis-2.4.5-win32-win64

# 问题

* Redis缓存穿透原理与解决方案



# 内容

## Redis概述

目前使用Redis，我看到有的公司使用的是memcache，这个10年前，就这屌样，功能非常的简陋不说，主要一个问题是会有死缓存，就是缓存怎么也清空不了，这个你想想就知道多悲剧了，商家修改了价格，怎么也改不了，最后只能关闭机器重启。还有的公司使用的还是hibernate提供的ehcache，这个大家自行了解即可，关键是他做集群有问题，搞电商不可能是单机的，刚上线至少是2台服务器。



## Redis 数据结构和底层实现

   
## 持久化方式

   持久化方式主要分两种，aof和rdb, 前者基于追加日志的方式来实实现日志持久化，后者则是使用备份数据的方式来实现持久化

## 分布式方案

   Redis可以使用主从的方式部署，其中“哨兵”这一组件用于故障切换。
   基于哨兵的主从部署后来发展为Redis cluster的部署方式，也就是Redis集群，通过分片的方式来部署Redis集群，并集群中任一节点都可用来对外提供服务。
   当然，除了Redis集群外，还有codis的分布式方案，codis基于代理的方式来实现，表面上还是使用原来的Redis API,但实际上访问的却是一个Redis集群。


# 有用的参考
* [Redis官网](https://redis.io/)
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


