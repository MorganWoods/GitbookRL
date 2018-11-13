---
description: Question collection
---

# Q&A

## Policy gradient 🌀

### ➡ explain the Loss function of PG

Loss = -log\(prob\)\*vt

log\(prob\) denotes the surprising degree of selecting action a on state s.   
上式中log\(prob\)表示在状态 s 对所选动作 a 的吃惊度, 如果概率越小, 反向的log\(prob\) 反而越大. 而vt代表的是当前状态s下采取动作a所能得到的奖励，这是当前的奖励和未来奖励的贴现值的求和。也就是说，我们的策略梯度算法必须要完成一个完整的eposide才可以进行参数更新，而不是像值方法那样，每一个\(s,a,r,s'\)都可以进行参数更新。如果在prob很小的情况下, 得到了一个大的Reward, 也就是大的vt, 那么-log\(prob\)\*vt就更大, 表示更吃惊, \(我选了一个不常选的动作, 却发现原来它能得到了一个好的 reward, 那我就得对我这次的参数进行一个大幅修改\)。

这就是 -log\(prob\)\*vt的物理意义啦.Policy Gradient的核心思想是更新参数时有两个考虑：如果这个回合选择某一动作，下一回合选择该动作的概率大一些，然后再看奖惩值，如果奖惩是正的，那么会放大这个动作的概率，如果奖惩是负的，就会减小该动作的概率。

1. 算法输出的是动作的概率，而不是Q值。
2. 损失函数的形式为：loss= -log\(prob\)\*vt
3. 需要一次完整的episode才可以进行参数的更新

### ➡ Log likelihood or likelihood

> [https://math.stackexchange.com/questions/892832/why-we-consider-log-likelihood-instead-of-likelihood-in-gaussian-distribution](https://math.stackexchange.com/questions/892832/why-we-consider-log-likelihood-instead-of-likelihood-in-gaussian-distribution)

1. It is extremely useful for example when you want to calculate the _joint likelihood_ for a set of independent and identically distributed points. Assuming that you have your points:X={x1,x2,…,xN}X={x1,x2,…,xN}The total likelihood is the product of the likelihood for each point, i.e.:p\(X∣Θ\)=∏i=1Np\(xi∣Θ\)p\(X∣Θ\)=∏i=1Np\(xi∣Θ\)where ΘΘ are the model parameters: vector of means μμ and covariance matrix ΣΣ. If you use the log-likelihood you will end up with sum instead of product:lnp\(X∣Θ\)=∑i=1Nlnp\(xi∣Θ\)ln⁡p\(X∣Θ\)=∑i=1Nln⁡p\(xi∣Θ\)
2. Also in the case of Gaussian, it allows you to avoid computation of the exponential:

   p\(x∣Θ\)=1\(2π‾‾‾√\)ddetΣ‾‾‾‾‾√e−12\(x−μ\)TΣ−1\(x−μ\)p\(x∣Θ\)=1\(2π\)ddetΣe−12\(x−μ\)TΣ−1\(x−μ\)Which becomes:

   lnp\(x∣Θ\)=−d2ln\(2π\)−12ln\(detΣ\)−12\(x−μ\)TΣ−1\(x−μ\)ln⁡p\(x∣Θ\)=−d2ln⁡\(2π\)−12ln⁡\(detΣ\)−12\(x−μ\)TΣ−1\(x−μ\)

3. Like you mentioned lnxln⁡x is a monotonically increasing function, thus log-likelihoods have the same relations of order as the likelihoods:

   p\(x∣Θ1\)&gt;p\(x∣Θ2\)⇔lnp\(x∣Θ1\)&gt;lnp\(x∣Θ2\)p\(x∣Θ1\)&gt;p\(x∣Θ2\)⇔ln⁡p\(x∣Θ1\)&gt;ln⁡p\(x∣Θ2\)

4. From a standpoint of computational complexity, you can imagine that first of all summing is less expensive than multiplication \(although nowadays these are almost equal\). But what is even more important, likelihoods would become very small and you will run out of your floating point precision very quickly, yielding an underflow. That's why it is way more convenient to use the logarithm of the likelihood. Simply try to calculate the likelihood by hand, using pocket calculator - almost impossible.

   Additionally in the classification framework you can simplify calculations even further. The relations of order will remain valid if you drop the division by 22 and the dln\(2π\)dln⁡\(2π\) term. You can do that because these are class independent. Also, as one might notice if variance of both classes is the same \(Σ1=Σ2Σ1=Σ2\), then you can also remove the ln\(detΣ\)ln⁡\(detΣ\) term.

