[TOC]

# 计算机网络基础知识

## 网络架构

### 1、网络模型

<img src=".\images\网络架构.png" style="zoom:80%;" />

### 2、请求过程

<img src=".\images\请求过程.png" style="zoom:80%;" />

### 3、网络分层

<img src=".\images\网络分层.png" style="zoom:80%;" />

## 物理层



## 数据链路层

#### 1、网桥，交换机：

其实交换机可以看做是多个网桥组成的。

网桥只有两个口。

交换机，网桥，集线器它们都是必须在**同一网段**的通信，如果是跨网段必须加上**路由器**

但是现在有的**交换机有路由器的功能**

#### 2、网段：子网掩码，ip分类（A类，B类，C类...）

路由器实验：

1.两个路由器是怎么设置通信的？

2.当192.168.1.11 ping 195.171.1.10时，路由器需要怎样的配置？**（路由器的静态配置）**

3.路由器是如何配置默认路由？

![image-20210914105753570](E:\my_document\computer_network\images\image-20210914105753570.png)

#### 3、MAC地址

* 买个网卡都有一个6个字节（48bit）的MAC地址（Media Access Control Address）***长度6字节***

* 全球***唯一***，固化在网卡的ROM中，有IEEE802标准规定 ***类似身份证 ID***
* 前3个字节：OUI（Organizationally Unique Identifier) ，***组织唯一标识符***
  - 有IEEE的注册管理机构分配给厂商
* 后3个字节：***网络接口标识符***
  * 厂商自己分配
  <img src=".\images\mac地址.png" style="zoom:50%;" />

1. MAC分类

   [MAC分类]: http://standards-oui.ieee.org/oui/oui.txt

2. MAC获取

   - ipconfig -all 命令

3. ARP协议

4. <font color=red>MAC地址全为1表示广播地址 **(FF:FF:FF:FF)**</font>

#### 4、包结构

![](.\images\数据链路层包.png)

***用ppt画图解释data link layer 结构***



## 网络层

## 传输层

### 1、连接管理

#### 1.三次握手流程

![三次握手](.\images\三次握手.png)

#### 2.四次挥手流程

![四次挥手](.\images\四次挥手.png)

![三次挥手](.\images\三次挥手.png)

### 2、如何确保可靠传输

### 3、如何控制流量

### 4、拥塞如何控制

<font color=red>TCP payload是什么意思</font>

![tcp_payload](.\images\tcp_payload.png)



## 应用层

### HTTP

### DNS

### DHCP



## 问题：

### 1、子网掩码不同的两个IPping通问题。

192.168.1.10/24 ping 192.168.10.10/16 **能不能ping通**

不能ping通，因为192.168.1.10/24 ping 192.168.10.10 是以自己的掩码24位去计算192.168.10.10，得出192.168.10.10和自己**不是一个网段**

**反过来**思考

 192.168.10.10/16 ping  192.168.1.10/24**能不能ping通**

按照上面的计算方式，发现这两个都在192.168.0.0 网段。但实际上使用packet tracer实验却**不能通信**，在实验中发现**arp协议都发送失败**

<font color=red>**我暂且不知道原因。**</font>



## 推荐书籍
《Linux内核源码剖析——TCP/IP实现》
《深入理解Linux网络TCP源码实现》
《追踪Linux.TCP／IP代码运行：基于2.6内核》

## TODO

- [ ] arp 协议图解，写个Python脚本或Qt解析mac地址，返回对应的厂商信息。arp属于哪一层？？？
- [ ] data linker layer 画图解释

