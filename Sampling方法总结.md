
## Sampling方法介绍

### 背景知识：
现实中，很多问题无法用分析的方法来求得精确解，需要通过一些方法得到近似解，随机模拟就是一种**求近似解**的方法。

假设，我们有一个矩形的区域R（大小已知），在这个区域中有一个不规则的区域M（即不能通过公式直接计算出来），现在要求取M的面积？ 怎么求？近似的方法很多，例如：把这个不规则的区域M划分为很多很多个小的规则区域，用这些规则区域的面积求和来近似M，另外一个近似的方法就是采样的方法，我们抓一把黄豆，把它们均匀地铺在矩形区域，如果我们知道黄豆的总个数S，那么只要我们数数位于不规则区域M中的黄豆个数S1，那么我们就可以求出M的面积：M=S1*R/S

随机模拟方法的核心就是**如何对一个概率分布得到样本**，即采样（sampling）。而Sampling方法解决问题的基本思想，就是**产生一系列样本来模拟一个概率分布**。


###  1. 蒙特卡洛数值积分

如果我们要求f(x)的积分，如:

$$\int_{a}^{b} f(x)dx $$

而f(x)的形式可能比较复杂，积分不好求，则可以通过数值解法来求近似的结果。常用的方法是蒙特卡洛积分：

$$\int_a^b f(x) dx = \int_a^b \frac{f(x)}{g(x)}g(x) dx = \frac{1}{n}\sum _1^n \frac{f(x)}{g(x)}$$

这样把g(x)看做是x在区间内的概率分布，而把前面的分数部分看做一个函数，然后在g(x)下**抽取n个样本**，当n足够大时，可以用采用均值来近似。因此只要g(x)比较容易采到数据样本，就可以求得分f(x)在区间上的积分。

### 2. Monte Carlo principle

Monte Carlo 采样计算：x表示随机变量，服从概率分布 p(x)，那么要计算 f(x) 的期望，只需要我们不停从 p(x) 中抽样xi，然后对这些f(xi)取平均即可近似f(x)的期望。

![enter image description here](https://images0.cnblogs.com/blog/533521/201310/25225400-30083dce288f4bbfbd0294d8c70e553b.png)

![enter image description here](https://images0.cnblogs.com/blog/533521/201310/25225413-7405b98e045b4af09eea448fb1db4eb5.gif)

### 3. 接受-拒绝采样

很多实际问题中，p(x)是很难直接采样的的，因此，我们需要求助其他的手段来采样。既然 p(x) 太复杂在程序中没法直接采样，那么我设定一个程序可抽样的分布 q(x) 比如高斯分布，然后按照一定的方法拒绝某些样本，达到接近 p(x) 分布的目的:

![enter image description here](https://images0.cnblogs.com/blog/533521/201310/25225434-fd6db018b45d4152a09ea1de2b5304ad.png)

具体操作如下，设定一个方便抽样的函数 q(x)，以及一个常量 k，使得 p(x) 总在 kq(x) 的下方。（参考上图）

-   x 轴方向：从 q(x) 分布抽样得到 a。
-   y 轴方向：从均匀分布(0, kq(a)) 中抽样得到 u。
-   如果刚好落到灰色区域: u > p(a) 拒绝， 否则接受这次抽样
-   重复以上过程

在高维的情况下，接受-拒绝采样会出现两个问题：第一是合适的 q 分布比较难以找到，第二是很难确定一个合理的 k 值。这两个问题会导致拒绝率很高，无用计算增加。

### 4. 接受-拒绝采样




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI0MzE2NTIzMywtMTg5Nzg1MTM3OCwtNj
M2OTI5Nzc5LC0yMDU5MzU1NzEwLDc0ODgwMTg2NSwyMDk2MDA2
OTUsMjE0Njg1OTU4MSwtMTEzNzMwNzk2NCwxNjUyMjczMzg4LD
E4MDY4MzkxOTgsLTM1NzA3MDQ4MywxMjExNDQxNzddfQ==
-->