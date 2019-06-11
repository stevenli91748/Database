
<details>
<summary>Redis有哪些数据类型？</summary>

string，list，set，sorted set（Zset），hash

</details>

<details>
<summary>讲一讲Redis的常用场景</summary>

简单kv字符存储、Session会话记录、Token保持、热点数据存储、网页缓存、数据行缓存、排名、高速队列、分布式锁、计数器、发布订阅……

</details>

<details>
<summary>Redis如何设置密码及验证密码？</summary>

设置密码：config set requirepass 123456

授权密码：auth 123456

</details>

<details>
<summary>Redis集群方案应该怎么做？都有哪些方案？</summary>
  
1.twemproxy，大概概念是，它类似于一个代理方式，使用方法和普通redis无任何区别，设置好它下属的多个redis实例后，使用时在本需要连接redis的地方改为连接twemproxy，它会以一个代理的身份接收请求并使用一致性hash算法，将请求转接到具体redis，将结果再返回twemproxy。使用方式简便(相对redis只需修改连接端口)，对旧项目扩展的首选。 问题：twemproxy自身单端口实例的压力，使用一致性hash后，对redis节点数量改变时候的计算值的改变，数据无法自动移动到新的节点。
 

2.codis，目前用的最多的集群方案，基本和twemproxy一致的效果，但它支持在 节点数量改变情况下，旧节点数据可恢复到新hash节点。
 

3.redis cluster3.0自带的集群，特点在于他的分布式算法不是一致性hash，而是hash槽的概念，以及自身支持节点设置从节点。具体看官方文档介绍。
 

4.在业务代码层实现，起几个毫无关联的redis实例，在代码层，对key 进行hash计算，然后去对应的redis实例操作数据。 这种方式对hash层代码要求比较高，考虑部分包括，节点失效后的替代算法方案，数据震荡后的自动脚本恢复，实例的监控，等等。

</details>

<details>
<summary>mySQL里有2000w数据，redis中只存20w的数据，如何保证redis中的数据都是热点数据？</summary>
  
redis内存数据集大小上升到一定大小的时候，就会施行数据淘汰策略。

相关知识：redis 内存数据集大小上升到一定大小的时候，就会施行数据淘汰策略。redis 提供 6种数据淘汰策略：

voltile-lru：从已设置过期时间的数据集（server.db[i].expires）中挑选最近最少使用的数据淘汰

volatile-ttl：从已设置过期时间的数据集（server.db[i].expires）中挑选将要过期的数据淘汰

volatile-random：从已设置过期时间的数据集（server.db[i].expires）中任意选择数据淘汰

allkeys-lru：从数据集（server.db[i].dict）中挑选最近最少使用的数据淘汰

allkeys-random：从数据集（server.db[i].dict）中任意选择数据淘汰

no-enviction（驱逐）：禁止驱逐数据
  
</details>  

<details>
<summary>Redis和Redisson有什么关系？</summary>

Redisson是一个高级的分布式协调Redis客户端，能帮助用户在分布式环境中轻松实现一些Java的数据结构对象 (Bloom filter, BitSet, Set, SetMultimap, ScoredSortedSet, SortedSet, Map, ConcurrentMap, List, ListMultimap, Queue, BlockingQueue, Deque, BlockingDeque, Semaphore, Lock, ReadWriteLock, AtomicLong, CountDownLatch, Publish / Subscribe, HyperLogLog)

</details>  


<details>
<summary>Jedis 和Redisson同步异步IO的区别？</summary>

Jedis使用阻塞的I/O，且其方法调用都是同步的，程序流需要等到sockets处理完I/O才能执行，不支持异步。Jedis客户端实例不是线程安全的，所以需要通过连接池来使用Jedis。

Redisson使用非阻塞的I/O和基于Netty框架的事件驱动的通信层，其方法调用是异步的。Redisson的API是线程安全的，所以可以操作单个Redisson连接来完成各种操作。
  
</details>  


<details>
<summary>Redis集群的主从复制模型是怎样的？</summary>
  
为了使在部分节点失败或者大部分节点无法通信的情况下集群仍然可用，所以集群使用了主从复制模型,每个节点都会有N-1个复制品.

</details>  

<details>
<summary>Redis集群会有写操作丢失吗？为什么？</summary>
  
Redis并不能保证数据的强一致性，这意味这在实际中集群在特定的条件下可能会丢失写操作。

</details>  

<details>
<summary>Redis集群之间是如何复制的？</summary>
  
异步复制

</details>  

<details>
<summary>Redis集群最大节点个数是多少？</summary>
  
16384，即哈希槽的数量

</details>  

<details>
<summary>Redis哈希槽的概念？</summary>
  
Redis集群没有使用一致性hash,而是引入了哈希槽的概念，Redis集群有16384个哈希槽，每个key通过CRC16校验后对16384取模来决定放置哪个槽，集群的每个节点负责一部分hash槽。

</details>  


<details>
<summary>谈谈AOF中appendfsync各个选项的区别？</summary>
  
appendfsync always：每次操作都写入一次aof文件，并完成磁盘同步，强烈不建议使用，会严重降低Redis的写效率，甚至写入放大问题；

appendfsync everysec：默认的选项，每一秒写入aof文件，并显式完成磁盘同步

appendfsync no：写入aof文件，不等待磁盘同步，即由系统来决定写AOF文件，可能会带来数据丢失问题。

</details>  

<details>
<summary>谈谈如何解决AOF文件越来越膨胀的问题？</summary>
  
