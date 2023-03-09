## 学习matlab例子-使用强化学习调节PI参数

本质上是用强化学习agent替代了PI控制器，但结果上又能根据神经网络结构得到$k_P$,$k_I$的具体参数，细节在于，另外设计了一个PI神经网络层，本质上是一个全连接层，predict预测时所有权重都取绝对值

如果放到目前正在做的振荡抑制中，由于PSS的超前滞后角度为0，所以可以只考虑k值，因此设计一个PSS神经网络层，其输入数量为1，输出数量为1，可学参数数量为1，即k值。

**不同工况下**

可以利用该神经网络结构学习不同工况时的系统，从而取得各自不同的最优k值，在工况发生变换时从而可以进行切换

![image-20230307213222321](https://cdn.jsdelivr.net/gh/So1omonintrouble/gitpush/image/image-20230307213222321.png)

![image-20230308125931902](https://cdn.jsdelivr.net/gh/So1omonintrouble/gitpush/image/image-20230308125931902.png)

![image-20230308131838594](https://cdn.jsdelivr.net/gh/So1omonintrouble/gitpush/image/image-20230308131838594.png)

## 问题 

1. 训练不稳定-改个种子就回不去了
2. 训练无法维持在稳态，再训练几十个episode就掉下去了

![image-20230308185019395](https://cdn.jsdelivr.net/gh/So1omonintrouble/gitpush/image/image-20230308185019395.png)