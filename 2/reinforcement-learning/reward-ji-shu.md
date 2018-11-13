# Reward

## Deep Successor Reinforcement Learning

> Tejas D.Kulkarni, Harvard, NIPS 2016
>
> 参考此文总结: [http://swarma.blog.caixin.com/archives/164137](http://swarma.blog.caixin.com/archives/164137)

* 《Curiosity-driven Exploration by Self-supervised Prediction》 by UCB. ICML 2017. 《Learning to Act by Predicting the Future》 by IntelLab. ICLR 2017 \(oral\).《Deep Successor Reinforcement Learning》 by MIT & Harvard. NIPS 2016 workshop.这三篇都是解决 reward 稀疏的问题, 先收藏保留. 有的思想是奖励分成过程奖励与结果奖励.
* 本文用SR 方法求解 RL. 思路是将 value function 拆成两部分,一个是通过预测任务学习型到的表达,另一个是表达紧密相关激励函数reward shaping 对 RL 训练的好处,稳定性提高,收敛加快.

