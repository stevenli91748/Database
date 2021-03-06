*  [通信](#通信)
   * [通信类型](#通信类型)
     * [同步通信](#同步通信)
     * [异步通信](#异步通信)
   * [通信连接方式](#通信连接方式)
     * [长连接](#长连接)
     * [短连接](#短连接)
   * [通信协议](#通信协议)
     * [HTTP](#HTTP)
     * [TCP](#TCP)
     * [WebService](#WebService)
   * [消息格式](#消息格式)
     * [XML格式](#XML格式)
     * [JSON 格式](#JSON 格式)
     * [定长格式](#定长格式)
*  []()
*  []()
*  []()

# 通信类型

## 同步通信
   
    一般来说我们连接数据库都是同步连接。
   
## 异步通信

    如果异步存在并发，每一个 SQL 的执行都要单独建立一个连接，避免数据混乱。但是这样会给服务端带来巨大的压力（一个连接就会创建一个线程，线程间切换会占用大量 CPU 资源）。另外异步通信还带来
    了编码的复杂度，所以一般不建议使用。如果要异步，必须使用连接池，排队从连接池获取连接而不是创建新连接。
    
# 通信连接方式

## 长连接

    长连接可以保持打开，减少服务端创建和释放连接的消耗，后面的程序访问的时候还可以使用这个连接。一般我们会在连接池中使用长连接。
    
    mysql> show global variables like 'wait_timeout%'; -- 非交互式超时时间， 如 JDBC 程序
    mysql> show global variables like 'interactive_timeout%'; -- 交互式超时时间， 如数据库工具
    
    默认都是 28800 秒，8 小时

## 短连接

    短连接就是操作完毕以后，马上 close 掉。

# 通信协议

## HTTP

## TCP

## WebService

# 消息格式

## XML格式

## JSON 格式

## 定长格式
