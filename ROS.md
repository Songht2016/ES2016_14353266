#��װ������ROS
---
>  ROS---Robot operation system��һ�׿�ܣ��ײ��ṩӲ����������������֧��ͨ�õ��ļ���ʽ��������Ubuntu�ϰ�װ����ROS���������£�

##����Ubuntu������Դ
    ����UbuntuҪ����������restricted��universe��multiverse������Դ
##��������Դ��sources.list
```
$sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu trusty main" > /etc/apt/sources.list.d/ros-latest.list'
```

##������Կ
```
$ wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
```

##��װ
ROS�������಻ͬ�ĺ�����͹��ߣ��������ȫ��װ�����а���ROS�����ӻ�����rviz��ͨ�û����˿⣬���滷���ȵȣ�
```
$ sudo apt-get update
$ sudo apt-get install ros-indigo-desktop-full
```

##��ʼ��rosdep
rosdep����ʹϵͳ�������İ�װ���ӷ��㣬ͬʱROS��һЩ��Ҫ����������Ҳ��Ҫrosdep
```
$ sudo rosdep init
$ rosdep update
```

![](http://upload-images.jianshu.io/upload_images/3398279-ba6db8e8ab6dc7fa.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##��װrosinstall
```
$ sudo apt-get install python-rosinstall
```

##����ROS��������
```
$ echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```

##����ROS����
ͨ�����������鿴ROS�������������ã�����Ƿ����ROS_ROOT��ROS_PACKAGE_PATH��Щ��������
```
$ export | grep ROS
```
![](http://upload-images.jianshu.io/upload_images/3398279-5ae8ba643929f713.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##����ROS��������

����catkin��������

```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace
```

����һ�������ռ�

```
$ cd ~/catkin_ws/
$ catkin_make
```

![](http://upload-images.jianshu.io/upload_images/3398279-5fa8fbd8fd30a192.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
�����µ�setup.*sh �ļ�

```
$ source devel/setup.bash
```

ȷ�ϵ�ǰĿ¼�Ƿ��ڻ���������
```
$ echo $ROS_PACKAGE_PATH
```

![](http://upload-images.jianshu.io/upload_images/3398279-81c8c2a91dba294b.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


---
����Ϊֹ���Ͱ�װ���óɹ���~

���룺��װ�Ĺ��̻��Ǻ�˳���ģ�����install full��ʱ�����һ�£������ٴ�����Ȼ�Ѿ�install���ˣ������档����