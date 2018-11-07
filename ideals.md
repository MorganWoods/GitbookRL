---
description: "Tasks and ideas \uD83D\uDCA1"
---

# Tasks & ideas🔅

## Tasks 🌀

### ➡ Upcoming tasks

* 看文章,准备下一篇.
* ~~把 Reinforcement Learning 相关笔记与知识迁移到 Gitbook 上 迁过去吧,记笔记看笔记方便一些.但这里保存原来的几个文件,且暂时停止更新.~~

  ~~已经迁移到 gitbook 上的 RL 文档中:~~[~~https://kiitos.gitbook.io/rl/~~](https://kiitos.gitbook.io/rl/) 目前纸质笔记迁移中, ~~接下来把工具操作相关文档也迁移到 gitbook 的 tool 中.~~

* ~~写实验部分时候参考别的论文的实验用语. 加油吧,提高效率.~~
* ~~完成论文\(20-May\), 修改论文\(30-May\); 加 on policy 版本算法\(30-May\); 五月末完成论文, 6月准备投稿.~~
* ~~查找会议与期刊.~~
* moving OneNote to Gitbook; Moving formulas and figures in paper to RLKnowledge folder. Additional, your paper note.
* recording and classifying references.
* Writing CV; interview.

### ➡ Potential tasks

* enhance conference talking ability.

## Planning 🌀

### ➡ Journal\_2018

Oct.5 - Oct.15 finish rewriting  
Oct.15-Oct.30. finish submit.

Nov.6-Nov.9, submitting.

### ➡ Conference\_2019.4 

April,2019, finish the 1st draft.   
May,2019, have a journal letter.

## All ideals 🌀

> reward system. Lstm mechanism;  
> For real applications, need further focus on: big data, video/image processing, deep learning, recommender system.

* Gridworld 改成机器人类似的形式,把终点信息加入 reward 中,加强其泛化能力;
* 类似 NAF 那样把两个网络完成的事弄成一个网络完成,看可行不可行;
* gazebo 环境的开发
* [https://www.youtube.com/watch?v=EaY5QiZwSP4](https://www.youtube.com/watch?v=EaY5QiZwSP4) 一个无人车模拟,可以尝试
* 研究 LSTM 算法
* 关于奖励稀疏的问题, 最终奖励过于稀疏不利于训练. 参考这个网页的解释[http://swarma.blog.caixin.com/archives/164137](http://swarma.blog.caixin.com/archives/164137)也可以归类于 reward shaping 类别下.
* VIN 应用到连续空间可行么?
* 使用增强网络建造神经网络结构.
* using imageNet to finish some work? 关于图像方面是一个重点,还有卷积神经网络.
* GAN and RL cooperation?
* Transfer learning&gt;? GAN should be useful for it.
* 关于贪婪算法,也有提升空间, oleksii 论文说的 Upper confidence bound 算法.
* Hierarchical reinforcement learning.
* Dual attention technique.
* Researching the practical directions with RL method.

### ➡ experience replay

* 对 reward 的机制下手, 让他得分惩罚更加合理有利于收敛. reward shaping
* PER 那个, 以后注意一下, 经历分出优先级使用.

### ➡ RL designs network??

## General Note 🌀

### ➡ RL in real applications

> 7, Nov, 2018

Now I realise a problem of RL, that is it cannot work without an environment, which is a built model for agent to interact. Next step, I will focus on some real applications of RL such as computer vision, image processing, etc. I should dig in.

> [https://towardsdatascience.com/applications-of-reinforcement-learning-in-real-world-1a94955bcd12](https://towardsdatascience.com/applications-of-reinforcement-learning-in-real-world-1a94955bcd12)  
> ⬇️

RL is a very general framework for learning sequential decision making tasks. This article aims to investigate the breadth and depth of RL applications in real world.

* Resources management in computer clusters Paper"resource management with DRL" shows using RL automatically learn to allocate and schedule computer resources to waiting jobs, with the objective to minimize the average job slowdown. **State space** was formulated as the current resources allocation and the resources profile of jobs. For **action space**, they used a trick to allow the agent to choose more than one action at each time step. **Reward was** the sum of \(-1/duration of the job\) over all the jobs in the system. Then they combined REINFORCE algorithm and baseline value to calculate the policy gradients and find the best policy parameters that give the probability distribution of actions to minimize the objective. Click here to view the code on [Github](https://github.com/hongzimao/deeprm).
* Traffic light control In the paper “Reinforcement learning-based multi-agent system for network traffic signal control”[\[3\]](http://web.eecs.utk.edu/~itamar/Papers/IET_ITS_2010.pdf), researchers tried to design a traffic light controller to solve the congestion problem. Tested only on simulated environment though, their methods showed superior results than traditional methods and shed a light on the potential uses of multi-agent RL in designing traffic system.
* Robotics There are tremendous work on applying RL in Robotics. Readers are referred to [\[10\]](https://www.ias.informatik.tu-darmstadt.de/uploads/Publications/Kober_IJRR_2013.pdf) for a survey of RL in Robotics. In particular, [\[11\]](https://arxiv.org/pdf/1504.00702.pdf) trained a robot to learn policies to map raw video images to robot’s actions. The RGB images were fed to a CNN and outputs were the motor torques. The RL component was the guided policy search to generate training data that came from its own state distribution.
* Web system configuration There are more than 100 configurable parameters in a web system and the process of tuning the parameters requires a skilled operator and numerous trail-and-error tests. The paper “A Reinforcement Learning Approach to Online Web System Auto-configuration” [\[5\]](http://ranger.uta.edu/~jrao/papers/ICDCS09.pdf) showed the first attempt in the domain on how to do autonomic reconfiguration of parameters in multi-tier web systems in VM-based dynamic environments.
* **Personalized Recommendations ⭐️**  Guanjie et al. have applied RL in news recommendation system in a paper titled “DRN: A Deep Reinforcement Learning Framework for News Recommendation” to combat the problems [\[1\]](http://www.personal.psu.edu/~gjz5038/paper/www2018_reinforceRec/www2018_reinforceRec.pdf).
* **Bidding and Advertising ⭐️ \(this could be applied to IT service\)**

  Researchers from Alibaba Group published a paper “Real-Time Bidding with Multi-Agent Reinforcement Learningin Display Advertising” [\[6\]](https://arxiv.org/pdf/1802.09756.pdf) and claimed that their distributed cluster-based multi-agent bidding solution \(DCMAB\) has achieved promising results and thus they plan to conduct a live test in Taobao platform.

* Deep learning CNN, RNN, GAN.
* There are several things needed before RL can be applied: ⭐️

  *  You may want to check if your problem has some of the following characteristics before deciding to use RL: a\) trial-and-error \(can be learned to do better by receiving feedback from the environment\); b\)delayed rewards; c\)can be modeled as MDP; d\)your problem is a control problem.
  * A simulated environment: Lots of iterations are needed before a RL algorithm to work.
  * MDP: You world need to formulate your problem into a MDP. You need to design the state space, action space, reward function and so on. Your agent will do what it is rewarded to do under the constraints. You may not get the results you want if you design the things differently.

### ➡ shortcoming

> [https://www.alexirpan.com/2018/02/14/rl-hard.html](https://www.alexirpan.com/2018/02/14/rl-hard.html)     ⬇️  
> shortcomings of RL

  




