# 第3章 HTTP再邂逅--熟悉HTTP协议结构和通讯原理

## 3-1_HTTP协议特点

![HTTP协议特点](./assets/HTTP协议特点.png)



## 3-2_详解URL与URI的区别与联系

![详解URL与URI的区别与联系](./assets/详解URL与URI的区别与联系.png)



## 3-3_HTTP报文结构分析

### 请求报文

![请求报文](./assets/请求报文.png)

### HTTP报文头

![HTTP报文头](./assets/HTTP报文头.png)

#### 通用报文头

![通用报文头](./assets/通用报文头.png)

#### 请求报文头

![请求报文头](./assets/请求报文头.png)

#### 响应报文头

![响应报文头](./assets/响应报文头.png)

#### 实体报文头

![实体报文头](./assets/实体报文头.png)

### 常见HTTP报文头

#### Accept

![Accept](./assets/Accept.png)

#### Accept-Encoding

![Accept-Encoding](./assets/Accept-Encoding.png)

#### Accept-Language

![Accept-Language](./assets/Accept-Language.png)

#### Connection

![Connection](./assets/Connection.png)

#### Host

![Host](./assets/Host.png)

#### Referer

![Referer](./assets/Referer.png)

#### User-Agent

![User-Agent](./assets/User-Agent.png)

#### Content-Type

![Content-Type](./assets/Content-Type.png)



### 响应报文

![响应报文](./assets/响应报文.png)



## 3-4_HTTP请求方法剖析

```
HTTP1.1
GET
POST
PUT
HEAD
DELETE
OPTIONS
TRACE
CONNECT
```



### GET获取资源

![GET获取资源](./assets/GET获取资源.png)



### POST

![POST](./assets/POST.png)

### POST和GET区别

```
速度：GET速度快
客户端请求：GET通过url提交，数据在url里可以看到；POST请求数据放在http的body里面
大小：GET有大小限制
安全性： 使用GET参数会显示在地址栏上，POST不会，一些敏感数据不适合
```

### PUT

![PUT](./assets/PUT.png)

```
PUT基本退出使用，自身不带验证机制，有安全性问题，基本被POST+后端逻辑取代
```

### HEAD

类似于GET请求，只不过返回的响应中没有具体内容，用于获取报头

### DELETE

基本不用，被攻击

请求服务器删除指定资源

### OPTIONS

![OPTIONS](./assets/OPTIONS.png)

### TRACE

基本不用，被攻击

回显服务器收到的请求，主要用于测试和诊断

### CONTECT

网页中基本不用

开启一个客户端与所请求的资源之间的双向沟通的渠道，它可以创建隧道



## 3-5_HTTP响应状态码拆解

### 状态码

![状态码](./assets/状态码.png)

### HTTP状态码详解

![HTTP状态码详解](./assets/HTTP状态码详解.png)

#### 2XX

![2XX](./assets/2XX.png)

#### 3XX

![3XX](./assets/3XX.png)

#### 4XX

![4XX](./assets/4XX.png)

#### 5XX

![5XX](./assets/5XX.png)



## 3-6_实验：用telnet分析http协议的通讯过程



## 3-7_HTTP状态管理：Cookie与Session

### Cookie

#### Cookie

![Cookie](./assets/Cookie.png)

#### Cookie工作原理

![Cookie工作原理](./assets/Cookie工作原理.png)

### Session

#### Session

![Session](./assets/Session.png)

#### Session工作原理

![Session工作原理](./assets/Session工作原理.png)

#### 保存SessionID 的方式

![保存SessionID 的方式](./assets/保存SessionID 的方式.png)

#### Session有效期

- Session超时失效
- 程序调用HttpSession.invalidate()
- 服务器进程被停止



### Cookie与Seesion

```
存放位置不同：	Cookie存储在客户端；Session保存在服务器端
安全性（隐私策略）不同：Cookie在客户端建议敏感信息加密存储,传入服务器解密；
有效期不同：Cookie设置值，理论可以达到永久；Session服务器会定时清除长期不用，或者过期Session，避免出现	过大压力， 由于session依赖于SessionId,默认过期时间是个-1，关闭浏览器也就失效
对服务器压力不同：Seesion占用大量资源
```

