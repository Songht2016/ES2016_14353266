#安装和配置ROS
---
>  ROS---Robot operation system，一套框架，底层提供硬件驱动，软件层面支持通用的文件格式。关于在Ubuntu上安装配置ROS的流程如下：

##配置Ubuntu的软件源
    配置Ubuntu要求允许接受restricted、universe和multiverse的软件源
##添加软件源到sources.list
```
$sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu trusty main" > /etc/apt/sources.list.d/ros-latest.list'
```

##设置密钥
```
$ wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
```

##安装
ROS中有许多不同的函数库和工具，最好是完全安装，其中包括ROS，可视化环境rviz，通用机器人库，仿真环境等等：
```
$ sudo apt-get update
$ sudo apt-get install ros-indigo-desktop-full
```

##初始化rosdep
rosdep可以使系统依赖包的安装更加方便，同时ROS的一些主要部件的运行也需要rosdep
```
$ sudo rosdep init
$ rosdep update
```

![](http://upload-images.jianshu.io/upload_images/3398279-ba6db8e8ab6dc7fa.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##安装rosinstall
```
$ sudo apt-get install python-rosinstall
```

##添加ROS环境变量
```
$ echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```

##配置ROS环境
通过下面的命令查看ROS环境变量的设置，检查是否存在ROS_ROOT和ROS_PACKAGE_PATH这些环境变量
```
$ export | grep ROS
```
![](http://upload-images.jianshu.io/upload_images/3398279-5ae8ba643929f713.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##创建ROS工作环境

建立catkin工作环境

```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace
```

建立一个工作空间

```
$ cd ~/catkin_ws/
$ catkin_make
```

![](http://upload-images.jianshu.io/upload_images/3398279-5fa8fbd8fd30a192.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
启动新的setup.*sh 文件

```
$ source devel/setup.bash
```

确认当前目录是否在环境变量中
```
$ echo $ROS_PACKAGE_PATH
```

![](http://upload-images.jianshu.io/upload_images/3398279-81c8c2a91dba294b.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


---
到此为止，就安装配置成功啦~

感想：安装的过程还是很顺利的，除了install full的时候崩了一下，不过再打开他竟然已经install好了，很神奇。。。