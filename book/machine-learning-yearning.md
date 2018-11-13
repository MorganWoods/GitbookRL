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

Working on ML applications is hard enough. Having mismatched dev and test sets introduces additional uncertainty about whether improving on the dev set distribution also improves test set performance. Having mismatched dev and test sets makes it harder to figure out what is and isn't working, and thus makes it harder to prioritize that to work on.

_**It is an important research problem to develop learning algorithms that are trained on one distribution and generalize well to another.** ☆_ But if your goal is to make progress on a specific machine learning application rather than make research progress, I recommend trying to choose dev and test sets that are drawn from the same distribution.

#### 7 How large do the dev/test sets need to be?

> eke:  make an amount or supply of something last longer by using or consuming it frugally.

The dev set should be large enough to detect difference between algorithms that you are trying out.

```text
data/
    train/
        img_000.jpg
        ...
        img_799.jpg
    dev/
        img_800.jpg
        ...
        img_899.jpg
    test/
        img_900.jpg
        ...
        img_999.jpg
```

#### 8 Establish a single-number evaluation metric for your team to optimize.

> metric : a system or standard of measurement.  
> fraction: a numerical quantity that is not a whole number \(e.g. 1/2, 0.5\);.a small or tiny part, amount, or proportion of something.

classification accuracy is an example of a single-number evaluation metric.

In contrast, precision and recall is not a single-number evaluation metric: it gives two numbers for assessing your classifier. This way makes it harder to compare algorithms.

Recall is the percentage of all cat images in the dev \(or test\) set that it correctly labeled as a cat. What proportion of actual positives was identified correctly? R=TP/\(TP+FN\) .   
Precision is the fraction of images in the dev \(or test\) is labeled as cats that are really are cats. What proportion of positive identifications was actually correct?  P = TP/\(TP+FP\)  
There is often a tradeoff between having high precision and high recall.

If you really care about both precision and recall, I recommend using one of the standard ways to combine them into a single number. Alternatively, you can compute the F1 score.

F1 score:  The [F1 Score](http://en.wikipedia.org/wiki/F1_score) is the 2\*\(\(precision\*recall\)/\(precision+recall\)\). It is also called the F Score or the F Measure. Put another way, the F1 score conveys the balance between the precision and the recall. It is a 'harmonic mean'

#### 9 Optimizing and satisficing metrics

> derive:  obtain something from \(a specified source\).

#### 10 having a dev set and metric speeds up iterations

> incorporate : take in or contain \(something\) as part of a whole; include.

#### 11 When to change dev/test sets and metrics



