# ROS安装 #
## SLAM：即时定位与地图构建，并发建图与定位。##

SLAM作为一种基础技术，从最早的军事用途（核潜艇海底定位就有了SLAM的雏形）到今天，已经逐步走入人们的视野，过去几年扫地机器人的盛行让它名声大噪，近期基于三维视觉的VSLAM又让它越来越显主流，许多人不得不关注它。其中，SLAM一个很厉害的功能就是为了实现室内的定位定姿。

目前用在SLAM上的Sensor主要分两大类，激光雷达和摄像头。激光雷达有单线多线之分，角分辨率及精度也各有千秋。SICK、velodyne、Hokuyo以及国内的北醒光学、Slamtech是比较有名的激光雷达厂商。他们可以作为SLAM的一种输入形式。

SLAM算法在实现的时候主要需要考虑以下几点：地图、信息、数据关联和定位与构图。

看了一波资料，感觉就是高大上，前沿时尚。
## ROS：机器人操作系统 ##

ROS是一个机器人软件操作平台，它提供一些标准操作系统服务，目前主要支持Ubuntu操作系统。ROS可分为两层，低层是操作系统层，高层是实现不同功能的软件包。
## 安装具体步骤 ##

参考链接：[http://wiki.ros.org/jade/Installation/Ubuntu](http://wiki.ros.org/jade/Installation/Ubuntu)

相关环境：Ubuntu14.04

1. 配置Ubuntu软件库：进入System Settings->Software & Updates,将Ubuntu Software选项卡下的"restricted"、 "universe" 和 "multiverse"选中 ，保存更改.
2. 修改source.list文件，使得电脑能够在线更新packages.ros.org上的软件 `sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`
3. 因为使用未经验证的第三方软件需要手动加载公钥并更新列表，加载公钥操作过程：`sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116 sudo apt-get update`
4. 安装ROS Desktop-Full`sudo apt-get install ros-jade-desktop-full`
5. 在使用ROS之前，需要先初始化rosdep,这样可使之后安装一些运行ROS核心部件所需要的源变得更加容易`sudo rosdep init rosdep update`
6. 设置环境变量`echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc source ~/.bashrc`
7. 前面的都是相关准备工作，现在终于正式安装rosinstall`sudo apt-get install python-rosinstall`
    