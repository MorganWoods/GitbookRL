---
description: 'continuous control methods,'
---

# Continuous control

## Actor-critic series🌀

* Policy network select actions as an actor, value-based critic estimate the behavior of policy. update policy parameters according to critic's output.
* The proof that AC methods converge was shown in a brilliant Masters thesis by Konda

### Actor-Critic algorithms

> Konda, mit.

These are two-time-scale algorithms in which the critic uses TD learning with a linear approximation architecture and the actor is updated in an approximate gradient direction based on information provided by the critic.

### Asynchronous Methods for Deep Reinforcement Learning \(A3C\)

> Volodymyr Mnih. DeepMind. 2016.

* 异步梯度下降优化深度神经网络,提出了许多异步变体. 表现最好的变体是应用在 actor critic 上的并且超过 Atari 上的最新水平.使用多核 CPU 运行程序.解决 AC 算法不收敛问题.同时创建多个并行环境,多个 agent 隔离运行.主结构的参数更新受到副结构提交更新的不连续性干扰.更新相关度降低,收敛性提高.
* DRL 基于 experience replay, 但他的缺点是:每次交互需要计算,需要离策略学习算法.本文使用**多线程取代了 experience replay.**本文提出的算法: asynchronous one-step Q-learning; Asynchronous advantage actor-critic;

### Benchmarking Deep Reinforcement Learning for Continuous Control

> Yan Duan, OpenAI . 2016

* 一份 Benchmark. 文中列举的算法有: Reinforce;**TNPG**;RWR;REPS;**TRPO**;CEM;CMA-ES; **DDPG**
* 其中, TRPO 与 TNPG 效果优秀. 本文介绍了参数的选取与微调.
* 对 DDPG 的评价: 某些任务收敛快,由于样本的高效率.但是不稳定.并且训练过程中 policy 表现降级.对 reward 的范围较敏感,本文实验把 reward 设置为0.1,似乎提高了稳定性.
* TNPG 和 TRPO: 此二者表现尤其突出,证明了限制 policy 分布的改变可以提高学习的稳定性.
* 文末补充材料中有实验细节,可以作为参考.

### Combining Deep Q-Learning and Advantage Actor-Critic for Continuous Control \(A2S\)

> Rae C.Jeong, Waterloo,2018
>
>  源码 [https://github.com/raejeong/RaeboSchool](https://github.com/raejeong/RaeboSchool)

* 本文代码与 DDPG 的唯一区别是在选择最优动作方面: DDPG 是 PG 网络\( actor\)直接选择动作并执行, DQN 网络\(critic\)进行价值评估; 此文是根据 policy 网络分布选择几个候选动作,再用 DQN 网络价值评估,存储价值最高动作. 并执行.\(把确定性多做策略改为不确定性动作策略\)
* 实验效果优于 A2C

### Combining Policy Gradient And Q-Learning \(PGQL\)

> Brendan O'Donoghue,ICLR,2017

* 与 DDPG 齐名的 PGQL; 结合 PG 与离策略 Q-Learning,
* Q 更新方程做了改变.

### Continuous Control with Deep Reinforcement Learning \(DDPG\) 

> 2016年ICLR, Author: Timothy P.Lillicrap

* DDPG 算法从这里提出. AC 算法加 DQN 算法. 是 AC 的升级版.

### Continuous Deep Q-Learning with Model-based Acceleration \(NAF\)

> 2016年, Cambridge, 作者: Shixiang Gu

* 高维RL 基于 model-free 会增加采样的复杂程度,这篇文章主要降低连续空间采样复杂度.提出 NAF 可以使用 Qlearning 处理连续任务.使用 model-based 加速; model-based: 使用监督学习并且在 model 下优化出的策略.
* 本文三个贡献: Qlearning 在连续空间的使用; learned model; 加速 model free 连续学习.
* NAF: 不需要像 DDPG 那样训练两个网络,只需要训练一个;提出算法名字:continuous Q learning with NAF.
* 从文章实验来看, NAF 的更稳定,并且 reward 高,与 DDPG 相比.
* 为什么这个 NAF 的 Qlearning 可以在连续空间运用? ❓ 怎么选择动作的? 选择动作的网络如何更新? 和 DQN 的更新方式有区别么?

### Deterministic Policy Gradient Algorithms \(DPG\)    

> 2014, David Silver ,DeepMind

* DDPG base on DPG, which is deterministic actor-critic method.
* This paper prove policy gradient. adjust parameters to maximum object $$J(\pi_\theta))$$ function.
* Equivalence Between Policy Gradients and Soft Q-Learning
* The deterministic policy gradient is relative to stochastic PG.
* However, we show that the deterministic policy gradient does indeed exist, and further-more it has a simple model-free form that simply follows the gradient of the action-value function.
* In the stochastic case, the policy gradient integrates over both state and action spaces, whereas in the deterministic case it only integrates over the state space.
* To ensure that our deterministic policy gradient algorithms continue to explore satisfactorily, we introduce an off-policy learning algorithm. The basic idea is to choose actions according to a stochastic behaviour policy \(to ensure adequate exploration\), but to learn about a deterministic target policy \(exploiting the efficiency of the deterministic policy gradient\).

