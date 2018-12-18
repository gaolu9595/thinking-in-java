
## Sampling方法介绍

### 背景知识：
现实中，很多问题无法用分析的方法来求得精确解，需要通过一些方法得到近似解，随机模拟就是一种**求近似解**的方法。

假设，我们有一个矩形的区域R（大小已知），在这个区域中有一个不规则的区域M（即不能通过公式直接计算出来），现在要求取M的面积？ 怎么求？近似的方法很多，例如：把这个不规则的区域M划分为很多很多个小的规则区域，用这些规则区域的面积求和来近似M，另外一个近似的方法就是采样的方法，我们抓一把黄豆，把它们均匀地铺在矩形区域，如果我们知道黄豆的总个数S，那么只要我们数数位于不规则区域M中的黄豆个数S1，那么我们就可以求出M的面积：M=S1*R/S

随机模拟方法的核心就是**如何对一个概率分布得到样本**，即采样（sampling）。而Sampling方法解决问题的基本思想，就是**产生一系列样本来模拟一个概率分布**。

## 1、蒙特卡洛数值积分

如果我们要求f(x)的积分，如
-$$\nf$$

![](http://www.forkosh.com/mathtex.cgi?formdata=%5Cint%5Climits_%7Ba%7D%5E%7Bb%7Df%28x%29dx)

而f(x)的形式比较复杂积分不好求，则可以通过数值解法来求近似的结果。常用的方法是蒙特卡洛积分：

[![mathtex](https://images0.cnblogs.com/blog/354318/201502/012131210506829.gif "mathtex")](https://images0.cnblogs.com/blog/354318/201502/012131205342973.gif)

这样把q(x)看做是x在区间内的概率分布，而把前面的分数部门看做一个函数，然后在q(x)下抽取n个样本，当n足够大时，可以用采用均值来近似：

![](http://www.forkosh.com/mathtex.cgi?formdata=%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%7D%5Cfrac%7Bf%28x_i%29%7D%7Bq%28x_i%29%7D)

因此只要q（x）比较容易采到数据样本就行了。随机模拟方法的核心就是如何对一个概率分布得到样本，即抽样（sampling）。下面我们将介绍常用的抽样方法。





<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNTkzNTU3MTAsNzQ4ODAxODY1LDIwOT
YwMDY5NSwyMTQ2ODU5NTgxLC0xMTM3MzA3OTY0LDE2NTIyNzMz
ODgsMTgwNjgzOTE5OCwtMzU3MDcwNDgzLDEyMTE0NDE3N119
-->