---
description: For curious AI
---

# Hierarchical RL

hierarchical, arranged in order of rank  ;   mitigate, make sth less serious;  

## Meta Learning Shared Hierarchies

> [https://blog.openai.com/learning-a-hierarchy/](https://blog.openai.com/learning-a-hierarchy/)  
> openAI, 2017,   
> [https://github.com/openai/mlsh](https://github.com/openai/mlsh)    code  
> concrete , 实在的,具体的.  execute 执行,实行,处死;   metric 公制的,公尺的;   off the shelf:  Not designed or made to order but taken from existing stock or supplies._‘off-the-shelf software packages’ ;_   formulate, v, create or prepare methodically.   tractably ,温顺地;    warmup 热身;     unroll 展开,铺开,显示;     rationale,基本原理;

1. Abstract We provide a concrete metric for measuring the strength of such hierarchies, leading to an optimization problem for **quickly reaching high reward on unseen tasks**.
2. utilize prior knowledge to master new tasks quickly. We propose a method for the end-to-end training of sub-policies that allow for quick learning on new tasks, handled solely by learning a master policy. - We will henceforth refer to our proposed method—**including the hierarchical architecture and optimization algorithm**—as MLSH, for metalearning shared hierarchies. - experiments: 2d continuous movement, gridworld navigation, 3d physics tasks. Our experiments show that our method is capable of learning meaningful sub-policies solely through interaction with a distributions of tasks, outperforming previously proposed algorithms.



## HRL NIPS workshop ppt

> nips , ppt , 2007  
> mitigate, make sth less serious;

1. advantages of HRL - faster learning. mitigates scaling problem - transfer of knowledge from previous tasks. generalization, shaping
2. Disadvantages of HRL - Need 'right' options: how to learn them? - Suboptimal behavior \(negative transfer, habits\) - more complex learning/control structure



## Learning Hierarchical Features for Scene Labeling

> Clement Farabet, Yann LeCun, 2013



