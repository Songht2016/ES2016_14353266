#Lab4. DeadLock

###一、死锁结果截图
***

  ![](http://upload-images.jianshu.io/upload_images/3398279-9517abeec2a8762b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


###二、产生死锁的四个必要条件
***

- 互斥：同一时刻，某个资源只能被一个进程访问
- 占有并等待：一个进程必须至少占有一个资源，并且等待另一个资源，而该资源为其他进程所占有
- 非抢占：资源不能被抢占，即资源只能在进程完成任务后自动释放
- 循环等待：有一组等待进程{p1,p2,p3,...,pn}，p1等待的资源被p2占有，p2等待的资源被p3占有，p3等待的资源被p4占有，...，pn等待的资源被p1占有，形成一种环装的结构

###三、本实验的死锁产生的解释
***

- 调用deallock.java时，创建了两个资源a和b
  当t.start();开始运行的时候，线程t开始被调度
  此时while();会运行，同时run();也会运行；

  ![](http://upload-images.jianshu.io/upload_images/3398279-030643972f7036ec.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


- b.last()是一个synchronized同步代码块，当Deadlock()在访问这部分代码块的时候,同为synchronized同步代码块的a.last()的访问将被阻塞


  ![](http://upload-images.jianshu.io/upload_images/3398279-2e17043db45bc67e.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 而在构造函数内的a.method(b)有调用b.last()，当他先申请得到b.last()这部分资源的时候，run()如果再去申请a.last()就会被阻塞，只有等b.last()完全被释放，run()才会从阻塞的状态变为被唤醒，才能去申请资源a.last()



  ![](http://upload-images.jianshu.io/upload_images/3398279-c51f6d11964d8621.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


  ![](http://upload-images.jianshu.io/upload_images/3398279-8dbc4ca1e114c050.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 当run在运行b.method(a)的时候，如果构造函数同时也跑到了a.method(b)这部分代码块，两个线程同时去申请属于synchronized的同步代码块Deadlock（）申请b.last()，run()申请a.last()，synchronized类型的资源同一时间只能被一个进程访问，双方僵持着，互相不让步，就会产生死锁
