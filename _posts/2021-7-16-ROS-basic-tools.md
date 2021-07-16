---
layout: post
title: "ROS practice--basic command"
date: 2021-7-13
excerpt: "Command lines that often occur when running ROS for beginners."
tags: [Notes,ROS]
project: ture
timeline: true
---
<script type="text/javascript" src="http://tajs.qq.com/stats?sId=66526224" charset="UTF-8"></script>


#### 查看qt的版本
`<qmake -v>`

#### 使用根用户来运行命令行
`<su root>`

ctrl+d退出

#### rosnode的作用
用于检查系统中注册了哪些节点，并检查他们的状态

- rosnode list 显示运行节点的列表

- rosnode info 显示有关选定节点的信息

- kill 停止选定的节点

#### rostopic的作用

- rostopic list 显示运行话题的列表
- rostopic info 显示有关选定话题的信息
- echo 显示在话题中发布的消息

#### rqt_graph 适用于可视化跨系统中不同节点的数据流的图新工具
- 椭圆代表节点
- 矩形代表话题
- 包含其他元素的大矩形代表命名空间
- 从节点指向主题的箭头表示话题的发布
- 反之则是对该话题的订阅


