# Others

## Actor-Critic method Introduction

> Menghao Wu, 2018-09-12,

Actor-Critic method IntroductionDRLValue based method & Policy based methodActor-Critic methodHow it works?AC's extensions

Hello, today I want to give a brief Intro about a rinforcement learning mehod: Actor-Critic algorithm.

### DRL

let's start from this basic graph of RL : well, as we know , the principle of RL is an agent continuously interact with the environment, the process is driven by reward. From this process, agent seems to become more and more smart and learn optimal behaviours by taking the actions with a positive or high reward and avoiding actions with the negative or lower reward. \[Fig.1\] ![](file:///var/folders/89/qnykkcts2gn7zdw58b8d_5dh01qz3z/T/abnerworks.Typora/image-20180910092716831.png?lastModify=1536674160)

On each time-step, The neural network of the Agent will choose a action according to the reward and state it received before and strive to acquire a high reward in this loop. Many classical algorithms base on these logic, like Deep Q learning.

Actually, It learns a value function map each state-action pair to a value. This method works well to a finite set of actions, because the agent tend to know on which state, which action will bring back a big value or reward. This we also call it **value-based** method. The NN updates its parameters rely on the value.

### Value based method & Policy based method

Besides Value-based methods, there are **Policy-based** methods. Here the Policy means the control strategy of the agent. So Policy based methods directly optimize the policy without using a value function. This one is useful to the tasks with a continuous or stochastic action space. The main problem of this method is finding a good score function to compute how good a policy is. A method is using total rewards of the episode. But, waiting until the end of an episode to calculate the reward will cause some problem, all actions in this episode will be look as on a same level even some were really good or bad.

So this is why researchers present the new algorithms.

### Actor-Critic method

![](file:///var/folders/89/qnykkcts2gn7zdw58b8d_5dh01qz3z/T/abnerworks.Typora/image-20180910092732871.png?lastModify=1536674160)

 \[Fig.2\] This is the AC method, it's a **hybrid method**, we using two NNs by combining Value and Policy.

* a Critic that measures how good the action taken is \(value-based\)
* an Actor that controls how our agent behaves \(policy-based\)

This model has a better score function, instead of waiting until the end of episode, we make an update at each step \(this is the so-called Temporal Difference learning\).

### How it works?

Next, let's explain how it works.

Imagine you play a video game with a friend who provides you some feedback. Now you are the Actor and your friend is the Critic.At the beginning, you don't know how to play, so you try some action randomly. you'll update your policy and be better at playing that game; On the other hand, your friend the Critic also update their own way to provide a better feedback next time.ACTOR update the policy function: ​ ; CRITIC update the value fucntion: ​ ; Both NNs run in parallel. We could tell that we have two set of weights\(​\), they should be optimized separately.

The formulas:

![](file:///var/folders/89/qnykkcts2gn7zdw58b8d_5dh01qz3z/T/abnerworks.Typora/image-20180910111734193.png?lastModify=1536674160)

**The process**

1. At each time-step t, we take the current state ​ and pass it as an input through Actor and Critic.
2. Policy takes the state, outputs an action ​, and receives a new state ​ and a reward ​.
3. The Critic computes the value of taking that action at that state; The Actor updates its policy parameters using this q value.
4. Actor produce the next action ​ and env gives the new state ​. The Critic then updates its value parameters;

By this way, the 2 NNs cooperations to make the agent enough smart handle tasks with a complex action space.

### AC's extensions

Base on this architecture, A2C, A3C and DDPG etc. develop.

