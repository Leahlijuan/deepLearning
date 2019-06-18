# LSTM

## RNN简介

* Recurrent Neural Network 递归神经网络
* 用于处理序列数据，能处理序列变化的数据
* 如：某个单词的含义会随着上下文不同意思变化，RNN可以处理



![1558400463549](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558400463549.png)

* x为该节点输入，h为接收到上一个节点的输入

* y为当前节点的输出，h‘为传递到下一节点的输出

![1558400554600](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558400554600.png)

## LSTM简介

* long short-term memory 长短期记忆，是一种特殊的RNN

* 主要为了解决长序列训练过程中的梯度消失和梯度爆炸问题

![1558400684885](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558400684885.png)

* LSTM有两种传输状态，ct（cell state）改变慢；ht（hidden state）改变很快



![1558400992931](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558400992931.png)

![1558401042689](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558401042689.png)

![1558401089912](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558401089912.png)

**LSTM内部的三个阶段**

* 忘记阶段：忘记不重要的，记住重要的： 计算zf来控制c（t-1）那些需要记住
* 选择记忆阶段：对输入的xt进行选择记忆
  * 前两步结果相加得到ct，也就是第一个公式
* 输出阶段

## CNN 卷积神经网络 

[https://adeshpande3.github.io/A-Beginner%27s-Guide-To-Understanding-Convolutional-Neural-Networks/](https://adeshpande3.github.io/A-Beginner's-Guide-To-Understanding-Convolutional-Neural-Networks/)

### 应用

* 图像处理，像素点



## 结构

### 第一层 卷积层

* 过滤器（filter，or neuron，kernel）
* 被照过的区域称为 receptive field
* filter（5 * 5 * 3） 的深度必须与输入（32 * 32 * 3）的深度相同 

![1558402452027](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558402452027.png)

* 5 * 5 * 3 的filter在32 * 32 * 3的input上移动，最后得到 28 * 28 * 2 （考虑到边缘部分，所以变成了28，depth是2是因为用了2个filter），称为activation map
* filter可以被认为是feature identifiers，filter的样子就是想要识别的特征的样子

**经典的CNN结构**

* input -> Conv layers -> ReLU -> Conv -> ReLU -> Pool -> ReLU -> Conv  -> ReLU -> Pool -> Fully connected



* 最后的完全连接层是一个N为向量，N是该程序必须选择的分类。例如，如果某一数字分类程序的结果矢量是 [0 .1 .1 .75 0 0 0 0 0 .05]，则代表该图片有 10% 的概率是 1、10% 的概率是 2、75% 的概率是 3、还有 5% 的概率是 9

![1558404938078](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558404938078.png)



### 训练

* backpropagation：
  * forward pass
  * loss function: 常见的有 mean squared error
  * backward pass
  * weight update



stride: filter每次移动多少，如果是前面的例子，步幅是1

padding：给input的四周填充数值

![1558406036604](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558406036604.png)

### ReLU layers

* introduce non-linear property

### Pooling layers

* 类似filter
* 可能是取最大值，
* 作用：减少参数，控制over fitting

### Dropout layers

* 把一些值设置为0
* 解决过度拟合的问题

### Network in Network layers

* 可以看作是1 * 1 * depth的filter
* 作用是depth上的计算



### Transfer learning

* 在没有海量数据的情况下，利用别人已经预先训练好的模型，用给自己的数据“fine-tuning”模型，
* 移除最后一层，用自己的classifier代替；然后将权重固定，正常地训练模型的最后一层

### Data augmentation techniques

* 改变数据表征但是保持标签不变的方法
* 常用的有：灰度变化grayscales 水平翻转 垂直翻转等等





## 基于tensorflow的LSTM-CNN文本分类模型

<https://blog.csdn.net/ZJRN1027/article/details/80090749>

## LSTM-CNN model

* 通过embedding layer将单词转化为词向量
* 输入到LSTM中进行语义特征提取（原始语料用了padding，LSTM子啊输出时乘以MASK矩阵来减小padding的影响）
* 将LSTM所谓CNN输入，进行进一步的特征提取
* 得到分类结果

![1558408501808](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558408501808.png)

## 用CNN、RNN、HAN进行文本分类

不同的数据集

* training set: 用来learning
* validation set （development set）：对训练后的参数进行细微的调整以防止过度拟合。比如，用了两个不同的模型，会用这个数据集来选择用哪个模型
* test set

![1558416386504](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558416386504.png)



### 分类系统的组成

* training set
* feature vector
* labels 
* ML algorithm
* predictive model

![1558416529169](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1558416529169.png)



### 用CNN做分类



## GloVe a pre-trained model

































