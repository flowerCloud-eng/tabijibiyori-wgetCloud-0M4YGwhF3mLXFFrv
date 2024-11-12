
# （1）Pytorch——数值处理



> 参考于李沐“动手学深度学习”系列以及网上各路大佬的博客资料，感谢大家的分享，如错改，如侵删。


## torch中的数值处理


数值处理是深度学习中**极其重要**的一部分，张量（tensor）是后续进行处理和计算的基本单位。张量表示一个由数值组成的数组，这个数组可能有多个维度。具有一个轴的张量对应数学上的向量（vector）；
具有两个轴的张量对应数学上的矩阵（matrix）；具有两个轴以上的张量没有特殊的数学名称。


### 创建和初始化


话不多说我们直接上代码：



```


|  | # 张量定义 |
| --- | --- |
|  | x = torch.arange(12) |
|  | y = torch.zeros((2, 3, 4)) #定义全零/全一张量 |
|  | z = torch.rand(3, 4) #正态分布随机定义tensor elements |
|  |  |
|  | # 改变张量形状 |
|  | x.reshape(3, 4) |
|  | x.reshape(-1, 4) #通过-1可以实现形状的自动计算 |


```

tensor同样支持直接的\+ \- \* / 甚至 \=\= 运算符。我们也可以按某个指定轴将tensor联结到一起，代码如下。



```


|  | X = torch.arange(12) |
| --- | --- |
|  | dtype=torch.float32).reshape((3,4)) |
|  | Y = torch.tensor([[2.0, 1, 4, 3], [1, 2, 3, 4], [4, 3, 2, 1]]) |
|  | torch.cat((X, Y), dim=0), torch.cat((X, Y), dim=1) |


```

运行效果如图：
![](https://img2024.cnblogs.com/blog/2988059/202411/2988059-20241111100436846-1909706420.png)
tensor所有元素求和：`X.sum()`


### 索引和切片


torch中的索引和切片原则基本和python一致，就不赘述了，如果Python基础不好的同学可以看一下我主页的另一篇Python的博客。
并且，numpy和torch定义的张量相互转换十分便捷：



```


|  | A = X.numpy() |
| --- | --- |
|  | B = torch.tensor(A) |


```

### 微积分、线性代数和概率论


微积分、线性代数和概率论中设计到的数学操作也是深度学习非常重要的一部分，毕竟工科尽头是理科。这块内容较多，笔者还在整理，稍后补齐(挖坑ing)。


## 数据预处理


到目前为止我们终于可以真正开始深度学习的工作了，数据预处理也是我们构建模型训练的第一步。


**Pandas**是python中常用的数据分析处理拓展包。
**Dataset**是Pytorch中的一个类，用于封装数据集的加载逻辑，使其可以被 DataLoader 有效加载。
**Transformer**是一个用于图像预处理的工具集。在计算机视觉方面应用较多。
这些我们在下一节**线性神经网络**中实战中会有所涉及，遇到具体的api也会做解释，大家一开始不必强硬的记住所有api，具体问题具体了解就好了。


 本博客参考[milou加速器](https://xinminxuehui.org)。转载请注明出处！
