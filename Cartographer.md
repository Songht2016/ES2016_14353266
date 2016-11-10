#在ROS中安装Cartographer

Cartographer是Google开源的一个SLAM算法，基于激光雷达以及IMU（惯性处理单元）。它是发布于GitHub上的开源技术可同时用于二维与三维空间的移动映射，搭配有开源机器人操作系统(ROS)，易于部署机器人、无人驾驶、无人机等系统。

因为在上一次配置ROS的时候顺手建立了catkin工作环境，并创建了工作空间，所以这次安装Cartographer就直接打开工作空间进行安装就可以了，步骤流程如下：

##获取依赖关系代码
```
# Merge the cartographer_ros.rosinstall file and fetch code for dependencies
$ cd catkin_ws
$ wstool init src
$ wstool merge -t src https://raw.githubusercontent.com/googlecartographer/cartographer_ros/master/cartographer_ros.rosinstall
$ wstool update -t src
```

##安装依赖关系
```
# Install deb dependencies.
$ rosdep init
$ rosdep update
$ rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
```

##安装
```
# Build and install.
$ catkin_make_isolated --install --use-ninja
$ source install_isolated/setup.bash
```
在catkin_make_isolated --install --use-ninja的时候出现了问题，因为需要到外网去下载东西，百度了一下，找到了解决的办法：
打开下面的文件：
build_isolated/ceres_solver/install/ceres_src-prefix/tmp/ceres_src-gitclone.cmake
将clone后面的网址改一下，把google的改成github的就可以下载了
![](http://upload-images.jianshu.io/upload_images/3398279-1797d308e241d13b.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##下载2D模型的例子，并雷达仿真出来
```
# Download the 2D backpack example bag.
$ wget -P ~/Downloads https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag
# Launch the 2D backpack demo.
$ roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag
```
最后得到的仿真图（因为等待的时间实在是太长了 等了一晚上它也没画完 我就截了下中间的图）

![](http://upload-images.jianshu.io/upload_images/3398279-71ff0aed67f7a566.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
