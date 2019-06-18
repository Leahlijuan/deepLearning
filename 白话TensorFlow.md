# 白话TensorFlow

## Chapter1 机器学习是什么

### 监督学习与无监督学习

* 回归
* 分类

* 聚类

## Chapter2 深度学习是什么

## Chapter3 TensorFlow

* 图形化界面 tensorboard

  ```
  # 启动
  tensorboard --logdir=path/to/logs  
  # 默认web位置 http://localhost:6006
  ```

  

## Chapter4 feedforward neural network

从输入层开始，接受前一级的输入，并输入到下一级，直到输出层。directed acyclic graph

### Back Propagation Networks 反向传播网络

梯度下降

## Chapter5 手写板功能

training set

validation set  可以用来预防过拟合

test set



loss下降后如果开始增加，或者accuracy增加后开始下降，那么这个拐点就是过拟合的开始，应当及时停止



## Chapter6 卷积神经网络

full connect network

convolutional neural network CNN

* 卷积
  * 通过两个函数g和f生成第三个函数的一种数学算子，表征函数f与g经过翻转和平移的重叠部分的面积



#### regularization正则

* to solve the problem of overfitting
* ![1559182614696](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1559182614696.png)
* regulazation
  * L1 regulazation
  * L2 regulazation : used offen





































