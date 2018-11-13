---
description: easy to copy
---

# formulas collection

> summary the formulas in your paper.

environments $$ \mathcal{E} $$ ; state space $$\mathcal{S}$$ ​;  action $$a_t \in \mathcal {A}(s_t) $$ ​;  policy $$\pi({a}_{t}|{s}_{t})$$ ​;  policy $${ \pi }^{ \ast }$$ ​;  discount factor $$\gamma \in (0,1]$$ ​;

Markov property  $$p({ s }_{ t+1 }|{ s }_{ 1 },{ a }_{ 1 },...,{ s }_{ t },{ a }_{ t }) = p({ s }_{ t+1 }|{ s }_{ t },{ a }_{ t })$$ ​;  Markov Decision Processes \(MDPs\) $$(\mathcal{S},\mathcal{A},\mathcal{P},\mathcal{R},\gamma)$$

discounted return : ​$$ { R }_{ t }=\sum _{ k=0 }^{ \infty  }{ { \gamma  }^{ k }{ r }_{ t+k } } ​$$  ;    
expected discounted return $${ R }_{ t }=\sum_{ k=0 }^{ \infty }{ { \gamma }^{ k }{ r }_{ t+k } } $$  
  
state-value function: ​  
 $$ { V }^{ \pi }(s)=\mathbb{ E }[R|s,\pi ]=\mathbb{E}[\sum _{ k=0 }^{ \infty  }{ { \gamma  }^{ k }{ r }_{ t+k } }|s,\pi] $$  
optimal state-value function:   
$${ V }^{ \ast }(s)=\max _{ \pi }{ { V }^{ \pi }(s) } \quad \forall s\in \mathcal{ S }$$  
  
state-action-value :   
​$${ Q }^{ \pi  }(s,a)=\mathbb{ E }[R|s,a,\pi ]= \mathbb{E}[\sum _{ k=0 }^{ \infty  }{ { \gamma  }^{ k }{ r }_{ t+k } }|s,a,\pi]$$  
optimal state action value :  
$${ Q }^{ \ast }(s,a)=\max _{ \pi }{ { Q }^{ \pi }(s,a) } \quad \forall s\in \mathcal{ S } , \forall a\in \mathcal{ A }$$  
dynamic programming :  
 ​$${Q}^{\pi}(s,a)=\mathbb{E}_{{s}^{\prime}}[r+\gamma\mathbb{E}_{{a}^{\prime}\sim{\pi}({s}^{\prime})}[{Q}^{\ast}({s}^{\prime},{a}^{\prime})]|s,a,\pi]$$  
  
Advantage function:  
 ​$${ A }^{ \pi }(s,a)={ Q }^{ \pi }(s,a)-{ V }^{ \pi }(s)$$ ​

Loss Function:  
 $${L}_{i}({\theta}_{i})=\mathbb{E}_{s,a,r,{s}^{\prime}}[{({y}_{i}^{DQN}-Q(s,a;{\theta}_{i}))^{2}]}$$  
with $${y}_{i}^{DQN}=r+\gamma \underset {{a}^{\prime}}{max}Q({s}^{\prime},{a}^{\prime};{\theta}^{-}) $$

Policy gradient:  
 $$             {\nabla}_{\theta}J({\pi}_{\theta})=\int _{\mathcal{S}}^{  }{{\rho}^{\pi} }\int_{\mathcal{A}}^{  }{{\nabla}_{\theta}}{\pi}_{\theta}(a|s){Q}^{ \pi}(s,a)dads \\               \quad\quad\quad\quad=\mathbb{E}_{s\sim{\rho}^{\pi},a\sim {\pi}^{\theta}}[{\nabla}_{\theta} log{\pi}^{\theta}(a|s){Q}^{\pi}(s,a)]$$

Dueling:   
 $$Q(s,a;\theta^{Q},\alpha,\beta ) =V(s;\theta^{Q},\beta)+ A(s,a; \theta^{Q}, \alpha )$$     
$$Q(s,a;\theta^{Q},\alpha,\beta)=V(s;\theta^{Q},\beta)+ (A(s,a;\theta^{Q},\alpha)-\max_{a^{\prime} \in| \mathcal{A}|}{A(s,a^{\prime};\theta^{Q},\alpha)})$$  
$$Q(s,a;\theta^{Q},\alpha,\beta)=V(s;\theta^{Q},\beta)+ (A(s,a;\theta^{Q},\alpha)-\frac{1}{|\mathcal{A}|} \sum_{a^{\prime}} {A(s,a^{\prime};\theta^{Q},\alpha)})$$

$$\epsilon$$-greedy :  
 $$\mu^{\prime}(s) = \mu(s|\theta^{\mu})+\mathcal{N}$$

