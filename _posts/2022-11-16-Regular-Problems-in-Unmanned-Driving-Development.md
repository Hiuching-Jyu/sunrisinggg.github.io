---
layout: post
title: "【Unmanned Vehicle】-Frequent problems"
date: 2022-11-16
excerpt: "Collected during my UMV intern."
tags: [Notes,Robotics,UMV]
project: ture
comments: true
timeline: true
robotics: true
---
<script type="text/javascript" src="http://tajs.qq.com/stats?sId=66526224" charset="UTF-8"></script>
## Problem1
加速启动后，在路中无障碍物出现突然的减速。

#### Solution1
去除部分相机输出障碍物的噪声.

## Problem2
底盘会出现无法send message的报错。用CANOE检测出现周期性规律错误帧。

#### Solution2
修改CAN驱动，或者暂时屏蔽掉错误帧，但有触发其他严重问题的风险。

## Problem3
车辆前方没有障碍物，但处于阴天或者傍晚。猜测可能是影子或者烟雾等意外因素导致相机检测到ghost。

#### Solution3
待定

## Problem4
gps信号不稳定，有时输出0有时1。北云imu的前后天线标定的三个值（前天线xyz，后天线xyz和自定义数值）没有正确配对，且设定的标准差太小。

#### Solution4
重新标定，检查单位，并增加标准差至0.03m。

## Problem5
直线轨迹启动后出现突然右转，网络状态良好，GPS=1，int解。

#### Solution5
天线的ant1和ant2插反了，指南针测得方向为正方向。

## Problem6
遥控升级后依然有很频繁的错误帧，帧数高达1帧/秒。未接电源时有错误帧，接了电源后错误帧更多了。

#### Solution6
电源线虚接，重新做线。

## Problem7
有一定概率在域控开机后，车辆无法自动联网。有线和无线都不稳定，但一般是在有线网络硬件连接的时候，选择无线网络的连接方式。

#### Solution7
可能是网络连接方式和自动驾驶节点和网络时序的问题。

