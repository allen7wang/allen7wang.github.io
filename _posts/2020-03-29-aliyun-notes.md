---
title: Aliyun Learning Notes
updated: 2020-03-29 18:12
---
 of Contents

1.  [云基本介绍](#org6806bde)
    1.  [什么是云？](#org95cc4b5)
    2.  [云的分类？](#org819d279)
    3.  [为什么要用云？](#orgc60f444)
    4.  [云有哪些厂商？](#org3fae900)
    5.  [云上面的产品（名词）对应哪些技术债？](#org47a2e48)
2.  [ECS产品使用](#orgd4f8d46)
3.  [ECS快照](#orga82022c)
4.  [ECS镜像](#org4494e3e)
5.  [SLB负载均衡](#orgeadcd66)
6.  [RDS数据库服务-Redis](#orga4b102f)
7.  [RDS数据库服务-mysql](#org51aa9f8)
8.  [NAS存储服务-NFS](#orgf013aed)
9.  [DNS](#orgca691db)
10. [CDN](#orgd1526de)
11. [HTTPS](#org9459769)
12. [WAF](#org7ceeb15)
13. [NAT](#org0c7a046)
14. [OSS对象存储](#orgfbb583e)

阿里云课程大纲


<a id="org6806bde"></a>

# 云基本介绍


<a id="org95cc4b5"></a>

## 什么是云？

-   云是一种“按需付费的模式”，这种模式提供了（计算、存储、网络等资源），这些资源能够被快速提供。


<a id="org819d279"></a>

## 云的分类？

-   公有云（阿里云、腾讯云）只有使用权，按需付费（技术层面：数据不安全）
-   私有云（自建机房，自己搭建，所有自行管理（局限：资源固定））
-   混合云（主要业务放私有云、当有临时需求的时候使用公有云，使用结束后释放）
-   ![img](http://cdn.xuliangwei.com/15235988962356.jpg)


<a id="orgc60f444"></a>

## 为什么要用云？

-   海量资源池灵活掉配
-   无处不在的网络资源
-   随需应变的自主服务【包年包月｜按需付费】
-   保证服务的高可用性
-   能实现快速弹性伸缩


<a id="org3fae900"></a>

## 云有哪些厂商？

-   阿里云
-   腾讯云
-   &#x2026;


<a id="org47a2e48"></a>

## 云上面的产品（名词）对应哪些技术债？

-   物理服务器 &#x2013;> 阿里云
-   服务器    &#x2013;> ECS、快照、镜像
-   负载均衡  &#x2013;> SLB
-   数据库   &#x2013;> RDS
-   存储服务 &#x2013;> NAS、OSS
-   防火墙  &#x2013;> 安全组、高防、WAF
-   远程访问 &#x2013;> VPN
-   消息队列  &#x2013;> MQ

&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;.


<a id="orgd4f8d46"></a>

# ECS产品使用

云服务器（Elastic Compute Service,简称ECS)，是一种简单高效、可弹性伸缩的计算服务。比如：当服务器运行符合不够时，通常的做法时增加服务器，那么增加服务器的流程和步骤如下：
1.购买硬件，拆开服务器，安装硬件设备。2.部署系统、部署应用、接入集群。
但如果使用云主机，可以实现自动化感知、自动化扩展集群。

-   ECS云服务逻辑架构  ![img](http://cdn.xuliangwei.com/15483981096062.jpg)
-   ECS地域与可用区说明
-   ECS云主机配置选项
-   ECS中的网络简要说明  ![img](http://cdn.xuliangwei.com/15800999499690.jpg)
-   ECS云主机购买
-   ECS系统设置
-   ECS安全组配置
-   ECS远程连接（控制台｜Xshell)
-   ECS其他操作（添加数据盘｜扩容磁盘｜重制密码）
-   ECS搭建kodcloud

Document: <https://help.aliyun.com/product/25365.html?spm=a2c4g.11186623.6.540.4db0505cbq9EHp>


<a id="orga82022c"></a>

# ECS快照

-   快照基本配置
-   手动创建快照
-   自动创建快照

Document: <https://help.aliyun.com/document_detail/25391.html?spm=a2c4g.11186623.6.823.73175b2cIbssVu>


<a id="org4494e3e"></a>

# ECS镜像

-   基于快照创建镜像
-   基于镜像启动实例
-   镜像复制、镜像共享、镜像删除

Document: <https://help.aliyun.com/document_detail/25389.html?spm=a2c4g.11186623.6.737.68f9117diWlmEv>


<a id="orgeadcd66"></a>

# SLB负载均衡

-   SLB是什么
-   SLB负载均衡高可用
-   SLB负载均衡应用场景
-   SLB快速入门、实践
-   SLB转发规则实践

Document: <https://help.aliyun.com/document_detail/27539.html?spm=a2c4g.11186623.6.544.3ad85339qTt0wW>


<a id="orga4b102f"></a>

# RDS数据库服务-Redis

-   RDS-Redis架构
-   RDS实例创建
-   RDS实例设置白名单｜设置免密访问
-   RDS实例备份与恢复
-   实战：实现kodcloud会话共享

Document: <https://help.aliyun.com/product/26340.html?spm=a2c4g.11174283.6.34.690852fe0TaF4k>


<a id="org51aa9f8"></a>

# RDS数据库服务-mysql

-   购买RDS数据库
-   配置白名单（允许谁能连接），获取RDS内网数据库地址
-   创建用户，点击账号管理，创建用户，等待1分钟
-   通过ECS云主机的内网链接RDB数据库
-   如何配置RDB能通过外网连接
    -   设置白名单
    -   添加白名单分组
    -   选择外网地址，填写IP（公司的固定IP｜0.0.0.0/0）
-   配置RDB读写分离
    -   添加只读实例，购买一台主机
    -   申请读写分离地址 rm-uf62lze1b67nt3645rw.mysql.rds.aliyuncs.com
-   配置RDB的备份策略，备份恢复中点击->备份设置，根据实际情况做调整。
-   实践：搭建wordpress、共享数据至RDS

Document: <https://help.aliyun.com/document_detail/96047.html?spm=a2c4g.11174283.6.603.72514c22mb10IC>


<a id="orgf013aed"></a>

# NAS存储服务-NFS

-   NAS基本介绍
-   NAS使用流程
-   实战：共享多ECS静态资源至NAS

Document: <https://help.aliyun.com/product/27516.html?spm=a2c4g.750001.list.20.f8277b1305C1mf>


<a id="orgca691db"></a>

# DNS

-   DNS基本介绍
-   DNS递归查询与迭代查询
-   DNS集中解析


<a id="orgd1526de"></a>

# CDN

-   CDN架构介绍
-   CDN加速两种方式（CDN根据热点缓存｜CDN根据OSS进行缓存）
-   SCDN（安全与速度） 全站CDN（动态居多）

Document:<https://help.aliyun.com/product/27099.html?spm=a2c4g.750001.list.74.70497b13IJcDtu>


<a id="org9459769"></a>

# HTTPS

-   如何购买HTTPS
-   企业购买HTTPS建议说明
-   实战：配置SLB支持HTTPS
-   实战：配置CDN支持HTTPS

Document: <https://help.aliyun.com/product/29533.html?spm=a2c4g.750001.list.180.70497b13IJcDtu>


<a id="org7ceeb15"></a>

# WAF

-   WAF产品基本介绍
-   WAF接入网站架构
-   WAF+CDN接入网站架构
-   实战：WAF+CDN结合使用
-   模拟漏洞注入：curl -I "test.oldxu.com/?alert('xss')" 拦截返回405

Document: <https://help.aliyun.com/product/25855.html?spm=a2c4g.11196623.6.540.535448595bgK6Y>


<a id="org0c7a046"></a>

# NAT

-   通过firewalld实现内部主机共享上网
-   NAT实现内容共享上网
-   路由表如何添加


<a id="orgfbb583e"></a>

# OSS对象存储

-   什么是对象存储？
-   对象存储使用场景？
-   使用CDN对OSS进行加速？

Document: <https://help.aliyun.com/product/318518.html?spm=a2c4g.11186623.6.540.152f406cjmJWuA>
