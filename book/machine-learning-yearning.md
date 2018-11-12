---
description: 'Technical strategy for AI engineers, in the era of DL'
---

# Machine Learning Yearning

> Andrew Ng

#### 1 Why Machine learning strategy

> tragically: in a way that involves or causes extreme distress or sorrow.

This book will tell you how. Most machine learning problems leave clues that tell you what’s  
useful to try, and what’s not useful to try. Learning to read those clues will save you months  
or years of development time

#### 2 How to use this book to help your team

#### 3 Prerequisites and notation

Supervised learning algorithms include linear regression, logistic regression, and neural networks. The majority of ML's practical value today comes from supervised learning.

#### 4 Scale drives ML progress

Data availability and computational scale.

Plateaus :  an area of fairly level high ground. This means its learning curve flattens out.

Many other details such as neural network architecture are also important, and there has been much innovation here. But one of the more reliable ways to improve an algorithm's performance today is still to 1 train a bigger network and 2 get more data.

#### 5 Your development and test sets

Positive examples, negative examples, training and test sets.  
**Training set** - which you run your learning algorithm on.  
**Development set** - which you use to tune parameters, select features, and make other decisions regarding the learning algorithm. sometimes also called the hold-out cross validation set.   
**Test set** - which you use to evaluate the performance of the algorithm, but not to make any decisions regarding what learning algorithm or parameters to use.

The purpose of the dev and test sets are to direct your team toward the most important changes to make to the machine learning system.

Choose dev and test sets to reflect data you expect to get in the future and want to do well on.

> √  Here I have an idea which is applying GAN to generates more training set if source of picture limited.

#### 6 your dev and test sets should come from the same distribution

> prioritize:  designate or treat \(something\) as being very or most important.













