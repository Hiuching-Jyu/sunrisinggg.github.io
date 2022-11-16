---
layout: post
title: "ROS Practice--Create-Workspace-and-packages."
date: 2022-11-16
excerpt: "Tutorial for creating workspace and package in ROS environment"
tags: [Notes,ROS,]
project: ture
comments: true
timeline: true
robotics: true
---
<script type="text/javascript" src="http://tajs.qq.com/stats?sId=66526224" charset="UTF-8"></script>
## ROS工作空间搭建和功能包创建与编译
如果工作空间和功能包没有创建好，会导致目录很乱，且编译容易出问题
无解释&纯代码版本，catkin_make（无cmake和build），工作空间&功能包。

#### 1.创建工作空间
mkdir -p catkin_ws/src
cd catkin_ws/src
catkin_init_workspace
src里面会出现CMakeLists.txt

#### 2.编译工作空间
cd ..
catkin_make
src目录下会出现build 和devel

#### 3.设置环境变量
source devel/setup.bash

#### 4.1创建功能包
cd src
catkin_create_pkg [功能包名字] std_msgs roscpp rospy

#### 4.2替换功能包
将整个别人的功能包copy到src下即可进下一步

#### 5.编译功能包
cd ..
catkin_make





