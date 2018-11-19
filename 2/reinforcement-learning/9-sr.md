---
description: Successor Representation 技术
---

# SR

### Deep Successor Reinforcement Learning

> Tejas D.Kulkarni, Harvard, NIPS 2016  
> Code and other resources – [https://github.com/Ardavans/DSR](https://github.com/Ardavans/DSR)  
> 参考此文总结: [http://swarma.blog.caixin.com/archives/164137](http://swarma.blog.caixin.com/archives/164137)

> occupancy 占有; appealing properties; distal 末端的; factorization 因式分解; bottleneck 瓶颈; diverse 不同的,多种多样的; sensitivity 敏感; infer 推断; Specifically 独有地, ; dot product 点乘; representation 代理,代表; adapt 适应; intrinsic 内在的固有的, extrinsic 外在的,非本质的;

![&#x4E0B;&#x9762;&#x662F;SR&#x6A21;&#x5757;,&#x5DE6;&#x9762;&#x662F; CNN, &#x4E0A;&#x9762;&#x662F;&#x7ACB;&#x5373; reward](../../.gitbook/assets/image%20%288%29.png)

1. 《Curiosity-driven Exploration by Self-supervised Prediction》 by UCB. ICML 2017. 《Learning to Act by Predicting the Future》 by IntelLab. ICLR 2017 \(oral\).《Deep Successor Reinforcement Learning》 by MIT & Harvard. NIPS 2016 workshop.这三篇都是解决 reward 稀疏的问题, 先收藏保留. 有的思想是奖励分成过程奖励与结果奖励.
2. 学习价值方程有 model free 和 base 的算法, 这里有个新方法, successor representations\(SR\).本文用SR 方法求解 RL. 思路是将 value function 拆成两部分,一个是通过预测任务学习型到的表达\(reward predictor\),另一个是表达紧密相关激励函数reward shaping 对 RL 训练的好处,稳定性提高,收敛加快\(successor map\).
3. 本文提出 DSR, 泛化了 SR.使用端到端 DRL framework. 其有几个 appealing properties: 提高对末端 reward 改变的敏感程度,能抽出瓶颈状态; 本文用了两个环境证明: grid world 和 Doom 游戏 engine.
4. Successor Representation \(SR\) : it factors\(引入\) the value function into a predictive representation and a reward function. 尤其, 一个状态的价值函数可以表示为长久 reward 和立即 reward 的点乘.

   使用 SR 代表 value function. SR 能更快适应末端 reward 变化,比 model free 要强.

5. 本来的 Q 值计算是使用累计衰减 reward 计算; SR 形式就是换了个方向,使用 SR 乘立即 reward 来计算 Q 值.

