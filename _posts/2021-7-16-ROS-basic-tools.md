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

#### rqt_graph 
适用于可视化跨系统中不同节点的数据流的图新工具

- 椭圆代表节点
- 矩形代表话题
- 包含其他元素的大矩形代表命名空间
- 从节点指向主题的箭头表示话题的发布
- 反之则是对该话题的订阅

#### roslaunch 启动系统
是一种简化同时运行多个节点的工具

- 调用方法：
    - roslaunch package file.launch 适用于随包提供启动文件，可以从任何文件夹运行它
    - Roslaunch file.launch 当使用独立文件的时候，在启动文件所在的文件夹中运行它

- .launch文件的结构，用的是XML的标记语言。
    - 需要添加的内容被插入在<launch>…</launch>中
    - 使用node元素定义节点
        - <node pkg="package_name" type="node" name="id" required="true" output="screen"> </node>
            - type：要运行的节点
			- name：将绑定到节点的id
			- required：如果是true则.launch中该节点停止或者失败，则文件中的所有节点都将会停止，默认值为false
            - output：如果值为screen节点输出将定向到屏幕，如果值为log输出将定向到日志文件，默认为日志。

- 使用launch来运行节点
    - 通过输入节点名称来启动ROS
			rosrun tutorial_pkg tutorial_pkg_node
	- 如果要使用.launch与自定义包关联的文件，那么就必须要创建launch目录，并且将.launch文件放在那里
			
    `<mkdir ~/ros_workspace/src/tutorial_pkg/launch>`
		
     通过以下命令来驱动.launch

`<roslaunch tutorial_pkg your_launch_file.launch>`
