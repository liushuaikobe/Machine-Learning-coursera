## 机器学习的定义
### Arthur Samuel（Informal Defination）
> Field of study that gives computers the ability to learn without being explicity programmed.

*e.g.* 一个西洋棋的程序

### Tom Mitchell
> Well-posed problem: A computer program is said to learn from **experience E** with respect to **some task T** and some **performance measure P**, if its performance on T, as measured by P, improves with experience E. 

在西洋棋的例子中：

- experience E：程序上万次的跟自己下棋
- task T：下棋
- performance measure P：在下棋时赢得比赛的概率

### 机器学习算法的分类

- Supervised learning（监督式学习）   
- Unsupervised learning（无监督式学习）

其他术语：Reinforcement learning (强化学习) | recommender systems (推荐系统)

#### 监督式学习
##### Regression Problem ：连续型的输出值 
*e.g.* 预测房价（回归问题）

给算法一个数据集，数据集是一些“正确的答案”，算法根据这些答案给出更多的“正确的答案”   

##### Classification Problem：离散型的输出值
*e.g.*  预测肿瘤是恶性的还是良性的（分类问题）

对更多种已知数据 -> 对无限多种已知数据进行分析（病人年龄、肿瘤大小、细胞大小、细胞形状等等），从而作出预测: 支持向量机算法（Support Vector Machine）	

##### 总结

在监督式学习的数据集中，对于数据集中的每个数据，都有相应的“正确地答案”，算法就是基于这些来做出预测。

回归问题：通过回归来预测一个连续值的输出    
分类问题：预测一个离散值的输出

#### 无监督式学习
数据集中的数据没有明确的正确的答案，不知道数据里面有什么，不知道数据的类型，甚至不知道有哪些类型，不知道数据代表什么，算法可以自动找出数据中的结构
##### 聚类算法（clustering algorithm）
*e.g.* Google news 将说同一个事情（例如原油泄漏）的新闻聚类到一起    
*e.g.* 基因组理解的应用：对一些个体进行分析，将基因相似的或者包括某特定基因的个体聚类到一起
##### 鸡尾酒宴算法
*e.g.* 鸡尾酒宴问题 分离音频

先用[Octave](https://www.gnu.org/software/octave/)建立学习模型，并验证好之后再用到C++或者Java等实现。
##### 总结
无监督学习中，交给算法大量的数据，并让算法为我们从数据中找出某种结构。