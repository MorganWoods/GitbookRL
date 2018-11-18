# ML

## Logistic regression

It is a classification model easy to implement but performs very well on linearly separable classes. For binary classification and it can be extended to multiclass classification via OvR technique.

odds ratio = p/\(1-p\) , p stands for the probability of the positive event.

logit function: logit=log{odds ratio} 

The logit function takes input values in the range 0 to 1 and transforms them to values over the entire real number range, which we can use to express a linear relationship between feature values and the log-odds

## Variables

#### Categorical Variable

Variables can be classified as **categorical** \(aka, qualitative\) or **quantitative** \(aka, numerical\).

* Categorical. Categorical variables take on values that are names or labels. The color of a ball \(e.g., red, green, blue\) or the breed of a dog \(e.g., collie, shepherd, terrier\) would be examples of categorical variables. 
* Quantitative. Quantitative variables are numerical. They represent a measurable quantity. For example, when we speak of the population of a city, we are talking about the number of people in the city - a measurable attribute of the city. Therefore, population would be a quantitative variable.

#### Encode

In [digital circuits](https://en.wikipedia.org/wiki/Digital_circuits), **one-hot** is a group of bits among which the legal combinations of values are only those with a single high \(1\) bit and all the others low \(0\).[\[1\]](https://en.wikipedia.org/wiki/One-hot#cite_note-1) A similar implementation in which all bits are '1' except one '0' is sometimes called **one-cold**.

