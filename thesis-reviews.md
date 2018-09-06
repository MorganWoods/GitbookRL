---
description: aalto's thesis reviews
---

# Thesis reviews🎓

## Graph signal sampling via reinforcement learning

> Master's thesis, Oleksii Abramenko , 2018 , pages 58,
>
> cardinality:势 ;  disposal 处理,管理; applicability 适用性;

1. Graph signal processing area and it's practical applications such as compression and image denoising. This thesis applys RL theory to aforementioned problem. He propose two RL based sampling algorithms.
2. Abbreviations: GSP: graph signal processing   SLP:sparse label propagation    LASSO: least absolute shrinkage and selection operator    TV: total variation    SBM: stochastic block model     RWS: random walk sampling     URS: uniform random sampling
3. **contents**:  C1: Intro  C2: ML for GSP    C3: RL fundamentals   C4: Graph signal sampling as RL problem   C5: experiments   C6:discussion   C7:conclusions
4. The nodes of graph: network elements; edges: the connections of elements; 1st challenge: representative samples selection; 2nd challenge: how to recover the required info. _**Goal**: Learn a sampling policy choosing signal samples with small reconstruction error_.
5. Upper confidence bound approach 可以更好的替代 贪婪算法; 他能衡量准确度.
6. 看到了4.2章. 先看别的. we consider the selection of the nodes to be sampled being carried out by an “agent” which crawls over the data graph G A specific action a 2 A refers to the number of hops the sampling agent performs starting at the current node it to reach a new node it+1, which will be added to the sampling set, i.e., M := M \[ {it+1}

> correspond to; whereas; reasoning, Noun, The action of thinking about something in a logical, sensible way.; come down to, 归结为; preclude, prevent from happening, make impossible; derivative 衍生; consequently, as a result; be identical to , similar as     ;     represent 代表,表示,呈现;       proportional 成比例的; consensus, general agreement 共识       ;  essence, intrinsic nature or indispensable quality of sth,本质        ; responsible for ...     ; originate from 源于;  consecutive, following each other continuously,连续的;  underlying 相关;   denote , be a sign of, indicate;   linearly decrease 线性;   proceed, go on, begin a course of action 继续进程;   course, 课程,进程,路线.;    amount to , 共计, 意味着, 发展成;  retain, continue to have sth, keep possession of.;    synchronise, sync;    tend to 趋于;  reward 报酬,答谢;   basic adj,  basics n;   vestly, adv 大大地;     hop 跳跃;     prescribe 规定,药方;      assess 评估;      convex 凸的.;    compact 合同,契约;      provoke 激励,煽动;       detrimental, harmful. ;       ambiguous 模棱两可的;     paradigm范例   ;       derivation 引出,诱导,来历;      problematic 问题的,有疑问的;       disputable  有争议的,可疑的;       interval   间隔, 休息;       underlying 相关的;       accordance   符合,同意;       consistent  一贯;        prospect 前途,景色;         in comparison to;         tendency 趋向,趋势;           intractability   难解;         stateless 无状态;           diameter 直径;       cliques  派系,小集团;      depict  描述;

