---
layout: post
title: "Huawei -deep-learning"
date: 2020-3-2
excerpt: "The neural network of deep learning used to realize spot recognition"
tags: [Notes,Deep-learning]
project: ture
comments: true
---
#### 华为云---深度学习之构建神经网络实现景区识别

• 图像预处理
 &nbsp;  ○ 输字构造模型的时，入层是非弹性的，素以需要明确自己能够接受多大数据，因此需要同一图像分辨率，也就是总的像素点个数，彩色图向每个像素点对应三个数字RJB，
&emsp; &nbsp; ○ 随机裁剪图片&emsp; 
&nbsp;  &nbsp; § 因为每个图片中目标可能上下左右方位不一样，与实际缩放距离有差距&emsp; 
&nbsp; ○ 更改颜色空间，可能因为夜晚而与实际有误差&emsp; 
• 卷积神经网络是用于处理具有类似网格结构的数据的神经网络，例如时间序列和图像数据，卷积是一种数学运算&emsp; 
• 输入图像-卷积层对图像处理--生成多个feature map--池化层对FM进行缩减，减少计算量，防止过拟合，再次卷积，再次提取特征，再次池化--平坦层，把二维矩阵变成一维向量&emsp; 
• 卷积层和池化层都是在二维空间进行，在全连接层使用一维数据，需要加入&emsp; 
• softmax输出层，神经网络中都是数字，但是输出是向量，softmax把数字转换为概率，转换为标识类别的向量，右边的数值加起来等于一，取最大的，类别都是由字符串组成&emsp; 
• 独热编码，one-hot encoding，1所在的位置是有效的，用响亮准确标示类别&emsp; 
• 卷积神经网络结构-正则化层-防止过拟合-即学过的事物可以很好地分辨，但遇到新事物就表现的很差&emsp; 
&nbsp;  ○ 正则化的方法
&nbsp;  &nbsp; § dropout随机扔掉一些神经元和特征&emsp; 
&nbsp;  &nbsp; § L1L1正则化 限制模型复杂度&emsp; 
&nbsp;  &nbsp; § 提前停止训练，模型正在学习特征，但还没到过拟合的程度就停止了学习&emsp; 
• 输入层（接收图片）---卷积层+正则化层（卷积层可以作为输入层）---池化层+正则化层--平坦层（因为只是简单地二维变一维，所以不需要正则化层）---全连接层+正则化层---输出层&emsp; 
• CNN模型构建：&emsp; 
&nbsp; ○ 创建空模型&emsp; 
&nbsp; ○ 添加输入层，指定输入大小&emsp; 
&nbsp; ○ 添加卷积层，制定卷积核大小和数量&emsp; 
&nbsp; ○ 添加正则化层，指定丢弃神经元比例&emsp; 
&nbsp; ○ 添加池化层，设置池化参数&emsp; 
&nbsp; ○ 重复以上步骤，….&emsp; 
• 设置模型训练参数&emsp; 
&nbsp; ○ 指定损失函数&emsp; 
&nbsp; &nbsp; § 用于衡量预测值和实际值的距离&emsp; 
&nbsp; ○ 指定优化器≈学习方法&emsp; 
&nbsp; &nbsp; § 优化器决定模型如何改进，使预测值更加接近实际值&emsp; 
&nbsp; ○ 指定验证集的比例&emsp; 
&nbsp; &nbsp; § 用于改进模型训练效果&emsp; 
&nbsp;○ 指定其他训练参数&emsp; 
&nbsp; &nbsp;§ 设置模型训练周期等&emsp; 
• 损失函数的介绍：&emsp; 
&nbsp; ○ 训练模型的目的：让实际值和预测值之间的距离变小&emsp; 
&nbsp; ○ 常用的损失函数&emsp; 
&nbsp; &nbsp;§ 交叉熵 ，复杂的数学公式&emsp; 
&nbsp; &nbsp;§ MSE   是均方误差，预测值和实际值，然后取平方，不会出现负数&emsp; 
&nbsp;&nbsp; § 0-1误差，不考虑距离把心有多远&emsp; 
&nbsp; ○ 实际应用&emsp; 
&nbsp;&nbsp; § 打中靶心就是正确，否则是错的，则使用MSE和0-1误差&emsp; 
• 训练集包括验证集，测试集则是另一部分&emsp; 
&nbsp; ○ 测试集考察模型的泛化能力&emsp; 
• 参数调优介绍：&emsp; 
&nbsp; ○ 增加训练周期&emsp; 
&nbsp; ○ 更改卷积核数量&emsp; 
&nbsp; ○ 更改卷积核大小&emsp; 
&nbsp; ○ 增加卷积层数量&emsp; 
&nbsp; ○ 更改池化层大小&emsp; 
• 模型评估---使模型泛化能力增强&emsp; 
