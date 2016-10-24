
#Lab.3 DOL实例分析及编程
###修改example2，将square变为2个
***
1.  打开example2.xml文件：
``` 
  ~$ cd dol/examples/example2           //进入到需要修改的文件example2.xml所在文件夹中
  ~$ sudo gedit example2.xml            //赋予编辑该文件的权限，开始修改代码
```

2.  修改example2.xml文件：

    ` variable N = 3 改为 variable N = 2;  ->  即将下图中的value改为2;`
![](http://upload-images.jianshu.io/upload_images/3398279-0341221485466c38.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  `修改依据：
    在下面的instantiate resources定义中，对square.c的定义是iterator -> 要迭代的程序:`
![](http://upload-images.jianshu.io/upload_images/3398279-f69121de966d09ac.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  `从上面的定义中可以看出，迭代的次数，也就是放了几个square在流程里面，是依赖于 N 的值的，进入该程序的值是 c，经过square.c 处理以后得到c^2, i是变量，下面有定义 i 的值每次 +1，因此想要把square的个数改变，只要改变N的值就可以了`

3.  运行改后的example2文件：

    ```
    $ sudo rm -rf dol/build/bin/main/example2    
    //编译前先将之前编译文件时产生的文件给删除，否则在运行的时候得到的还是没改之前的结果

    $ cd dol
    $ sudo ant -f build_zip.xml all
    //重新编译修改过后的文件

    $ cd build/bin/main
    $ sudo ant -f runexample.xml -Dnumber=2 
    //运行example2.xml文件，输出结果
    ```

4.  输出的结果为：

    修改后的example2运行得到的结果

    ![](http://upload-images.jianshu.io/upload_images/3398279-d9d70c3e27250005.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5.  最终得到的.dot文件中，流程图如下：

    example2的流程图
    
    ![](http://upload-images.jianshu.io/upload_images/3398279-9586bdd53627a227.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###修改example1，将平方变为立方
***

1.  打开example1/src文件夹下的square.c文件：

    ``` 
    ~$ cd dol/examples/example1/src           //进入到需要修改的文件square.c所在文件夹中
    ~$ sudo gedit square.c            //赋予编辑该文件的权限，开始修改代码
    ```

2.  修改square.c文件：

    ` 将代码中有关计算的部分 i*i 改为 -> i*i*i`
    ![](http://upload-images.jianshu.io/upload_images/3398279-7d89d94b8b4b9657.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.  运行改后的example1文件：

    ```
    $ sudo rm -rf dol/build/bin/main/example1   
    //编译前先将之前编译文件时产生的文件给删除，否则在运行的时候得到的还是没改之前的结果
   
   $ cd dol
    $ sudo ant -f build_zip.xml all
    //重新编译修改过后的文件

    $ cd build/bin/main
    $ sudo ant -f runexample.xml -Dnumber=1 
    //运行example1.xml文件，输出结果
    ```

4.  输出的结果为：

    example1输出结果
    
    ![](http://upload-images.jianshu.io/upload_images/3398279-61f6674392f9fa7f.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###实验感想
***

本次实验修改代码，理解代码的部分都不难，主要还是熟悉下对于xml语言，对于xml文件中各部分的作用的理解，以及对于编译文件，运行文件等命令的复习以及熟悉。