### High-Dimensional Continuous Control Using Generalized Advantage Estimation \(GAE\)

> John Schulman, ICLR, 2016

* Policy Gradient 方法对于 RL的两个挑战:需要大量的样本数据;尽管输入数据不稳定,但是也很难得到稳定的和持续的提高. 解决前者使用 value function 减少方差; 解决后者使用 **trust region optimization**.
* 使用二足四足机器人做实验, model free 的.
* 本文贡献: 提出 GAE 来纠正和提高 PG 的 variance reduction 的有效性;提出对于 Value function 使用 TRO 方法,健壮有效来训练神经网络;结合上二者,获得了在连续控制任务中有效的策略.
* 一个可能的未来工作是如何自适应或自动调节估计参数 
* > 摘自 [天津包子馅](https://zhuanlan.zhihu.com/p/29486661) : 基线函数的引用可以减小 PG 的方差. A\( 优势函数\)是动作值函数相对于值函数的优势, 若动作值函数比值函数大,那么又是函数为正,反之亦反; 对于 PG,优势函数为正时，其幅值为正，则参数沿着使得该轨迹概率增大的方向更新；优势函数为负时，策略梯度的幅值为负，则参数沿着使得该轨迹减小的方向更新。因此，采用优势函数时，算法的收敛速度更快。
  >
  > 然而，根据优势函数定义 ![](https://www.zhihu.com/equation?tex=A%5E%7B%5Cpi%7D%5Cleft%28s_t%2Ca_t%5Cright%29%3DQ%5Cleft%28s_t%2Ca_t%5Cright%29-V%5Cleft%28s_t%5Cright%29)，优势函数中的值函数常常利用逼近算法近似计算，因此往往会引入偏差。
  >
  > 优势函数的一步估计可写为：
  >
  > 从优势函数的一步估计中我们看到， ![](https://www.zhihu.com/equation?tex=V%5Cleft%28s_t%5Cright%29)和 ![](https://www.zhihu.com/equation?tex=V%5Cleft%28s_%7Bt%2B1%7D%5Cright%29)的真实值都是未知的，而是用到了估计值，因此优势函数存在偏差。
  >
  > GAE的方法是改进对优势函数的估计，将偏差控制到一定的范围内。其方法是对优势函数进行多步估计，并将这些多步估计利用衰减因子进行组合
  >
  > Shulman 提出广义优势函数估计 ![](https://www.zhihu.com/equation?tex=GAE%5Cleft%28%5Cgamma+%2C%5Clambda%5Cright%29)，利用指数加权平均从1步到无穷步的优势函数估计
  >
  > 该方法很好的评价了偏差和方差. 利用代替AC方法中的Critic会产生更好的效果? ? ?

### Learning Continuous Control Policies by Stochastic Value Gradients \(SVG\)

> Nicolas Heess, DeepMind ,2015

* 提出框架使用反向传播学习连续动作空间策略. 通过在 bellman 等式的确定性函数中增加噪声来增加策略随机性.
* 本文提出的方法是 SVG, 通过 re-parameterization 把噪声引入到策略和 model 中.

### Policy Gradient Methods for Reinforcement Learning with Function Approximation \(PG\)

> Richard S.Sutton, 1999

* 证明了 PG 可以收敛到全局最优点. 优化函数是 RL 必要的环节, 但是标准的方法优化价值函数和决定策略从理论上难以证明.这篇文章中我们探索了一个可供替代的方法,策略可以明确地用他自己的函数近似者表明, 独立于价值函数,并且根据关于策略参数的梯度期望来更新.我们主要的结果表明梯度可以写成适应于近似动作值和利益方程的形式.使用这个结果,我们首次证明使用任意的微分近似方程的策略迭代可以收敛到全局最优策略.
* the value-function approach has worked well in many applications, but has several limitations. first, it is oriented toward finding deterministic policies, whereas the optimal policy is often stochastic, selecting different actions with specific probabilities. Second, an arbitrarily small change in the estimated value of an action can cause it to be, or not be, selected.

### Q-prop: Sample-Efficent Policy Gradient With An Off-Policy Critic \(Q-Prop\)

> Shixiang Gu, Cambridge, ICLR, 2017

* 在面向现实实验中, model free DRL 会面对一个高采样复杂度. Batch PG 方法可以稳定学习,但是 cost 高方差,需要大量的 batches; TD 方法如 AC 和 QL, 采样多但是有偏差. 这篇文章提出方法: **结合 PG 的稳定性与 off policy RL 的效率**.提出了 Q prop 方法,他既有采样效率也有稳定性. 降低梯度估计的方差并且不引入偏置.
* 核心想法: 使用 critic 的 first-order Taylor expansion \(一阶泰勒展开\) 作为控制变量.解析梯度项评价过程,它既可以被看做使用off-policy的评价过程来减小策略梯度方法带来的方差，又被看作使用on-policy蒙特卡洛方法来修正评价梯度方法带来的偏差。
* PG 除了高方差,另一问题在于他需要 on-policy 样本,这使得他对样本敏感. Q prop 用来估计 PG 的.
* 通过使用确定性有偏估计作为控制变量的独特形式对于 MC PG 估计器,我们可以有效地使用两种形式的梯度信息来建造一个新估计器在实践中提高样本效率通过包含 off policy 采样同时保留 on policy MC PG 的稳定性.

### Trust Region Policy Optimization \(TRPO\)

> John Schulman, University of California, 2015

![](https://pic3.zhimg.com/80/v2-e519a12e0617dd0eb66de29db96af429_hd.jpg)

* 在策略梯度方法中还有很多有意思的课题，比如相容函数法，自然梯度法等等。但Shulman在博士论文中已证明，这些方法其实都是TRPO弱化的特例，说这些是再次强调TRPO的强大之处。策略梯度算法的硬伤就在更新步长 ​，当步长不合适时，更新的参数所对应的策略是一个更不好的策略，当利用这个更不好的策略进行采样学习时，再次更新的参数会更差，因此很容易导致越学越差，最后崩溃。所以，合适的步长对于强化学习非常关键。所谓合适的步长是指当策略更新后，回报函数的值不能更差。如何选择这个步长？或者说，如何找到新的策略使得新的回报函数的值单调增，或单调不减。这是TRPO要解决的问题。

  ![](../../.gitbook/assets/image%20%2810%29.png)

  值函数 ![](https://www.zhihu.com/equation?tex=V%28s%29)可以理解为在该状态下所有可能动作所对应的动作值函数乘以采取该动作的概率的和。更通俗的讲，值函数 ![](https://www.zhihu.com/equation?tex=V%28s%29)是该状态下所有动作值函数关于动作概率的平均值。而动作值函数 ![](https://www.zhihu.com/equation?tex=Q%28s%2Ca%29)是单个动作所对应的值函数，​$$Q-V$$​能评价当前动作值函数相对于平均值的大小。所以，这里的优势指的是动作值函数相比于当前状态的值函数的优势。如果优势函数大于零，则说明该动作比平均动作好，如果优势函数小于零，则说明当前动作还不如平均动作好。

  ​

* 优化控制策略的方法,可以保证单调递增.对有优化大量非线性策略很有效\(如神经网络\).不需要大量调试超参数.
* 许多策略优化算法分类为三个:policy iteration; policy gradient;derivative-free optimization 如 cross entropy 方法\(CEM\) 和 covariance matrix adaptation\(CMA\), 它把 cost 视为黑盒; 对于连续控制,如 CMA 的方法很成功; 本文,第一次提出最小化一个固定的替代 loss 函数保证策略提高通过 non-trivial step size, 还描述了两种变体,1 ,single-path 方法,这种可以应用于 model-free 环境, 2 , vine 方法\(滕树\),需要系统在特定的状态保存,仅仅在仿真时候适用.
* MDP$$(\mathcal{S} ,\mathcal{A} ,P,c,{\rho}_{0},\gamma)$$, 其中,$$c$$是 cost function, $${\rho}_{0}$$是初始状态的分布,$$\pi$$是随机策略,$${\eta}_{\pi}$$是**期望衰减 cost**. 然后是 Q,V,A, 与其他的不同,这里都是用 cost 代替了前人的 reward. $$\tilde{\pi}$$是另一个策略关注 的Advantage; 提出是非正规化的衰减 visitation 频率:$$\rho_{\pi}(s)=(P(s_{0}=s)+\gamma P(s_{1}=s)+\gamma^{2} P(s_{2}=s)+...)$$.
* TRPO 的后身是 PPO, 分布式是 DPPO.

### Reinforcement Learning with Deep Energy-Based Policies \(soft Q learning\)

> Tuomas Haarnoja, 2017

* ​

### Soft-Robust Actor-Critic Policy-Gradient \(SR-AC\)

> Esther Derman, Technion Israel institute, Google deepmind, 2018

* MDPs 有些不确定性, 有个 Robust MDPs 解决这个问题. 但是它带来了过分谨慎的结果 ; 本文集中学习一个 soft robust policy 通过吸收 soft robustness 和 online ac 算法 ; 本文的贡献: 1, 一个 soft-robust 衍生的 目标函数 为了 PG. 2. SRAC 算法使用随机优化来学习 . 3. 收敛证明. 4. 实验,展示了其效率.
* PG 方法一般的目标函数时最大化平均 reward function.
* soft-robust 目标函数…



## Naf

## Naf

## Naf

## Naf

## Naf

