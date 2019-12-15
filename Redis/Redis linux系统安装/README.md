1. [root]# yum install gcc

下载redis安装包

2. [root]# wget http://download.redis.io/releases/redis-5.0.7.tar.gz

   [root]# tar xzf redis-5.0.7.tar.gz

   [root]# cd redis-5.0.7
   
   [root]# make
   
3. 启动redis
   
   在一个终端启动Redis 服务器
   
   [root]# cd /redis-5.0.7/src/
   
   [root]# ./redis-server
   
   在另一个终端可以使用内置的客户端与Redis服务器进行交互
   
   [root]# cd /redis-5.0.7/src/
   
   [root]# ./redis-cli
   
   redis> set foo bar
   
   OK
   
   redis> get foo
   
   "bar"
   
