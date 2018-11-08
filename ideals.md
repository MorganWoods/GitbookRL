---
description: "Tasks and ideas \uD83D\uDCA1"
---

# Tasks, ideas, thoughts🔅

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
* finding real application direction of RL.

### ➡ Potential tasks

* enhance conference talking ability.

## Planning 🌀

### ➡ Journal\_2018

Oct.5 - Oct.15 finish rewriting  
Oct.15-Oct.30. finish submit.

Nov.6-Nov.9, submitting.  
Nov.7: submitted

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

### ➡ Recommender system??

## General Thoughts 🌀

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

> [https://www.oreilly.com/ideas/practical-applications-of-reinforcement-learning-in-industry](https://www.oreilly.com/ideas/practical-applications-of-reinforcement-learning-in-industry)  
> ⬇️ Nov.8.2018

Generally speaking, the goal in RL is learning how to map observations and measurements to a set of actions while trying to maximize some long-term reward.  
 RL poses a different set of challenges from traditional [online learning](https://en.wikipedia.org/wiki/Online_machine_learning), in that you often [have some combination](https://www.safaribooksonline.com/library/view/oreilly-artificial-intelligence/9781491985250/video314916.html?utm_source=oreilly&utm_medium=newsite&utm_campaign=20171129_ben_lorica_reinforcement_learning_in_industry_body_text_have_some_combination_link) of delayed feedback, sparse rewards, and \(most importantly\) the agents in question are often able to affect the environments with which they interact.  
Deep learning as a machine learning technique is beginning to be used by companies on a variety of machine learning applications. RL hasn’t quite found its way into many companies, and my goal is to sketch out some of the areas where applications are appearing.

**Industrial automation**   
Bonsai company recently listed the following criteria for when RL might be useful to consider:

* You’re using simulations because your system or process is too complex \(or too physically hazardous\) for teaching machines through trial and error.
* You’re dealing with large state spaces.
* You’re seeking to augment human analysts and domain experts by optimizing operational efficiency and providing decision support.

**Data science and machine learning**  
 Several research groups have proposed using RL to make the process of designing neural network architectures more accessible \([MetaQNN from MIT](https://arxiv.org/abs/1611.02167) and [Net2Net operations](https://arxiv.org/abs/1707.04873)\). [AutoML from Google](https://research.googleblog.com/2017/05/using-machine-learning-to-explore.html) uses RL to produce state-of-the-art machine-generated neural network architectures for computer vision and language modeling.

Looking beyond tools that simplify the creation of machine learning models, there are some who think that RL will prove useful in assisting software engineers write computer programs.

**Education and training**  
Online platforms are beginning to experiment with using machine learning to create personalized experiences. Several researchers are investigating the use of RL and other machine learning methods in [tutoring systems and personalized learning](http://pact.cs.cmu.edu/pubs/New%20potentials%20for%20ITS-source.pdf). The use of RL can lead to training systems that provide custom instruction and materials tuned to the needs of individual students. [A group of researchers is developing RL algorithms and statistical methods](https://www.technologyreview.com/s/603504/playtimes-over/) that require less data for use in future tutoring systems.

#### Health and medicine

#### Text, speech, and dialog systems ⭐️

Companies collect a lot of text, and good tools that can help unlock unstructured text will find users. Earlier this year, AI researchers at SalesForce used [deep RL for abstractive text summarization](https://www.salesforce.com/products/einstein/ai-research/tl-dr-reinforced-model-abstractive-summarization/) \(a technique for automatically generating summaries from text based on content “abstracted” from some original text document\). This could be an area where RL-based tools gain new users, as many companies are in need of better text mining solutions.

[RL is also being used to allow ](https://www.microsoft.com/en-us/research/publication/towards-end-end-reinforcement-learning-dialogue-agents-information-access/)[dialog systems](https://www.microsoft.com/en-us/research/publication/towards-end-end-reinforcement-learning-dialogue-agents-information-access/) \(i.e., [chatbots](https://www.oreilly.com/ideas/bots-what-you-need-to-know)\) to learn from user interactions and thus help them improve over time \(many enterprise chatbots currently rely on decision trees\). This is an [active area of research](https://arxiv.org/abs/1709.02349v1) and VC investments: see [Semantic Machines](http://www.semanticmachines.com/technology/) and [VocalIQ](https://www.technologyreview.com/s/603613/siri-may-get-smarter-by-learning-from-its-mistakes/)—acquired by Apple.

#### Media and advertising ⭐️

Microsoft [recently described](https://arxiv.org/abs/1606.03966) an internal system called Decision Service that has since been made [available on Azure](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-decision-service/custom-decision-service-overview). [This paper](https://arxiv.org/abs/1606.03966)describes applications of Decision Service to content recommendation and advertising. Decision Service more generally targets machine learning products that suffer from failure modes including “feedback loops and bias, distributed data collection, changes in the environment, and weak monitoring and debugging.”

Other applications of RL include [cross-channel marketing optimization](https://dl.acm.org/citation.cfm?id=1016912) and [real time bidding systems](https://arxiv.org/abs/1701.02490) for online display advertising.

#### Finance

### ➡ shortcoming

> [https://www.alexirpan.com/2018/02/14/rl-hard.html](https://www.alexirpan.com/2018/02/14/rl-hard.html)     ⬇️  
> shortcomings of RL















## NaN

  




