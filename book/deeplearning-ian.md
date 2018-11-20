---
description: Ian Goodfellow's book
---

# DeepLearning-Ian

## 1 introduction

**Knowledge base** approaches experienced failure, they sought to hard-code knowledge about the world in formal languages.

AI system need the ability to acquire their own knowledge by extracting patterns from raw data, instead of relying on hard-coded knowledge. This capability is known as **machine learning**. Some simple ML algorithm: Logistic regression, Naive Bayes. They rely on the **representation** of the data. Pieces of information in the representation is known as **features**. 

Using ML to discover not only the mapping rom representation to output but also the representation itself. It is known as **representation learning**. An algorithm is **autoencoder**, which is the combination of an **encoder** function and **decoder** function.

The quintessential example of a deep learning model is the **feedforward deep network** or **multilayer perceptron \(MLP\)**. Depth allows the computer to learn a multi-step computer program. In a model, the input is known as **visible layer**, since in contains the variables that we are able to observe. A series of **hidden layers** extracts increasingly abstract features from image, 'hidden' refers to their values are not given in the data.

## Part 1: Applied Math and Machine Learning Basics

### 2 Linear algebra

#### 2.4 linear dependence and span

linear dependence; A square matrix with linearly dependent columns is known as **singular**.

In ML, we usually measure the size of vectors using a function called a **norm**. It covers Euclidean norm, max norm, Frobenius norm.

triangle inequality.

2.6

Diagonal matrices \(对称\); A **unit vector** is a vector with **unit norm**; **Orthogonal matrix**; **Eigendecomposition 特征 ,** eigenvector,  left eigenvector; **Singular Value Decomposition** factorize a matrix into **singular vectors** and **singular values**. 

### 3 Probability and Information Theory

We use probability theory in two major ways. First, the laws of probability tell us how AI systems should reason, so we design our algorithms to compute or approximate various expressions derived using probability theory. Second, we can use probability and statistics to theoretically analyze the behaviour of proposed AI systems.

**probability distribution**, **joint probability distribution**, **uniform distribution**, probability density function, marginal probability, 

The most commonly used distribution over real numbers is the normal distribu-tion, also known as the **Gaussian distribution**.

#### 3.10 Useful properties of common functions

**Logistic sigmoid**: $$\sigma(x)=\frac{1}{1+exp(-x)}$$ , also known as **sigmoid function**, it commonly used to produce the parameter of a Bernoulli distribution.  
The sigmoid function **saturates** when its argument is very positive or very negative, the function becomes very flat and insensitive to small changes in its input.

**Softplus function**: $$\varsigma(x)=log(1+exp(x))$$ 

![](../.gitbook/assets/image%20%283%29.png)

#### 3.13 Information Theory

**Shannon entropy**: $$H(x)=E_{ x\sim P }[I(x)]=-E_{ x\sim P }[logP(x)]$$   
When x is continuous, the H\(p\) is known as the **differential entropy.**

If we have two separate probability distributions P\(x\) and Q\(x\) over the same random variable x, we can measure how different these two distributions are using the **Kullback-Leibler \(KL\) divergence.**  
 $$D_{ KL }(P\parallel Q)=E_{ x\sim P }[log\cfrac { P(x) }{ Q(x) } ]=E_{ x\sim P }[logP(x)-logQ(x)]$$   
The KL divergence has many useful properties, it is non-negative. It is 0 if two are same distribution in the case of discrete variables.

**cross-entropy**: $$H(P,Q)=H(P)+D_{ KL }(P\parallel Q)=-E_{ x\sim P }logQ(x)$$ 

#### 3.14 Structured Probabilistic Model

A **graphical model** or probabilistic **graphical model** \(PGM\) or structured probabilistic **model** is a probabilistic **model** for which a **graph** expresses the conditional dependence structure between random variables. They are commonly used in probability theory, statistics—particularly Bayesian statistics—and machine learning. Node and Edge.

Two main kinds of graphical model: **directed** and **undirected**.  
Directed model uses graphs with directed edges, they represent factorizations into conditional probability distributions.

We will use graph models merely as a language to describe which direct probabilistic relationships different machine learning algorithms choose to represent.

### 4 Numerical Computation

#### 4.1 Overflow and underflow

rounding error; denominator 分母, numerator 分子; 

4.2 

Conditioning refers to how rapidly a function changes w.r.t small changes in its inputs. 

#### 4.3 Gradient based optimization

**Objective function** or **criterion, cost function, loss function, error function**.

**Critical points or stationary points** is the points with 0 derivate value. 

saddle point, global minimum, local maximum. second derivative, curvature 曲率.

Optimization algorithms that use only the gradient such as gradient descent, are called **first-order optimization algorithms**. That using Hessian matrix such as Newton's method, are called **second-order optimization algorithms**. 

In the context of DL, we sometimes gain some guarantees by restricting ourselves to functions that are either Lipschitz continuous or have Lipschitz continuous derivatives. **Lipschitiz continuous** function is function whose rate of change is bounded by a Lipschitz constant.

The most successful field of specialized optimization is **convex optimization**. Convex optimization algorithms are able to provide many more guarantees by making stronger restrictions. They are only applicable to **convex functions** - functions for which the Hessian is **positive semidefinite** everywhere. However, most problems in DL are difficult to express in terms of convex optimization. It is used only as a subroutine of some deep learning algorithms.

#### 4.4 Constrained Optimization

Maximal or minimal value of function for x in some set, this is contrained optimization.

#### 4.5 Linear Least Squares

### 5 Machine Learning Basics

In **regression** tasks, program predicts numerical value given some input.

**Transcription** tasks, Observing a relatively unstructured representation of some kind of data and transcribe it into discrete, textual form.

**Structured output** tasks,  Anomaly detection, Synthesis and sampling, Imputation of missing values. Denoising, Density estimation or probability mass function estimation.

**Mean squared error**, Normal equations 正规方程.

The ability to perform well on previously unobserved inputs is called **generalization**. Training error, generalization error, test error. 

## Part 2: Deep Networks: Modern Practices





## Part 3: Deep learning research



























##     --------------------