使用AOF 自动重写。即当AOF文件增长到一定大小的时候Redis能够调用 BGREWRITEAOF 对日志文件进行重写。它是这样工作的：Redis会记住上次进行写日志后文件的大小(如果从开机以来还没进行过重写，那日志大小在开机的时候确定)

基础大小会同现在的大小进行比较。如果现在的大小比基础大小大制定的百分比（auto-aof-rewrite-percentage），重写功能将启动。同时需要指定一个最小大小（auto-aof-rewrite-min-size）用于AOF重写，这个用于阻止即使文件很小但是增长幅度很大也去重写AOF文件的情况。

如：

auto-aof-rewrite-percentage 100

auto-aof-rewrite-min-size 64mb

</details>  

<details>
<summary>如何检查和修复AOF文件</summary>

查：redis-check-aof appendonly.aof

修复：redis-check-aof appendonly.aof  --fix

</details> 

<details>
<summary>如何进行性能测试</summary>

redis-benchmark -c 1 –q

</details> 

<details>
<summary>如何选择合适的持久化方式？</summary>

一般来说， 如果想达到足以媲美PostgreSQL的数据安全性， 你应该同时使用两种持久化功能。如果你非常关心你的数据， 但仍然可以承受数分钟以内的数据丢失，那么你可以只使用RDB持久化。

有很多用户都只使用AOF持久化，但并不推荐这种方式：因为定时生成RDB快照（snapshot）非常便于进行数据库备份， 并且 RDB 恢复数据集的速度也要比AOF恢复的速度要快。

</details> 


<details>
<summary>Redis常见性能问题和解决方案？</summary>

 (1) Master最好不要做任何持久化工作，如RDB内存快照和AOF日志文件

 (2) 如果数据比较重要，某个Slave开启AOF备份数据，策略设置为每秒同步一次

 (3) 为了主从复制的速度和连接的稳定性，Master和Slave最好在同一个局域网内

 (4) 尽量避免在压力很大的主库上增加从库

 (5) 主从复制不要用图状结构，用单向链表结构更为稳定，即：Master <- Slave1 <- Slave2 <- Slave3...这样的结构方便解决单点故障问题，实现Slave对Master的替换。如果Master挂了，可以立刻启用Slave1做Master，其他不变。

 (6) 如果是读压力比较大的应用，可以用树型结构，比如1主带2-3从，从再带2-3的二级从...
 
</details> 


<details>
<summary>基数估计算法（HyperLogLog）有什么特点和用途？</summary>
  
 HyperLogLog 的优点是，即使输入元素的数量或者体积非常非常大，计算基数所需的空间总是固定的、并且是很小的。在 Redis 里面，每个 HyperLogLog 键只需要花费 12 KB 内存，就可以计算接近 2^64 个不同元素的基数。这和计算基数时，元素越多耗费内存就越多的集合形成鲜明对比。但是，因为 HyperLogLog 只会根据输入元素来计算基数，而不会储存输入元素本身，所以HyperLogLog 不能像集合那样，返回输入的各个元素。

用途：用于仅仅需要计数（不要求完全精准）的场景。

比如网易音乐歌曲评论的999+之类的场景。还比如统计上亿计的IP、点击等数据，如果用传统的集合需要500GB内存，而用HyperLogLog只需要12kb

</details> 

<details>
<summary>Redis 的事务中途的命令错误和运行时错误会造成事务回滚吗？</summary>
  
命令错误会，但运行时错误不会。因为Redis的事务没有关系数据库事务提供的回滚（rollback）功能。为此开发者必须在事务执行出错后自己写代码（如事务日志）来处理。

</details>   


<details>
<summary>介绍一下你所知道的分区方式或算法</summary>
  
1、范围分区

最简单的分区方式是按范围分区，就是映射一定范围的对象到特定的Redis实例。

比如key为:object_ID，ID从0到10000的用户会保存到实例R0，ID从10001到 20000的用户会保存到R1，以此类推。这种方式是可行的，并且在实际中使用，不足就是要有一个区间范围到实例的映射表。这个表要被管理，同时还需要各 种对象的映射表，通常对Redis来说并非是好的方法。

2、哈希分区

另外一种分区方法是hash分区。这对任何key都适用，也无需是object_name:这种形式，像下面描述的一样简单：用一个hash函数将key转换为一个数字，比如使用crc32 hash函数。对key foobar执行crc32(foobar)会输出类似93024922的整数。

对这个整数取模，将其转化为0-3之间的数字，就可以将这个整数映射到4个Redis实例中的一个了。93024922 % 4 = 2，就是说key foobar应该被存到R2实例中。注意：取模操作是取除的余数，通常在多种编程语言中用%操作符实现。

</details>   

<details>
<summary>如何实现分布式锁？</summary>
  
1. [Redis分布式锁的正确实现方式](https://www.cnblogs.com/linjiqin/p/8003838.html)

2. [基于redisson快速实现分布式锁](https://github.com/redisson/redisson/wiki/8.-distributed-locks-and-synchronizers)

</details>   


---

179.redis 是什么？都有哪些使用场景？

180.redis 有哪些功能？

181.redis 和 memecache 有什么区别？

182.redis 为什么是单线程的？

183.什么是缓存穿透？怎么解决？

184.redis 支持的数据类型有哪些？

185.redis 支持的 java 客户端都有哪些？

186.jedis 和 redisson 有哪些区别？

187.怎么保证缓存和数据库数据的一致性？

188.redis 持久化有几种方式？

189.redis 怎么实现分布式锁？

190.redis 分布式锁有什么缺陷？

191.redis 如何做内存优化？

192.redis 淘汰策略有哪些？

193.redis 常见的性能问题有哪些？该如何解决？

