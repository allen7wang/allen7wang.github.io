---
title: Aliyun Learning Notes
updated: 2020-03-29 18:12
---
# Talbe of Contents

1.  [云基本介绍](#org127832d)
    1.  [什么是云？](#org4ce17fa)
    2.  [云的分类？](#org4e46933)
    3.  [为什么要用云？](#org4866ec6)
    4.  [云有哪些厂商？](#org5f83826)
    5.  [云上面的产品（名词）对应哪些技术债？](#orgc87f83c)
    6.  [使用阿里云完成本次课程目标？ &#x2013;> 企业架构](#org843e0b5)
2.  [ECS产品使用](#org64bafb5)
    1.  [ECS云服务逻辑架构  http://cdn.xuliangwei.com/15483981096062.jpg](#orga80ecbf)
    2.  [ECS地域与可用区说明](#orgb6c4c7a)
    3.  [ECS云主机配置选项](#org96c022b)
    4.  [ECS中的网络简要说明  http://cdn.xuliangwei.com/15800999499690.jpg](#org7a3b653)
    5.  [ECS云主机购买](#org3a4d0f5)
    6.  [ECS系统设置](#org120a3c8)
    7.  [ECS安全组配置](#org2d452d4)
    8.  [ECS远程连接（控制台｜Xshell)](#org5973697)
    9.  [ECS其他操作（添加数据盘｜扩容磁盘｜重制密码）](#orgf0992d2)
    10. [ECS搭建kodcloud](#orge5cf21b)
3.  [ECS快照](#orgf35a4e5)
    1.  [快照基本配置](#orgc729f51)
    2.  [手动创建快照](#org06d12ce)
    3.  [自动创建快照](#org45650f8)
4.  [ECS镜像](#org3b1f4d9)
    1.  [基于快照创建镜像](#orgc0acf75)
    2.  [基于镜像启动实例](#org11b3957)
    3.  [镜像复制、镜像共享、镜像删除](#orgc229e83)
5.  [SLB负载均衡](#org9375e93)
    1.  [SLB是什么](#orgc5c4641)
    2.  [SLB负载均衡高可用](#org6a645ec)
    3.  [SLB负载均衡应用场景](#org6f3fa3c)
    4.  [SLB快速入门、实践](#org01418e2)
    5.  [SLB转发规则实践](#org49d1c0d)
6.  [RDS数据库服务-Redis](#org713c44b)
    1.  [RDS-Redis架构](#org2e34295)
    2.  [RDS实例创建](#orgcbc8e9c)
    3.  [RDS实例设置白名单｜设置免密访问](#orgd983856)
    4.  [RDS实例备份与恢复](#org7042b0a)
    5.  [实战：实现kodcloud会话共享](#orgdc51fed)
7.  [RDS数据库服务-mysql](#orge7d181d)
    1.  [购买RDS数据库](#org2e23194)
    2.  [配置白名单（允许谁能连接），获取RDS内网数据库地址](#orga6a537a)
    3.  [创建用户，点击账号管理，创建用户，等待1分钟](#orgc43f041)
    4.  [通过ECS云主机的内网链接RDB数据库](#org84342de)
    5.  [如何配置RDB能通过外网连接](#org758ddbe)
    6.  [配置RDB读写分离](#orgb5ff906)
    7.  [配置RDB的备份策略，备份恢复中点击->备份设置，根据实际情况做调整。](#orgce91365)
    8.  [实践：搭建wordpress、共享数据至RDS](#orgfb61f01)
8.  [NAS存储服务-NFS](#org57b5e07)
    1.  [NAS基本介绍](#org46f4951)
    2.  [NAS使用流程](#orgbaae977)
    3.  [实战：共享多ECS静态资源至NAS](#orgbc212fd)
9.  [DNS](#org7a01a63)
    1.  [DNS基本介绍](#org29cd9d4)
    2.  [DNS递归查询与迭代查询](#org9f8a55c)
    3.  [DNS集中解析](#org5a98c1c)
10. [CDN](#orgd737f0b)
    1.  [CDN架构介绍](#org0ee9464)
    2.  [CDN加速两种方式（CDN根据热点缓存｜CDN根据OSS进行缓存）](#orgedf8eb0)
    3.  [SCDN（安全与速度） 全站CDN（动态居多）](#org1d3b124)
11. [HTTPS](#org39be964)
    1.  [如何购买HTTPS](#org6940ee3)
    2.  [企业购买HTTPS建议说明](#orgdf0290a)
    3.  [实战：配置SLB支持HTTPS](#orgb41e469)
    4.  [实战：配置CDN支持HTTPS](#org4cdb153)
12. [WAF](#orgb62bd33)
    1.  [WAF产品基本介绍](#org73a6c92)
    2.  [WAF接入网站架构](#org983e9eb)
    3.  [WAF+CDN接入网站架构](#org5713fc6)
    4.  [实战：WAF+CDN结合使用](#orge1dcf27)
    5.  [模拟漏洞注入：curl -I "test.oldxu.com/?alert('xss')" 拦截返回405](#org5490d8f)
13. [NAT](#orgd493b61)
    1.  [通过firewalld实现内部主机共享上网](#org72fbcf3)
    2.  [NAT实现内容共享上网](#org7c48889)
    3.  [路由表如何添加](#org2d8d0c4)
14. [OSS对象存储](#org187a859)
    1.  [什么是对象存储？](#org8af87cd)
    2.  [对象存储使用场景？](#org54e1af6)
    3.  [使用CDN对OSS进行加速？](#org30f052f)

阿里云课程大纲


<a id="org127832d"></a>

# 云基本介绍


<a id="org4ce17fa"></a>

## 什么是云？

-   云是一种“按需付费的模式”，这种模式提供了（计算、存储、网络等资源），这些资源能够被快速提供。
-   P1:计算+存储+网络
-   P2:虚拟化技术


<a id="org4e46933"></a>

## 云的分类？

-   公有云（阿里云、腾讯云）只有使用权，按需付费（技术层面：数据不安全）
    -   阿里云、腾讯云、青云、七牛、UCloud、金山云、滴滴云、美团云、华为云、AWS等
-   私有云（自建机房，自己搭建，所有自行管理（局限：资源固定））
    -   openstack、zstack 虚拟资源池
    -   将真实的物理服务器逻辑捆绑成一个虚拟资源池，用户可以根据虚拟资源池按需使用，资源是固定。
-   混合云（主要业务放私有云、当有临时需求的时候使用公有云，使用结束后释放）
    -   按需使用、按需付费、保证业务稳定的同时，也能节省一定的成本。
-   ![img](http://cdn.xuliangwei.com/15235988962356.jpg)


<a id="org4866ec6"></a>

## 为什么要用云？

-   海量资源池灵活掉配 [像大海一样｜无尽头]
-   无处不在的网络资源 [随时随地能访问云资源]
-   随需应变的自主服务 [包年包月｜按需付费]
-   保证服务的高可用性
-   能实现快速弹性伸缩 [扩展｜伸缩｜自愈]


<a id="org5f83826"></a>

## 云有哪些厂商？

-   阿里云
-   腾讯云
-   &#x2026;


<a id="orgc87f83c"></a>

## 云上面的产品（名词）对应哪些技术债？

-   物理服务器 &#x2013;> 阿里云
-   服务器 &#x2013;> ECS、快照、镜像
-   负载均衡 &#x2013;> SLB
-   数据库 &#x2013;> RDS
-   存储服务 &#x2013;> NAS、OSS
-   防火墙 &#x2013;> 安全组、高防、WAF
-   远程访问 &#x2013;> VPN
-   消息队列 &#x2013;> MQ

&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;&#x2026;.


<a id="org843e0b5"></a>

## 使用阿里云完成本次课程目标？ &#x2013;> 企业架构


<a id="org64bafb5"></a>

# ECS产品使用

云服务器（Elastic Compute Service,简称ECS)，是一种简单高效、可弹性伸缩的计算服务。比如：当服务器运行符合不够时，通常的做法时增加服务器，那么增加服务器的流程和步骤如下：
1.购买硬件，拆开服务器，安装硬件设备。2.部署系统、部署应用、接入集群。
但如果使用云主机，可以实现自动化感知、自动化扩展集群。


<a id="orga80ecbf"></a>

## ECS云服务逻辑架构  ![img](http://cdn.xuliangwei.com/15483981096062.jpg)


<a id="orgb6c4c7a"></a>

## ECS地域与可用区说明


<a id="org96c022b"></a>

## ECS云主机配置选项


<a id="org7a3b653"></a>

## ECS中的网络简要说明  ![img](http://cdn.xuliangwei.com/15800999499690.jpg)


<a id="org3a4d0f5"></a>

## ECS云主机购买


<a id="org120a3c8"></a>

## ECS系统设置


<a id="org2d452d4"></a>

## ECS安全组配置


<a id="org5973697"></a>

## ECS远程连接（控制台｜Xshell)


<a id="orgf0992d2"></a>

## ECS其他操作（添加数据盘｜扩容磁盘｜重制密码）


<a id="orge5cf21b"></a>

## ECS搭建kodcloud

Document: <https://help.aliyun.com/product/25365.html?spm=a2c4g.11186623.6.540.4db0505cbq9EHp>


<a id="orgf35a4e5"></a>

# ECS快照


<a id="orgc729f51"></a>

## 快照基本配置


<a id="org06d12ce"></a>

## 手动创建快照


<a id="org45650f8"></a>

## 自动创建快照

Document: <https://help.aliyun.com/document_detail/25391.html?spm=a2c4g.11186623.6.823.73175b2cIbssVu>


<a id="org3b1f4d9"></a>

# ECS镜像


<a id="orgc0acf75"></a>

## 基于快照创建镜像


<a id="org11b3957"></a>

## 基于镜像启动实例


<a id="orgc229e83"></a>

## 镜像复制、镜像共享、镜像删除

Document: <https://help.aliyun.com/document_detail/25389.html?spm=a2c4g.11186623.6.737.68f9117diWlmEv>


<a id="org9375e93"></a>

# SLB负载均衡


<a id="orgc5c4641"></a>

## SLB是什么


<a id="org6a645ec"></a>

## SLB负载均衡高可用


<a id="org6f3fa3c"></a>

## SLB负载均衡应用场景


<a id="org01418e2"></a>

## SLB快速入门、实践


<a id="org49d1c0d"></a>

## SLB转发规则实践

Document: <https://help.aliyun.com/document_detail/27539.html?spm=a2c4g.11186623.6.544.3ad85339qTt0wW>


<a id="org713c44b"></a>

# RDS数据库服务-Redis


<a id="org2e34295"></a>

## RDS-Redis架构


<a id="orgcbc8e9c"></a>

## RDS实例创建


<a id="orgd983856"></a>

## RDS实例设置白名单｜设置免密访问


<a id="org7042b0a"></a>

## RDS实例备份与恢复


<a id="orgdc51fed"></a>

## 实战：实现kodcloud会话共享

Document: <https://help.aliyun.com/product/26340.html?spm=a2c4g.11174283.6.34.690852fe0TaF4k>


<a id="orge7d181d"></a>

# RDS数据库服务-mysql


<a id="org2e23194"></a>

## 购买RDS数据库


<a id="orga6a537a"></a>

## 配置白名单（允许谁能连接），获取RDS内网数据库地址


<a id="orgc43f041"></a>

## 创建用户，点击账号管理，创建用户，等待1分钟


<a id="org84342de"></a>

## 通过ECS云主机的内网链接RDB数据库


<a id="org758ddbe"></a>

## 如何配置RDB能通过外网连接

-   设置白名单
-   添加白名单分组
-   选择外网地址，填写IP（公司的固定IP｜0.0.0.0/0）


<a id="orgb5ff906"></a>

## 配置RDB读写分离

-   添加只读实例，购买一台主机
-   申请读写分离地址 rm-uf62lze1b67nt3645rw.mysql.rds.aliyuncs.com


<a id="orgce91365"></a>

## 配置RDB的备份策略，备份恢复中点击->备份设置，根据实际情况做调整。


<a id="orgfb61f01"></a>

## 实践：搭建wordpress、共享数据至RDS

Document: <https://help.aliyun.com/document_detail/96047.html?spm=a2c4g.11174283.6.603.72514c22mb10IC>


<a id="org57b5e07"></a>

# NAS存储服务-NFS


<a id="org46f4951"></a>

## NAS基本介绍


<a id="orgbaae977"></a>

## NAS使用流程


<a id="orgbc212fd"></a>

## 实战：共享多ECS静态资源至NAS

Document: <https://help.aliyun.com/product/27516.html?spm=a2c4g.750001.list.20.f8277b1305C1mf>


<a id="org7a01a63"></a>

# DNS


<a id="org29cd9d4"></a>

## DNS基本介绍


<a id="org9f8a55c"></a>

## DNS递归查询与迭代查询


<a id="org5a98c1c"></a>

## DNS集中解析


<a id="orgd737f0b"></a>

# CDN


<a id="org0ee9464"></a>

## CDN架构介绍


<a id="orgedf8eb0"></a>

## CDN加速两种方式（CDN根据热点缓存｜CDN根据OSS进行缓存）


<a id="org1d3b124"></a>

## SCDN（安全与速度） 全站CDN（动态居多）

Document:<https://help.aliyun.com/product/27099.html?spm=a2c4g.750001.list.74.70497b13IJcDtu>


<a id="org39be964"></a>

# HTTPS


<a id="org6940ee3"></a>

## 如何购买HTTPS


<a id="orgdf0290a"></a>

## 企业购买HTTPS建议说明


<a id="orgb41e469"></a>

## 实战：配置SLB支持HTTPS


<a id="org4cdb153"></a>

## 实战：配置CDN支持HTTPS

Document: <https://help.aliyun.com/product/29533.html?spm=a2c4g.750001.list.180.70497b13IJcDtu>


<a id="orgb62bd33"></a>

# WAF


<a id="org73a6c92"></a>

## WAF产品基本介绍


<a id="org983e9eb"></a>

## WAF接入网站架构


<a id="org5713fc6"></a>

## WAF+CDN接入网站架构


<a id="orge1dcf27"></a>

## 实战：WAF+CDN结合使用


<a id="org5490d8f"></a>

## 模拟漏洞注入：curl -I "test.oldxu.com/?alert('xss')" 拦截返回405

Document: <https://help.aliyun.com/product/25855.html?spm=a2c4g.11196623.6.540.535448595bgK6Y>


<a id="orgd493b61"></a>

# NAT


<a id="org72fbcf3"></a>

## 通过firewalld实现内部主机共享上网


<a id="org7c48889"></a>

## NAT实现内容共享上网


<a id="org2d8d0c4"></a>

## 路由表如何添加


<a id="org187a859"></a>

# OSS对象存储


<a id="org8af87cd"></a>

## 什么是对象存储？


<a id="org54e1af6"></a>

## 对象存储使用场景？


<a id="org30f052f"></a>

## 使用CDN对OSS进行加速？

Document: <https://help.aliyun.com/product/318518.html?spm=a2c4g.11186623.6.540.152f406cjmJWuA>

