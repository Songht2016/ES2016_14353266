#Lab4. DeadLock

###һ�����������ͼ
***
<div align=center>
![](http://upload-images.jianshu.io/upload_images/3398279-9517abeec2a8762b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)</div>


###���������������ĸ���Ҫ����
***

- ���⣺ͬһʱ�̣�ĳ����Դֻ�ܱ�һ�����̷���
- ռ�в��ȴ���һ�����̱�������ռ��һ����Դ�����ҵȴ���һ����Դ��������ԴΪ����������ռ��
- ����ռ����Դ���ܱ���ռ������Դֻ���ڽ������������Զ��ͷ�
- ѭ���ȴ�����һ��ȴ�����{p1,p2,p3,...,pn}��p1�ȴ�����Դ��p2ռ�У�p2�ȴ�����Դ��p3ռ�У�p3�ȴ�����Դ��p4ռ�У�...��pn�ȴ�����Դ��p1ռ�У��γ�һ�ֻ�װ�Ľṹ

###������ʵ������������Ľ���
***

- ����deallock.javaʱ��������������Դa��b
  ��t.start();��ʼ���е�ʱ���߳�t��ʼ������
  ��ʱwhile();�����У�ͬʱrun();Ҳ�����У�

<div align=center>
![](http://upload-images.jianshu.io/upload_images/3398279-030643972f7036ec.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)</div>


- b.last()��һ��synchronizedͬ������飬��Deadlock()�ڷ����ⲿ�ִ�����ʱ��,ͬΪsynchronizedͬ��������a.last()�ķ��ʽ�������

<div align=center>
![](http://upload-images.jianshu.io/upload_images/3398279-2e17043db45bc67e.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)</div>

- 
���ڹ��캯���ڵ�a.method(b)�е���b.last()������������õ�b.last()�ⲿ����Դ��ʱ��run()�����ȥ����a.last()�ͻᱻ������ֻ�е�b.last()��ȫ���ͷţ�run()�Ż��������״̬��Ϊ�����ѣ�����ȥ������Դa.last()


<div align=center>
![](http://upload-images.jianshu.io/upload_images/3398279-c51f6d11964d8621.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)</div>

<div align=center>
![](http://upload-images.jianshu.io/upload_images/3398279-8dbc4ca1e114c050.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)</div>

- ��run������b.method(a)��ʱ��������캯��ͬʱҲ�ܵ���a.method(b)�ⲿ�ִ���飬�����߳�ͬʱȥ��������synchronized��ͬ�������Deadlock��������b.last()��run()����a.last()��synchronized���͵���Դͬһʱ��ֻ�ܱ�һ�����̷��ʣ�˫�������ţ����಻�ò����ͻ��������