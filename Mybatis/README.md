# [MyBatis面试题](https://github.com/stevenli91748/Database/blob/master/Mybatis/Interview/README.md)


[精尽 MyBatis 学习指南](http://svip.iocoder.cn/MyBatis/tutorials/)|
---|

[Mybatis工作流程及其原理](https://zhuanlan.zhihu.com/p/206887990?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)|[持久层框架JPA与Mybatis该如何选型](http://www.zimug.com/java/%e6%8c%81%e4%b9%85%e5%b1%82%e6%a1%86%e6%9e%b6jpa%e4%b8%8emybatis%e8%af%a5%e5%a6%82%e4%bd%95%e9%80%89%e5%9e%8b/.html)|[超给力，一键生成数据库文档-数据库表结构逆向工程](http://www.zimug.com/java/spring/%e8%b6%85%e7%bb%99%e5%8a%9b%ef%bc%8c%e4%b8%80%e9%94%ae%e7%94%9f%e6%88%90%e6%95%b0%e6%8d%ae%e5%ba%93%e6%96%87%e6%a1%a3-%e6%95%b0%e6%8d%ae%e5%ba%93%e8%a1%a8%e7%bb%93%e6%9e%84%e9%80%86%e5%90%91%e5%b7%a5/.html)|
---|---|---|


# MyBatis的特点
    
   面向接口编程
   
   可以在配置文件中定义 SQL 语句
   
   支持动态 SQL, 这是其独特的一面
    
   **mybatis 的开发方法，一共有四种方法可用**，初期使用比较麻烦，需要各种配置文件、实体类、dao 层映射关联、还有一大推其它配置。当然 mybatis 也发现了这种弊端，
    
   1) 初期开发了 generator 可以根据表结果自动生产实体类、配置文件和dao 层代码，可以减轻一部分开发量；
    
   2) 后期也进行了大量的优化可以使用注解了，自动管理 dao 层和配置文件等。
    
   3) 后来在 springboot 中出现了 mybatis-spring-boot-starter，它就是 springboot+mybatis，可以完全注解不用配置文件，也可以简单配置轻松上手，但是两种方式还是各有利弊。
 
   * [MyBatis-Spring-Boot-Starter](https://jverson.com/spring-boot-demo/jdbc-orm/Mybatis-Springboot-Starter.html)
 
   4) 再到最后就有了 mapper-spring-boot-starter，就是集成通用 Mapper 到 Spring Boot，大部分场景无需注解，通过继承而来的通用方法即可实现，复杂的场景可通过注解手动 sql 实现

   * [通用mapper]( https://jverson.com/spring-boot-demo/jdbc-orm/Mybatis-Common-Mapper.html)

   有两种方式实现对象方法与数据库操作 sql 之间的映射，注解方式和 xml 配置方式，相对传统的 xml 配置方式，注解方式要清爽很多。但是这只针对于简单语句来说，Java 注解对于稍微复杂的语句就会力不
   从心并且会显得更加混乱。因此，如果你需要做很复杂的事情，那么最好使用 XML 来映射语句

[精尽 MyBatis 原理与源码系列](http://www.iocoder.cn/MyBatis/good-collection/)|[Mybatis-原理总结](https://www.jianshu.com/p/b34e61339422)|[MyBatis原理深入解析](https://github.com/stevenli91748/Database/blob/master/Mybatis/MyBatis%E5%8E%9F%E7%90%86%E6%B7%B1%E5%85%A5%E8%A7%A3%E6%9E%90.md)|[Spring Boot MyBatis 入门](http://www.iocoder.cn/Spring-Boot/MyBatis/?self)|
---|---|---|---|



# 基本知识

[Mybatis入门之基本操作](https://mp.weixin.qq.com/s/KdrEvlShnVoYA8nr0qLSNw)|[Mybatis动态SQL，你真的会了吗](https://juejin.im/post/6869178333003776008)|
---|---|


# 注意点

**由于Java 中的基本类型会有默认值, 在实体类中不要使用基本类型。基本类型包括byte 、int , short 、long 、float 、double 、char 、boolean **



# 实验

 * Spring + Spring MVC + Mybatis + MySQL集成
 * SpringBoot + Spring MVC + Mybatis + MySQL集成
 
## Mybatis的配置
   * 用XML方式对Mybatis进行配置
   * 用注解方式对Mybatis进行配置
   * 用Spring bean对Mybatis进行配置
   * 用Java编码对Mybatis进行配置
   
   * Mybatis代码生成器的配置
   
## 缓存
   * Mybatis 







# Mybatis 视频
* [千锋 Java Mybatis框架](https://www.bilibili.com/video/av69115359?from=search&seid=15013736168332447863)
* [Mybatis 2019_IDEA版(上)](https://www.bilibili.com/video/av49974308/?spm_id_from=333.788.videocard.1)
* [Mybatis 2019_IDEA版(下)](https://www.bilibili.com/video/av49974607/?spm_id_from=333.788.videocard.3)
* [尚硅谷_通用Mapper教程](https://www.bilibili.com/video/av37225384?from=search&seid=1935119067241462664)
* [mybatis逆向工程精讲](https://www.bilibili.com/video/av71615321?from=search&seid=10556876208171242365)
* [尚硅谷Java视频教程_MyBatisPlus](https://www.bilibili.com/video/av36304490?from=search&seid=10550336197411701893)
* [MyBatis第一套 推荐学习此套(老师讲得非常好)--基础篇](https://www.bilibili.com/video/av71177491)
* [MyBatis第一套 推荐学习此套(老师讲得非常好)--提高篇](https://www.bilibili.com/video/av71177582)
# 有用的参考
* [MyBatis原理深入解析](https://www.jianshu.com/p/ec40a82cae28)

* [Mybatis](https://mybatis.org/mybatis-3/zh/index.html)
* [MyBatis-Plus](https://mp.baomidou.com/guide/#%E4%BB%A3%E7%A0%81%E6%89%98%E7%AE%A1)
* [mybatis 入门教程](http://www.mybatis.org/mybatis-3/zh/index.html)
* [Mybatis深入浅出系列](http://www.cnblogs.com/dongying/tag/Mybatis%E6%B7%B1%E5%85%A5%E6%B5%85%E5%87%BA%E7%B3%BB%E5%88%97/)
* [mybatis 实战（干货）](https://blog.csdn.net/qq_27384769/article/details/79439817)
* [Mybatis内容聚合---非常强大](https://mp.weixin.qq.com/s?__biz=MzI4Njc5NjM1NQ==&mid=2247488945&idx=2&sn=2c0326af621ac51f33720e2608121cef&chksm=ebd62a9ddca1a38b8e284b413a8eea08aa452fdeda3c4740325803514d30029a2ab4af5bdfed&scene=21)
* [面试官问你MyBatis SQL是如何执行的？把这篇文章甩给](https://www.jianshu.com/p/e80f060e14d0)
* [为什么项目中用了JOOQ后大家都不愿再用Mybatis](https://juejin.im/post/5de64988f265da33e228ddc8)
* [便捷开发之mybatis逆向工程](https://juejin.im/post/5d371fbcf265da1b7c615a1a)
* [MyBatis Mapper3接口大全](https://blog.csdn.net/wtopps/article/details/70232866?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-5.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-5.channel_param)
* [使用 MyBatis 的 mapper 接口调用时有哪些要求](https://blog.csdn.net/qq_41806546/article/details/105293440?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-7.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-7.channel_param)
* [）mybatis 核心配置文件和接口不在同一包下的解决方案](https://blog.csdn.net/weixin_30341745/article/details/99297897?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-9.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-9.channel_param)
