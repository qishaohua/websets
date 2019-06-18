# ORBSLAM2-MYNT

末尾两个空格实现换行  
[protobuf简单介绍和ubuntu 16.04环境下安装](https://blog.csdn.net/kdchxue/article/details/81046192)  
[vector的初始化方式](https://blog.csdn.net/qq_28584889/article/details/83654318)  
[ncnn安装](https://github.com/Tencent/ncnn/wiki/how-to-build#build-for-linux-x86)  
[ncnn使用](https://github.com/Ewenwan/MVision/tree/master/CNN/HighPerformanceComputing/example)  
[caffe安装](https://www.cnblogs.com/xuanxufeng/p/6150593.html)  
[caffe安装报错](https://www.cnblogs.com/haiyang21/p/10214278.html)  
别忘记在Makefile.config中修改算力
[caffe报错 libcudnn.so.7](https://blog.csdn.net/sinat_23619409/article/details/85047788)  
[caffe Cmake安装报错1](https://blog.csdn.net/qq_42189368/article/details/87252919)  
[Ubuntu下，清屏等终端常用命令](https://blog.csdn.net/gaojinshan/article/details/9314435)  
[编译过程中的一些问题](https://github.com/Ewenwan/ORB_SLAM2_SSD_Semantic/issues/2)  
'dict_keys' object has no attribute 'remove' 解决方案：  
#first_keys = first_list.keys()  
#second_keys = second_list.keys()  
first_keys = list(first_list)  
second_keys = list(second_list)  

[Ubuntu16.04+cuda9.0安装教程](https://www.cnblogs.com/iloveblog/p/7683349.html)  
[CUDA9.1、cuDNN7在Ubuntu16.04上的安装](https://blog.csdn.net/jonms/article/details/79318566)  
[OpenCV - Linux（Ubuntu 16.04）中安装OpenCV + OpenCV_Contrib](https://www.cnblogs.com/fx-blog/p/8213704.html)  
[ubuntu16.04安装opencv3.4](https://blog.csdn.net/u013066730/article/details/79411767)  
[ubuntu 安装Pangolin 过程](https://blog.csdn.net/u012986684/article/details/52860849)  
  
    
      
软件卸载  
sudo rm -r /usr/include/pcl-1.7 /usr/share/pcl /usr/bin/pcl* /usr/lib/libpcl*  
sudo apt-get purge libvtk*  
  
  
  

YOLO运行  
./darknet detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights  
./darknet detect cfg/yolov3.cfg yolov3.weights data/eagle.jpg  
  
    
      
[Ubuntu16.04编译高博的ORBSLAM2_with_pointcloud_map](https://blog.csdn.net/qq_25349629/article/details/88350374)  

  
[ubuntu16配置Mask-RCNN](https://www.cnblogs.com/herd/p/9364911.html)  
[[论文笔记]Meaningful Maps With Object-Oriented Semantic Mapping](https://blog.csdn.net/pikachu_777/article/details/84570980)  

[最新网址get](http://zlibz.com/)  

  
[图漾 Percipio FM810-HD 的使用](https://blog.csdn.net/learning_tortosie/article/details/80887896)  

[ORB-SLAM2主页](https://github.com/raulmur/ORB_SLAM2)  



运行应用程序后，如果提示”Couldn’t open device, some information will be missing, ret: -3”, 请检查系统的访问权限配置是否正确。

