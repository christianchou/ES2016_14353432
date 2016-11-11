### ROS配置

ROS，Robot operation system， 一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。 

#### 1.配置 Ubuntu 软件仓库

配置你的 Ubuntu 软件仓库(repositories) 以允许 "restricted"、"universe" 和 "multiverse"这三种安装模式。

#### 2.添加 sources.list

配置你的电脑使其能够安装来自 packages.ros.org的软件包。 ROS Jade **仅** 支持Trusty (14.04)、Utopic (14.10) 和 Vivid (15.04)。

> sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

#### 3.添加 keys

> sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116

#### 4.安装

首先，确保你的Debian软件包索引是最新的：

> sudo apt-get update

然后安装ROS的各种函数库和工具，直接装桌面完整版：

> sudo apt-get install ros-jade-desktop-full

要查找可用软件包，请运行：

> apt-cache search ros-jade

#### 5.初始化 rosdep

在开始使用ROS之前你还需要初始化rosdep。rosdep可以方便在你需要编译某些源码的时候为其安装一些系统依赖，同时也是某些ROS核心功能组件所必需用到的工具。

> sudo rosdep init
>
> rosdep update

#### 6.环境配置

如果每次打开一个新的终端时ROS环境变量都能够自动配置好（即添加到bash会话中），那将会方便很多：

> echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
>
> source ~/.bashrc

#### 7.安装 rosinstall

rosinstall 是ROS中一个独立分开的常用命令行工具，它可以方便让你通过一条命令就可以给某个ROS软件包下载很多源码树。

要在ubuntu上安装这个工具，请运行：

> sudo apt-get install python-rosinstall



#### 到这里，只要每一步都成功运行，没有出现error，ROS就已经安装完成。

####因为ROS安装完，是没有直接的显示的，所以这里不再放上贴图。