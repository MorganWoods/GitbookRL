---
description: >-
  I think this is booming topic and it would be quite easy to get a job in the
  future.
---

# Image processing

## ImageNet Classification with Deep Convolutional Neural Networks

> Alex Krizhevsky, Geoffrey Hinton, University of Toronto, NIPS, 2012

1. -This paper introduces deep CNN architecture and it achieved record-breaking performance in the 2012 ImageNet LSVRC. -The model improves performance and reduce training time. -Uses data augmentation and dropout to prevent overfitting.
2. -Uses and popularizes\(propagate,disseminate,broadcast\) ReLUs instead of tanh as the non-linear activation unit, which makes training six times faster. -Uses local response normalization and overlapped pooling. -Dropout prevents overfitting. Randomly drops half of the neurons in the fully connected layers, and can be interpreted\(explain\) as averaging over exponentially \(['ɛkspə'nɛnʃəl](cmd://Speak/_us_/exponential) index\) - many dropout networks.
3. Weaknesses: lack theoretical insight. Design decisions are motivated solely by results.
4. **ImageNet:** Princeton University, Stanford University, The li Fei Fei team. Tasks: classification; classification and location; Kaggle: 

## UnsupervisedMonocular Depth Estimation with Left-Right Consistency

> university college london ,2016 [https://github.com/mrharicot/monodepth\#models](https://github.com/mrharicot/monodepth#models)  
> disparity: 不同,不等; top to bottom 从上到下; synthesis 合成法 ; As an alternative, ; intuition 直觉 ; binocular camera 双目的 ;

* 基本思路:匹配好左右视图的像素, 得到 disparity map. 根据 disparity , 算出 depth map. 本文能实现在35ms 内恢复一张图. 本文提出的架构收到 Mayer 的 dispNet 启发;

  利用图像重建误差 image reconstruction loss 来最小化光度误差\(类似 slam 中的直接法\),虽然得到图像重建结果,但深度预测很差; 为优化这个结果,采用 left-right consistency 优化,就是用左视图为输入,右视图为 training 中的监督真值,生成右侧对应的视图;然后又用左视图为监督真值,根据右视图生成左视图. 最小化这两个过程的联合 loss 则可以很好的左右视图对应关系.  

* method

  single image I, learn function f can predict depth, d= f\(i\)

.... 不懂

#### Depth Map Prediction from a Single Image using a Multi-Scale Deep Network

> 2014,

使用 CNN 单目深度估计

