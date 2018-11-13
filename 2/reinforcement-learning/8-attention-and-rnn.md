---
description: '每个标题用#标题; 按首字母排序;'
---

# Attention&RNN

##  Deep Attention Recurrent Q-Network

> Ivan Sorokin, 2015, hackathon DeepHack, Game 的一个队伍 5vision group  
> 本文被引用24次 NIPS  
> [https://5vision.github.io/2016/07/11/deep-attention-recurrent-q-network.html](https://5vision.github.io/2016/07/11/deep-attention-recurrent-q-network.html)

1. They present an extension of DQN by soft and hard attention mechanisms. DARQN=Deep Attention Recurrent Q-Network.
2. concise:简明的; analogue: 相似物; impressive 令人印象深刻的;Nonetheless 虽然如此,;systematic improvement 系统性提高,彻底提高; caption 字幕; induce 诱发;speedups, 加速名词; schematically 原理图;
3. LSTM   -  _\[5\]Sepp Hochreiter and Jurgen Schmidhuber. Long short-term memory. Neural Computation, 9\(8\):1735–1780, 1997._  
4. visual attention mechanisms \[6\]_Show, attend and tell: Neural image caption generation with visual atten- tion. arXiv preprint arXiv:1502.03044, 2015._ \[7\]_Advances in Neural Information Processing Systems 27, pages 2204–2212. Curran Associates, Inc., 2014._ \[8\]_Multiple object recognition with visual attention. In Proceedings ofthe International Conference on Learning Representations \(ICLR\), 2015. \[9\]_
5. the algorithm cannot master those games that require a player to remember events more distant than four screens in the past. It's the reason the following paper proposed the Deep Recurrent Q-Network\(DRQN\), a combination of LSTM and DQN. \[2\]_Matthew J. Hausknecht and Peter Stone. Deep recurrent q-learning for partially observable mdps. CoRR, abs/1507.06527, 2015._
6. 另一个 DQN 的缺点: 需要长时间训练. 有些方法未解决这个问题,使用 massively parallel version of algorithm.
7. 最近visual attention models的提高: caption generation\[6\] object tracking \[7,9\],machine translation. _\[9\]Learning where to attend with deep architectures for image tracking. Neural computation, 24\(8\):2151–2184, 2012_
8. 使用 attention 机制的主要好处: acquires the ability to select and then focus on relatively small informative \(提供信息的\) regions of an input image, thus helping to reduce the total number of parameters in the deep neural network and **computational operations\(计算操作\)** needed for training and testing it.
9. 每一个 step, CNN 收到当前状态的 visual frame, 然后产生一组 D feature maps, 每个有 mxm 维度; attention 网络把这些 maps 转换成一组向量形式,并且输出他们的线性组合,称为一个 context vector 环境向量; Recurrent 网络,在这个 LSTM 例子中,输入context vector, 随之有之前的隐藏状态和之前的记忆状态\(hidden state and memory state\) 并输出当前的 hidden state 被用于:一个线性层估计每个动作的 Q 值 和  用来attention 网络来生成下一步 context vector.
10. 本文另外介绍了两种 attention 机制, soft 和 hard; 算法在 atari 上做了实验.代码基于文章\[1\]且链接: [https://github.com/5vision/DARQN](https://github.com/5vision/DARQN) \[1\]Human-level control through deep reinforcement learning. Nature, 518\(7540\):529–533, 2015.
11. 其他人对本文评价摘录: DQN 加入 Attention 机制,使得学习具有方向性和指导性; DQN 将连续4帧输入 CNN, 之前会被遗忘.本文引入 lstm 到 DQN 中. 他们用了一帧的信息,算法可以抓住帧间信息.
12. 未来有前途的方向: 测试不同的技术来减少随机梯度变化程度; 应用不同方法来训练随机 attention 网络 



![9 - attention RNN](../../.gitbook/assets/image%20%283%29.png)

## Long Short-Term Memory

> Sepp Hochreiter , 德国慕尼黑工业大学;  
> 1997  
> [https://blog.csdn.net/baidu\_17806763/article/details/60957295](https://blog.csdn.net/baidu_17806763/article/details/60957295)   结合这个分析记录

![LSTM memory block](../../.gitbook/assets/image%20%281%29.png)

1. 通过 recurrent BP 方式学习存储随时间间隔变化的信息费时间.本文引入基于梯度的方法 LSTM.有效解决标签比较长的分类任务; LSTM 现在基本用在 RNN 中代替隐层单元,能够起到很好的长时间记忆效果.
2. RNN 共享权重,权重修正速度慢,只有短期记忆.卷积 bp through time 或 real time recurrent learning. 误差信号会随着反馈网络趋向于: 爆炸,消失,引发权重摆动,或浪费大量时间.
3. LSTM 引进乘法输入单元和输出单元,输入单元保护存储在记忆中的内容不受不相关的微小影响,同时,输出单元为了保护其他的单元不受当前不相关信号产生的微小影响.; 输入门,输出门,遗忘门;



