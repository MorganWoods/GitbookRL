---
description: technique relate to advantage
---

# Advantage tech

## basic info

* 对于解耦 Q 成为 A 和 V 的来源基础记录:
  * 把 Q 拆成 A 和 V 最早是baird, leemon, Advantage updating,1993 ,从 NAF文章摘出.

## Dueling Network Architectures for Deep Reinforcement Learning \(Dueling\)

> 2016, Ziyu Wang, DeepMind &lt;br&gt;

* 对于 model free RL 提出了一个新的神经网络: 一个为状态价值函数,一个为运动利益方程.在价值与利益两方面去耦合.
* 这个 Dueling network 是一个 Q 网络有两个输出流而不是一个.分别估计 state value $$function({V}_{\pi}$$\) 和 advantage function\(​$${A}_{\pi}$$\)
* 实验证明这种结构可以更快的找到正确动作. 我们发现当可用动作越高, 学习难度就越大, 不过 Dueling DQN 还是会比 Natural DQN 学习得更快. 收敛效果更好.
* 因为 Dueling 网络输出是 Q 函数,所以可以使用很多已经存在的算法训练,如 DDQN,SARSA.此外,也可以利用很多存在的提升方法,包括:better replay memories, better exploration policies, intrinsic motivation 等等.

## Continuous Deep Q learning with model-based Acceleration \(NAF\)

> 2016, Shixiang Gu
>
> 参考此文: [https://blog.csdn.net/u013236946/article/details/73243310](https://blog.csdn.net/u013236946/article/details/73243310)

* 提出算法降低 model free 采样复杂度, NAF - normalized Advantage functions; 和 iLQG; model based 算法可以提高效率,但是限制策略只能是一个学到的模型; 本 NAF 算法避免了 actor 网络或 policy 函数,是一个简化的算法, 简化优化目标从而提高采样效率.
* ​$$Q(x,u|θ^{Q})=V(x|θ^{V})+A(x,u|θ^{A})$$ , A 值表示動作 u 在狀態 x 下的優勢. 算法的目標是使策略網絡輸出的動作 u 對應的 Q 值最大. 本文的方法是讓 A 恒≤ 0 ,則 Q 恒≤ V , 在某一狀態下最優的動作的優勢函數為0. 所以最優的動作的值函數 是 Q = V.
* ​ $$A(x,u|θ^{A})=−\cfrac{1}{2}(u−μ(x|θ^{μ}))^{T}P(x|θ^{P})(u−μ(x|θ^{μ}))$$, P是一个关于状态的正定矩阵，因为正定矩阵可以进行楚列斯基（Cholesky）分解，即$$P(x|θ^{P})=L(x|θ^{P})L(x|θ^{P})^{T}$$ ​ ,其中,L\(x\|θP\)是对角线都是正数的下三角矩阵，且是唯一的。最终算法的Loss Function为

  ​$$L(θ^{Q})=E[(TargetQ−Q(x_{t},u_{t}|θ^{Q}))^{2}]$$  
  $$TargetQ=r_{t}+γV′(x_{t+1}|θ^{Q′})$$  
  $$Q(x_{t},u_{t}|θ^{Q})=V(x_{t}|θ^{V})+A(x_{t},v_{t}|θ^{A})$$  
  使用DQN的训练方式训练。

