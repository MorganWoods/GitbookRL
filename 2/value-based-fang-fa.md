---
description: 基于价值的算法
---

# Value based methods

* Parameter Space Noise for Exploration

  > Matthias Plappert, Open AI, 2018

  * DRL generally inject noise exploration in the action space. 一种可替代的方法是直接向参数中加入噪声.这样可以使得探索更加一致性并且得到丰富的表现集合. 他验证了这种方法结合传统的 RL 无论在策略离策略 DQN,DDPG,TRPO 离散或连续动作空间都表现很好.

* Universal Value Function Approximators \(UVFA\)

  > Tom Schaul, David Silver, Google DeepMind, 2015

  * 引入一个 universal value function approximator​$$V(s,g;\theta)$$, 不仅概括了状态 s 还有 goals g, 建立了一个有效的监督学习技术, 通过因式分解已观测的 values 为不同的向量为 state 和 goal. 然后学习 mapping 从 s 到 g 对这些分解的嵌入的向量. 最终结果 UVFA 可以成功generalise\(概括,推广,普及\)之前没见过的 goals.
  * 看不懂了,

* Value Iteration Networks \(VIN\)

  > Aviv Tamar, UC Berkeley, NIPS 最佳论文 ,2016
  >
  > [https://github.com/avivt/VIN](https://github.com/avivt/VIN)[https://github.com/TheAbhiKumar/tensorflow-value-iteration-networks](https://github.com/TheAbhiKumar/tensorflow-value-iteration-networks)

  * 把一个规划程序嵌入到神经网络结构中提高泛化能力.
  * 将奖励函数和转移函数参数化能求导,在策略求解中引入 **attention** 机制

