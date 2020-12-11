---
date: 2020-08-27T15:28
tags: [ROS,zt_structure]
---

# WIFI局域网多机器人分布式架构

## 应用环境

- WIFI 多AP组网，静态IP或者DHCP
- 网络不稳定，随时有节点退出、进入

## 需求

- 调度系统的基本功能
- 第三方软件接入，调度软件、监控软件等

## 现状

- ROS2 成熟度不够
- [[百度Apollo的ROS1]] 有所改进，后续已经不开发
- [ROS+ZeroMQ](http://po-jen.github.io/design/articles/ros_with_zeromq.html) 原来ROS2也考虑过用 ZeroMQ，后来用了DDS

## 方案

- 通讯采用 [[zyre-分布式应用框架]]
- 分布式文件使用 [[FileMQ-基于zeroMQ的文件服务]] 解决
- 分布式数据库：Redis集群，MySQL集群？ [[ZeroMQ+Redis图]]
- 第三方软件接入的问题，考虑到，机器人网络和办公网络之间，终归要有硬件防火墙，可以在防火墙上面安装负载平衡软件，软件的配置可以用动态改变（根据zyre的服务器group）

## 方案2

- 使用 [[WIFI局域网多机器人分布式架构]]
- Java + [[ZooKeeper]]

## 方案3

- 使用 [[ROS2]]

## 优缺点

集中式、分布式和hybrid（混合）

[[分布式机器人控制系统的优缺点]]