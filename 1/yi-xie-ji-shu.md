---
description: Techniques
---

# technique

### Reward Shaping

> contrived ,不自然的,勉强的.  absorbing state :吸收态; static 静态, dynamic 动态;  
> corollary 推论,必然的结果;

* Sam Devlin 的 ppt

  * provide heuristic 启发式的 knowledge by an additional reward: ​$$ Q(s,a) \leftarrow Q(s,a)+\alpha [r+F(s,s^\prime + \gamma max_{a^\prime}Q_i(s\prime,a\prime)-Q(s,a)]$$ F 是 additional reward 定义为此刻潜能乘衰减-上一刻的潜能. 一个潜能 potential 的例子: ​![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LHYMklgL164Q1SO96F6%2F-LIBkIuESYu7TwWnQN8-%2F-LIBky-foTS6JN2bPU7E%2Fimage.png?alt=media&token=8af0cedf-efa0-4b2c-8c87-c625265eae0f) 
  * 有了这个 reward shaping 技术 ,训练肯定更快,相当于提前知道了环境的信息. 但最终的性能差不多. Multi-agent potential-based reward shaping: 这种情况下训练速度提高,训练性能也提高.
  * ❓这和 model base 的环境有啥区别

* Andrew NG 的 ppt  


  * reward shaping: to provide guidance, policies can be learned on an MDP with a modified reward function, and then used on the original MDP with varying results
  * potential-based reward shaping: to ensure that good policies for a modified reward function are also good for the original, it suffices to base the rewards on a potential function.
  * Experiments: some potential-based shaping functions are evaluated.
  * If F is a potential-based shaping function, then every optimal policy in M'= S, A, T, γ, R + F will also be an optimal policy in M = S, A, T, γ, R \(and vice versa\)
  * If F is a potential-based shaping function, then every optimal policy in M' = S, A, T, γ, R + F will also be an optimal policy in M = S, A, T, γ, R \(and vice versa\). So
  * conclusion: We’ve seen that :  Reward shaping can change what the optimal policy is.   But, using potential-based shaping functions guarantees that the optimal policy will not be changed.  The idea of potential functions can help us find useful shaping functions in practice. 

  



experience repaly 

soft target update 

generalized Advantage estimate 

NAF 

Double Q learning 

attention 机制 

reward 方程参数化\(可以考虑对 reward 下手\)

