---
layout: post
title: "ROS practice--errors and sulotions"
date: 2021-7-13
excerpt: "Errors and tips that often occur when running ROS for beginners."
tags: [Notes,ROS]
project: ture
timeline: true
---
<script type="text/javascript" src="http://tajs.qq.com/stats?sId=66526224" charset="UTF-8"></script>


## Error1
`< E: The repository 'http://ppa.launchpad.net/levi-armstrong/ppa/ubuntu bionic Release' does not have a Release file.

N: Updating from such a repository can't be done securely, and is therefore disabled by default.

N: See apt-secure(8) manpage for repository creation and user configuration details.

E: The repository 'http://ppa.launchpad.net/levi-armstrong/qt-libraries-xenial/ubuntu bionic Release' does not have a Release file.

N: Updating from such a repository can't be done securely, and is therefore disabled by default.

N: See apt-secure(8) manpage for repository creation and user configuration details. >`

#### Sulotion
[解决方案链接](https://blog.csdn.net/m0_49448331/article/details/108354926 )

## Error2
`<Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?>`

#### Sulotion
[解决方案链接](https://www.jianshu.com/p/c9c425c56feb )

## Error3
`<Unable to locate package>`

#### Sulotion
`<sudo apt-get update
sudo apt-get upgrade>`

## Error4
`<ppa...（软件）Release 404 Not Found [IP: 91.189.95.83 80]>`

#### Sulotion
	1. cd  /etc/apt/sources.list.d 找到文件目录

	2. 先ls列出有的文件

	3. 然后把文件改成备份文件

	`<sudo mv damien-moore-ubuntu-codeblocks-stable-bionic.list damien-moore-ubuntu-codeblocks-stable-bionic.list.bak>`
   
    `<sudo apt update>`

## Error5
在qtcreator中没有显示可执行文件

#### Sulotion
原因是CMakelist没有填写好，按照以下格式添加即可

`<add_executable(eigenMatrix src/eigenMatrix.cpp)

target_link_libraries(
  eigenMatrix
  ${catkin_LIBRARIES}
)>`
