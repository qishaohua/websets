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

摘要
我们的系统利用稀疏，基于特征的RGB-D SLAM，基于图像的深度学习对象检测和3D无监督分割。

1 介绍

2 相关工作（其他人怎么做的，优缺点）
A 语义建图
B 目标检测和语义分割  

3 面向对象的语义建图
A SLAM
使用ORB-SLAM2
SLAM+semantic 应该是双向促进的。本文只用SLAM增益了语义分割（提供位姿），但没有通过语义信息增益SLAM。

B 用于语义建图的目标检测 SSD
COCO数据集 80类  

C 3D分割
Kruskal’s algorithm  是基于几何的方法，存在会把两个相连的同类物体分隔为一个的情况。  

D 数据关联
object是一个高层的抽象概念，维护的是object的几何，点云是它的一个属性。
其包含：对应3D点云、类别的累积概率、SLAM模块的位姿索引。
对于当前帧识别到的物体，若已存在，就把它加进去调整，若不存在，则插入。
判断是否存在，使用了类似ICP的方法，首先根据点云重心的欧式距离，找出最接近的一组候选object，然后使用最近列，看这个object和候选object直接，所有点对之间的欧式距离，如果超过50%点对的距离小于一个阈值，就认为是匹配到的object。  

E 对象模型更新
更新object的累计概率。就是简单的累加，把新加入object这个类别的置信度加在累计置信度上。判断类别时就argmax一下。
由于不是通过semantic segmentation获取的像素类别，因此在发生位姿变换、闭环检测时，map中点的标签就需要根据对应object的标签更新。因此，系统把每个object存储下来，构建地图或调整位姿时映射到地图中就好。  
