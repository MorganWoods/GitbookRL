---
description: 读书笔记
---

# 周志华 ML

## 第一章 绪论

1. model 即 learning algorithm; data set 包含着 示例 instance 或 样本 sample; 属性是 attribute 或 特征 feature; 属性值 attribute value, 属性张成的空间称为 attribute space 或 sample space 或 input space; 一个示例 instance 称为一个特征向量 feature vector;
2. 训练数据 training data, 训练样本 training sample; 训练样本组成 训练集 training set; 假设 hypothesis, 潜在的规律称为真相或事实 ground-truth; 模型或称为学习器 learner.
3. 标签空间或输出空间 label space; 离散值任务是 classification, 连续值任务叫 regression; 二分类任务 binary classification 包含一个 positive class 和一个 negative class. 多分类叫 multi-class classification;
4. clustering 聚类将训练样本分成 cluster 簇; supervised learning 负责分类和回归, unsupervised learning 负责 clustering task;
5. generalization; 分布 distribution; independent and identically distributed iid. identically 相等地;
6. 归纳 induction 与 演绎 deduction; 前者是从特殊到一般的 generalization. 后者是 specialization 过程; 通过样例学习的过程也可称之为 归纳学习 inductive learning;
7. 奥卡姆剃刀原则: occam's razor: 若有多个假设与观察一致,则选最简单的那个; M:中选最平滑的那个; No Free Lunch Theorem ,NFL. 没有免费午餐定理;

#### 阅读材料

Mitchell ,1997 是第一本 ML 教材; 出色的入门读物: Duda 2001, AI paydin 2004, Flach 2012; 进阶读物: Hastie 2009; Bishop 2006 有参考价值.  
WEKA 是著名的免费 ML 算法程序库,基于 java 开发;

## 第二章 模型评估与选择

1. cross validation : Divides data set D to k mutual-exlusived subsets, each step using k-1 subsets for training and the 1 left for testing.
2. **Bootstrapping** \(自助法\) base on **bootstrap sampling** \(自助采样\) and it is a testing method, the testing result **named out-of-bag estimate** \(包外估计\). It is very important in ML.
3. parameter tuning 调参;
4. Performance measure for ML model: - the most common measurement is Mean Square Error for regression tasks.
5. Besides testing algorithms in experiments, researchers also need know the principle behind the results. This tool **bias-variance decomposition** could help explain the generalization ability of algorithms. The Generalization Error can be decomposed to the sum of Bias and Var. Bias and Var are conflict. This called **bias-variance dilemma**.

第三章 线性模型

第四章 决策树

第五章 神经网络

第六章 SVC

第七章 贝叶斯分类

第八章 集成学习

第九章 clustering

第十章 降维与度量学习

第十一章 特征选择与稀疏学习

第十二章 计算学习理论

第十三章 Semi-supervised learning

第十四章 概率图模型

第十五章 规则学习

## C16 RL

1. About **K-armed bandi**t 多臂老虎机 On general situations, the rewards come from one action should be a distribution but not a specific value.  A single-step RL task refer to a theoretical model - K armed bandit. For knowing the reward of each arms, we could use **exploration-only method**, whilst for maximum accumulated rewards we could use **exploitation-only** method. actually the two methods is in dilemma called **Exploration-Exploitation dilemma**. For solve the exploration and exploitation dilemma, some well-known methods like **e-greedy** algorithm, Softmax algorithm.
2. **Softmax algorithm**: This method is a compromise between exploration and exploitation according to known average rewards of different arms. the probability of pull each arms with softmax method based on Boltzmann distribution.

