
#Lab.3 DOLʵ�����������
###�޸�example2����square��Ϊ2��
***
1.  ��example2.xml�ļ���
``` 
  ~$ cd dol/examples/example2           //���뵽��Ҫ�޸ĵ��ļ�example2.xml�����ļ�����
  ~$ sudo gedit example2.xml            //����༭���ļ���Ȩ�ޣ���ʼ�޸Ĵ���
```

2.  �޸�example2.xml�ļ���

    ` variable N = 3 ��Ϊ variable N = 2;  ->  ������ͼ�е�value��Ϊ2;`
![](http://upload-images.jianshu.io/upload_images/3398279-0341221485466c38.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  `�޸����ݣ�
    �������instantiate resources�����У���square.c�Ķ�����iterator -> Ҫ�����ĳ���:`
![](http://upload-images.jianshu.io/upload_images/3398279-f69121de966d09ac.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

  `������Ķ����п��Կ����������Ĵ�����Ҳ���Ƿ��˼���square���������棬�������� N ��ֵ�ģ�����ó����ֵ�� c������square.c �����Ժ�õ�c^2, i�Ǳ����������ж��� i ��ֵÿ�� +1�������Ҫ��square�ĸ����ı䣬ֻҪ�ı�N��ֵ�Ϳ�����`

3.  ���иĺ��example2�ļ���

    ```
    $ sudo rm -rf dol/build/bin/main/example2    
    //����ǰ�Ƚ�֮ǰ�����ļ�ʱ�������ļ���ɾ�������������е�ʱ��õ��Ļ���û��֮ǰ�Ľ��

    $ cd dol
    $ sudo ant -f build_zip.xml all
    //���±����޸Ĺ�����ļ�

    $ cd build/bin/main
    $ sudo ant -f runexample.xml -Dnumber=2 
    //����example2.xml�ļ���������
    ```

4.  ����Ľ��Ϊ��

    �޸ĺ��example2���еõ��Ľ��

    ![](http://upload-images.jianshu.io/upload_images/3398279-d9d70c3e27250005.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5.  ���յõ���.dot�ļ��У�����ͼ���£�

    example2������ͼ
    
    ![](http://upload-images.jianshu.io/upload_images/3398279-9586bdd53627a227.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###�޸�example1����ƽ����Ϊ����
***

1.  ��example1/src�ļ����µ�square.c�ļ���

    ``` 
    ~$ cd dol/examples/example1/src           //���뵽��Ҫ�޸ĵ��ļ�square.c�����ļ�����
    ~$ sudo gedit square.c            //����༭���ļ���Ȩ�ޣ���ʼ�޸Ĵ���
    ```

2.  �޸�square.c�ļ���

    ` ���������йؼ���Ĳ��� i*i ��Ϊ -> i*i*i`
    ![](http://upload-images.jianshu.io/upload_images/3398279-7d89d94b8b4b9657.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.  ���иĺ��example1�ļ���

    ```
    $ sudo rm -rf dol/build/bin/main/example1   
    //����ǰ�Ƚ�֮ǰ�����ļ�ʱ�������ļ���ɾ�������������е�ʱ��õ��Ļ���û��֮ǰ�Ľ��
   
   $ cd dol
    $ sudo ant -f build_zip.xml all
    //���±����޸Ĺ�����ļ�

    $ cd build/bin/main
    $ sudo ant -f runexample.xml -Dnumber=1 
    //����example1.xml�ļ���������
    ```

4.  ����Ľ��Ϊ��

    example1������
    
    ![](http://upload-images.jianshu.io/upload_images/3398279-61f6674392f9fa7f.PNG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###ʵ�����
***

����ʵ���޸Ĵ��룬�������Ĳ��ֶ����ѣ���Ҫ������Ϥ�¶���xml���ԣ�����xml�ļ��и����ֵ����õ����⣬�Լ����ڱ����ļ��������ļ�������ĸ�ϰ�Լ���Ϥ��






