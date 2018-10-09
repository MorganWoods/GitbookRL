---
description: Paper summary
---

# Paper Note📝

## The Plan of reading paper 🌀

1. continuous control

> 下面是暂存于此未分类文章记录

## Learning to act by predicting the future.

> ICLR 2017, intel labs.  
> sensorimotor 感觉运动的; immersive 身临其境的; extraneous 外部的,无关的; extensive experiment ,广泛的,大量的; sophisticated 尖端的; assist 帮助; overcome challenges;  depart from... 不同于; constitute 组成,构成; pertain to 适合,属于,关于; ammunition 弹药; in terms of... 在..方面; occasional 偶尔的; take ... into account, 把...考虑进去; perspective,前景,透视,观点,想法; date back decades; advantageous, 有利的;

1. 本文方法使用高维传感器流和低维度测量流;这个结构提供监督信号可以在交互中训练运动感知控制模型.这个模型使用监督学习技术训练不需要 extraneous supervision. 图像输入. supervised learning is concerned with learning input-output mappings, unsupervised learning aims to find hidden structure in data, and reinforcement learning deals with goal-directed behaviour.
2. 本文方法不同于奖励机制的 RL,而是使用 sensory input stream $$\{s_t\}$$, 和 measurements $$\{m_t\}$$; sensory stream 通常是高维的包含图像,声音等细节,measurement stream 低维的通常是此刻 state; 后者大多数为姿态,结构,血蓝值,关卡等等相关的状态量; 本文 guiding observation 把 temporal structure of sensory 和 measurement streams interlock 互锁起来,形成了丰富的监督的信号; 给了 sensory input, measurements, 和 goal, 智体就可以训练成可以预测在未来 measurements 下不同actions的结果了. 两个重要优点: 1-与偶尔的标量 reward 相比,measurements stream 提供丰富的和稠密的监督可以稳定并加速训练. 2-提出的公式训练过程中不需要有明确的目标,他能预测将来的目标; 

## Lists of Paper 🌀

#### DRL paper list

{% embed url="http://www.voidcn.com/article/p-rlbfnjbt-gc.html " %}

这个网页列出增强学习文章与分类列表,很有参考价值,分类详细.

改进目标Q值计算：Deep Reinforcement Learning with Double Q-learning 

改进随机采样：Prioritized Experience Replay 

改进网络结构，评估单独动作价值：Dueling Network Architectures for Deep Reinforcement Learning \( 本文为ICML最佳论文之一） 

改进探索状态空间方式：（1）Deep Exploration via Bootstrapped DQN （2）Incentivizing Exploration In Reinforcement Learning With Deep Predictive Models 

改变网络结构，增加RNN：Deep Recurrent Q-Learning for Partially Observable MDPs（非DeepMind出品，效果很一般，谈不上改进，本文也不考虑讲解） 

实现DQN训练的迁移学习：（1）Policy Distillation （2） Actor-Mimic: Deep Multitask and Transfer Reinforcement Learning 

解决高难度游戏Montezuma‘s Revenge：Unifying Count-Based Exploration and Intrinsic Motivation 

加快DQN训练速度：Asynchronous Methods for Deep Reinforcement Learning （这篇文章还引出了可以替代DQN的A3C算法，效果4倍Nature DQN） 

改变DQN使之能够应用在连续控制上面：Continuous Deep Q-Learning with Model-based Acceleration

{% embed url="https://github.com/junhyukoh/deep-reinforcement-learning-papers/blob/master/README.md\#continuous-control" caption="all DRL" %}

 

#### 

#### GAN paperlist

{% embed url="https://github.com/zhangqianhui/AdversarialNetsPapers   " %}

{% embed url="https://github.com/hindupuravinash/the-gan-zoo" %}

#### 

#### Multi-agent

{% embed url="http://lantaoyu.com/posts/2017/06/marl-papers/" %}

