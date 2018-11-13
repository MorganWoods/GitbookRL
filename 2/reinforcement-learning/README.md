# REINFORCEMENT LEARNING

## DRL overview 🌀

### Deep Reinforcement Learning: An Overview

> Yuxi Li, 2017

> termination, ending; incorporate, unite, organized ;

1. An overview of recent exciting achievements of DRL;
2. Robotics:  - See Kober et al. \(2013\) for a survey of RL in robotics, Deisenroth et al. \(2013\) for a survey on policy search for robotics, and Argall et al. \(2009\) for a survey of robot learning from demonstration. - 5.2.2 learn to Navigate.
3. AlphaGo was built with techniques of deep CNN, supervised learning, reinforcement learning, and Monte Carlo tree search \(MCTS\) 

### A Brief Survey of Deep Reinforcement Learning 

> A good tutorial paper Alex sent to me.  
> Kai Arulkumaran, 2017;

> DRL is poised of revolutionise the field of AI.  
> stabilising method; initially 最初地; modifications 改变; prior to the current surge of interest of... 在当前潮流之前;  trade off 平衡; compelling insight 引人入胜的洞察;  mitigate 减轻,缓和;

1. The paper cover central algorithms including DQN, TRPO, asynchronous advantage ac.
2. 3 Challenges in RL:  The only signal of RL is the reward;  The observations have strong temporal correlations\(相互关系\) since they base on actions;  Credit assignment problem, which means in tasks like chess, we don't know how to assign credit for each actions since the success signal just comes from the final step;  
3. potential ways: **Model-based RL**:  incorporates prior knowledge to speed up learning. **Hierarchical RL**:  relies on hierarchical policies. This approach allows top-level policies to focus on higher-level goals, whilst subpolicies are responsible for fine control. **Multi-agent RL**: multiple agents and often non-stationarity introduced by other agents changing their behaviours as they learn; **Memory and Attention**: one of the first extensions DQN spawned\(孵出,引出\) was converting the DQN into an RNN. integrating info over long time periods. recurrent connections provide an efficient means of acting conditionally on temporally distant prior\(前面的\) observations. Further improvements by introducing attention, which is a technique where additional connections are added from the recurrent to lower layers, resulting in the deep attention recurrent Q N\(DRQN\). However, the DQN outperformed the DRQN and DARQN on games requiring quick reactions, where Q-values can fluctuate more rapidly. **Transfer learning**: exploit previously acquired knowledge from related tasks\(transfer learning, multitask learning, curriculum learning\). Particularly from training in _physics simulators_ \(物理仿真器\) with visual renderers\(渲染器\) and fine-tuning the models in the real world.
4. The DQN addressed the fundamental instability problem of using function approximation\(近似\) in RL. 

