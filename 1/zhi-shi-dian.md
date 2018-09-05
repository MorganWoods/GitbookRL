---
description: Basic theory
---

# Basics

## Actor-Critc 

这是 on policy 的. 运行流程: A 根据 state 选出一个 action ➡️ C 根据 state 和 action 对 A 的表现打分 ➡️ A根据 C 的打分,调整自己的策略\(网络参数\) ➡️ C 根据系统的 reward 和 C 的 target 调整自己打分策略\(网络参数\)一开始 A 与 C 都是随机的,但是由于 reward 的存在,二者策略越来越准; A 调整参数根据 C 的打分,迎合 C.

## Policy

* Policy: maps state to action, optimization is to find an optimal mapping.
* episodic tasks - 情节性任务。指（强化学习的问题）会在有限步骤下结束。continuing tasks - 连续性任务。指（强化学习的问题）有无限步骤。episode - 情节。指从起始状态（或者当前状态）到结束的所有步骤。tabular method - 列表方法。指使用了数组或者表格存储每个状态（或者状态-行动）的信息（比如：其价值）。
* planning method - 计划性方法。需要一个模型，在模型里，可以获得状态价值。比如： 动态规划。learning method - 学习性方法。不需要模型，通过模拟（或者体验），来计算状态价值。比如：蒙特卡洛方法，时序差分方法。
* on-policy method - on-policy方法。评估的策略和优化的策略是同一个。
* off-policy method - off-policy方法。评估的策略和优化的策略不是同一个。意味着优化策略使用来自外部的样本数据。
* target policy - 目标策略。off-policy方法中需要优化的策略。
* behavior policy - 行为策略μ。off-policy方法中提供样本数据的策略
* importance sampling - 行为策略μ的样本数据。
* importance sampling rate - 由于目标策略π和行为策略μ不同，导致样本数据在使用上的加权值。
* ordinary importance sampling - 无偏见的计算策略价值的方法。
* weighted importance sampling - 有偏见的计算策略价值的方法。
* MSE\(mean square error\) - 平均平方误差。
* MDP\(markov decision process\) - 马尔科夫决策过程
* ≐ - 定义上的等价关系。E\[X\] - X的期望值。Pr{X=x} - 变量X值为x的概率。v↦g - v渐近g。👂v≈g - v约等于g。R - 实数集合。Rn - n个元素的实数向量。maxa∈A F\(a\) - 在所有的行动中，求最大值F\(a\)。argmaxc F\(c\) - 求当F\(c\)为最大值时，参数c的值。
* unbiased estimate :无偏估计,用样本统计量来估计总体参数时的一种无偏推断.估计量的数学期望等于被估计参数的真实值,具有无偏性,是一种用于评价估计量优良性的准则.

