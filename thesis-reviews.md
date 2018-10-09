---
description: 'Reviews of thesis, textbook, project.'
---

# My reviews🎓

##  The cryptocurrency market

> Kreutzman Emil, Oct, 2018
>
> sensible 明智的.

> I'm currently attending the course "CS-E4870 - Research Project in Machine Learning", and prof. Gionis Aristides suggested that you would supervise my idea of exploring reinforcement learning within cryptocurrencies.  
>   
> **My own idea in short**:  
>   
> **- Apply reinforcement learning to "play" the cryptocurrency market, not predict rates  
> - Teach a deep neural network a policy, as described in "Q-learning" or possibly even "actor/critic" architectures by Deep Mind  
> - I already have a data pipeline in Tensorflow, and some rudimentary actor/critic NN code**  
>   
> When will you be available to have the first meeting, so we can discuss the scope and my efforts so far? \(Thu, Oct 4 for instance\)

**Scope:**- I'll tell you what I've done so far- We'll discuss the **requirements** and what **goals** would be sensible for the project

> below from: [https://medium.com/smileinnovation/how-to-make-profits-in-cryptocurrency-trading-with-machine-learning-edb7ea33cee4](https://medium.com/smileinnovation/how-to-make-profits-in-cryptocurrency-trading-with-machine-learning-edb7ea33cee4)

[LSTM](https://en.wikipedia.org/wiki/Long_short-term_memory) for “Long Short Time Memory” is a model design that processes past data to give a prediction. It’s a type of neural network.  
With [LSTM](https://en.wikipedia.org/wiki/Long_short-term_memory), it is a bit more complicated but the basics are the same:   
we send a “chronological series” to let the neural network find the next probable value. A huge dataset, build on a long period, is not needed. You need enough data, to split the dataset in small chronological chunks, for the neural network to be able to understand and predict the next value.  
We used a software to get the data from “Bittrex” — an exchange platform of cryptocurrency — then save it to a database. [\(Crawler Bittrex\)](https://github.com/sky54000/Scroller_bittrex_websocket_node)  
The first question that comes to our mind is what did we need to teach our AI ? Price prediction ? Crash prediction? Top or bottom prediction ? Human-like professional trading?  
To make predictions, three actions are available :   
- Buy \(green point\)  
- Sell \(red point\)  
- Wait \(rest of tickers, blue line\)

> below from : [http://www.wildml.com/](http://www.wildml.com/)

This is not a “price prediction using Deep Learning” post. So, if you’re looking for example code and models you may be disappointed. Instead, I want to talk on a more high level about why learning to trade using Machine Learning is difficult, what some of the challenges are, and where I think Reinforcement Learning fits in. If there’s enough interest in this area I may follow up with another post that includes concrete examples.

**Trade**

A new Trade has happened. Each trade has a timestamp, a unique ID assigned by the exchange, a price, size, and side, as discussed above. If you wanted to plot the price graph of an asset, you would simply plot the price of all trades. If you wanted to plot the candlestick chart, you would window the trade events for a certain period, such as five minutes, and then plot the windows.

```text
{
    "time": "2014-11-07T22:19:28.578544Z",
    "trade_id": 74,
    "price": "10.00000000",
    "size": "0.01000000",
    "side": "buy"
}
```

with DRL

**Agent**

Let’s start with the easy part. The agent is our trading agent. **You can think of the agent as a human trader who opens the GUI of an exchange and makes trading decision based on the current state of the exchange and his or her account**.

Environment: assume we’re interacting with a single complex environment that includes the behavior of all other agents.

State: we are dealing with a Partially Observable Markov Decision Process \(POMDP\). What the agent observes is not the actual state ![S\_t](http://s0.wp.com/latex.php?latex=S_t&bg=ffffff&fg=000&s=0) of the environment, but some derivation of that.  there are a few other things that the observation must include, such as the current account balance, and open limit orders, if any.  
Time scale, 

**Action Space**

In Reinforcement Learning, we make a distinction between discrete \(finite\) and continuous \(infinite\) action spaces. Depending on how complex we want our agent to be, we have a couple of choices here.   
The simplest approach would be to have three actions: **Buy, Hold, and Sell**. That works, but it limits us to placing market orders and to invest a deterministic amount of money at each step.  **The next level of complexity** would be to let our agent learn how much money to invest, for example, based on the uncertainty of our model. That would put us into a continuous action space, as we need to decide on both the \(discrete\) action and the \(continuous\) quantity. An even more complex scenario arises when we want our agent to be able to place limit orders. In that case our agent must decide the level \(price\) and the quantity of the order, both of which are continuous quantities. It must also be able to cancel open orders that have not yet been matched.

**Reward Function**

There are several possible reward functions we can pick from. An obvious one would the _Realized PnL_ \(Profit and Loss\). The agent receives a reward whenever it _closes_ a position, e.g. when it sells an asset it has previously bought, or buys an asset it has previously borrowed. The _net profit_ from that trade can be positive or negative. That’s the reward signal. As the agent maximizes the total cumulative reward, it learns to trade profitably. This reward function is technically correct and leads to the optimal policy in the limit. However, rewards are sparse because buy and sell actions are relatively rare compared to doing nothing. Hence, it requires the agent to learn without receiving frequent feedback.

An alternative with more frequent feedback would be the _Unrealized PnL_, which the net profit the agent would get if it were to close all of its positions immediately. For example, if the price went down after the agent placed a buy order, it would receive a negative reward even though it hasn’t sold yet. Because the Unrealized PnL may change at each time step, it gives the agent more frequent feedback signals. However, the direct feedback may also bias the agent towards short-term actions when used in conjunction with a decay factor.

Both of these reward functions naively optimize for profit. In reality, a trader may want to minimize risk. A strategy with a slightly lower return but significantly lower volatility is preferably over a highly volatile but only slightly more profitable strategy. Using the [Sharpe Ratio](https://www.quantinsti.com/blog/sharpe-ratio-applications-algorithmic-trading/) is one simple way to take risk into account, but there are many others. We may also want to take into account something like [Maximum Drawdown](https://www.investopedia.com/terms/d/drawdown.asp), described above.  One can image a wide range of complex reward function that trade-off between profit and risk.

## Graph signal sampling via reinforcement learning

> Master's thesis, Oleksii Abramenko , 2018 , pages 58,  
> cardinality:势 ;  disposal 处理,管理; applicability 适用性;

1. Graph signal processing area and it's practical applications such as compression and image denoising. This thesis applys RL theory to aforementioned problem. He propose two RL based sampling algorithms.
2. Abbreviations: GSP: graph signal processing   SLP:sparse label propagation    LASSO: least absolute shrinkage and selection operator    TV: total variation    SBM: stochastic block model     RWS: random walk sampling     URS: uniform random sampling
3. **contents**:  C1: Intro  C2: ML for GSP    C3: RL fundamentals   C4: Graph signal sampling as RL problem   C5: experiments   C6:discussion   C7:conclusions
4. The nodes of graph: network elements; edges: the connections of elements; 1st challenge: representative samples selection; 2nd challenge: how to recover the required info. _**Goal**: Learn a sampling policy choosing signal samples with small reconstruction error_.
5. Upper confidence bound approach 可以更好的替代 贪婪算法; 他能衡量准确度.
6. 看到了4.2章. 先看别的. we consider the selection of the nodes to be sampled being carried out by an “agent” which crawls over the data graph G A specific action a 2 A refers to the number of hops the sampling agent performs starting at the current node it to reach a new node it+1, which will be added to the sampling set, i.e., M := M \[ {it+1}

> correspond to; whereas; reasoning, Noun, The action of thinking about something in a logical, sensible way.; come down to, 归结为; preclude, prevent from happening, make impossible; derivative 衍生; consequently, as a result; be identical to , similar as     ;     represent 代表,表示,呈现;       proportional 成比例的; consensus, general agreement 共识       ;  essence, intrinsic nature or indispensable quality of sth,本质        ; responsible for ...     ; originate from 源于;  consecutive, following each other continuously,连续的;  underlying 相关;   denote , be a sign of, indicate;   linearly decrease 线性;   proceed, go on, begin a course of action 继续进程;   course, 课程,进程,路线.;    amount to , 共计, 意味着, 发展成;  retain, continue to have sth, keep possession of.;    synchronise, sync;    tend to 趋于;  reward 报酬,答谢;   basic adj,  basics n;   vestly, adv 大大地;     hop 跳跃;     prescribe 规定,药方;      assess 评估;      convex 凸的.;    compact 合同,契约;      provoke 激励,煽动;       detrimental, harmful. ;       ambiguous 模棱两可的;     paradigm范例   ;       derivation 引出,诱导,来历;      problematic 问题的,有疑问的;       disputable  有争议的,可疑的;       interval   间隔, 休息;       underlying 相关的;       accordance   符合,同意;       consistent  一贯;        prospect 前途,景色;         in comparison to;         tendency 趋向,趋势;           intractability   难解;         stateless 无状态;           diameter 直径;       cliques  派系,小集团;      depict  描述;



## A gentle Introduction of RL

> A Fixed Point View on Cleaning Robots - Alexander Jung  
> Reviewed by Menghao Wu

#### 1 Introduction

* Actually,I suppose the relationship between the cleaning robot and the grid world is weak. Since robot's observation is snapshots or distance information , however the agent's observation in the grid world is a birds-eye view \(agent know everything e.g. obstacles, terminal … in grid world\). Logically,it seems that we should use a camera on the rooftop to see the cleaning robot and the floor and these should be the observation of robot. From my point of view, grid world is good enough to describe the RL's process

#### 2 MDP

* 2.1 The Elements of MDP
  * The hypothesis of Rumba can determine the position is wise .
  * To my way of thinking, Markov property's Introduction should be put at the beginning of **MDP** paragraph, and the intrduction should be more detailed because it is a basic ideal of all RL setting . It cuts off the relationship between the past and future states, but using discounted  reward to connect the whole process. Then  is a essential factor of MDP tuple.
  * "The discounted factor  trades-off the importance of immediate and future rewards" ← this sentence I found in paper seems more accurate to introduce  .
* 2.2 Policies
  * Up to **now** \(know\) ? 1st sentence of 2.2
* 2.5 Policy Improvement
  * Policy improvement via chooseing the action maximums the Q value, this is a value-based way, with the corresponding Policy-based methods are often used for Continuous control problem. Therefore this section is a thought to handle the discrete actions' tasks, the conditions of the scene can be introduced in detail.

#### 3 Computing Optimal Policies for Known MDPs

* 3.3 Return Shaping
  * Thsi section is extremely good since the metaphor is very appropriate. Return shaping is potential technique to improve perfoemance of training.

#### 4 Machine Learning as Low-Level AI

* I have used the thought as you write to process snapshots as labels relate to the location information. Eventhough the results are overfitting , it is a good idea to map location from the snapshot. However There is a big problem in real world because the robot moving Continuously so it often shots scene not in the labeled data. This will cause robot confuseing and labeled data not big enough too. robot can take snapshots in different angles , directions, locations . So it will come across many hard problem to handle in the real environment.

