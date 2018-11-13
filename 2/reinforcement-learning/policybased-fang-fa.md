---
description: 基于策略的算法
---

# Policy-based methods

## Guided Policy Search

> Sergey Levine, Stanford, 2013  
> 参考:[https://blog.csdn.net/sunbibei/article/details/51485661](https://blog.csdn.net/sunbibei/article/details/51485661)  
> trajectory 轨迹;  regularized 正则化的;  preliminary 准本工作; optima 最佳状态;

1. **直接策略搜索\(Direct PS\)** 有效对应高维系统,但对于具有数以百计的参数的策略具有挑战性.需要庞大样本学习. 本文提出的 GPS 算法将轨迹优化\(trajectory optimization\)应用到了 DPS 中. 从而避免 DPS 陷入局部最优; 论文提出使用差分动态规划\(Differential Dynamic Programming\) 生成合适引导样本\(guiding samples\), 并使用一个新颖的正则化项,提出正则化重要样本策略优化\(regularized importance sampled policy optimization\), 用来合并这些引导样本到策略搜索中. 梯度策略方法, 学习时间耗时,且每次迭代产生的样本使用之后被抛弃,下一次迭代无法使用.这类的算法不允许使用 off=policy 样本,同时需要控制步长. **重要采样\(importance sampled\)**技术使用另一个概率来估算关于概率的期望. 他的总结: GPS算法\[1\], 由Levine 在13年提出, 使用DDP产生处于高回报区域的引导样本, 辅助策略搜索. 类似然比率评估器的重要采样技术用于合并这些引导样本到策略搜索中. GPS算法使用model-free的一些方法, 并结合model-based的DDP生成引导样本对学习过程进行引导. 可以将其视为将引导轨迹集合转换为一个控制器的过程.

![](../../.gitbook/assets/image%20%282%29.png)

