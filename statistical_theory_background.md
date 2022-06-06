Necessary Statistic Theory background. This is a compilation of some of my notes on the theory, and is still a work in progress. 

## Why "Regression"

Stigler 1986 

Children of tall parents tended to be not quite as tall 
Likewise, the children of unusually short parents also tend to be closer to the average, and similarly
for other traits. This came to be called “regression towards the mean,” or even “regression towards
mediocrity”; hence the line relating the average height (or whatever) of children to that of their
parents was “the regression line,” and the word stuck.

## Origins of Mathematical Expectation $\mathbb{E}$

Originated from middle of 17th century from problem of how to divide points equally among players who cannot finish a game

It was decided by Fermat and Pascal simoltaneously that the value of a future gain should be directly proportional to the change of getting it. 

## Mathematical Expectation (Statistics)

the summation or integration of possible values of a random variable

generatlization of a weighted average

## Linearity of Expectation 
Expectaion of sum of RVs == sum of individual expecations, regardless of wether they are independent or dependent. 

Thus, for random variables $X$ and $Y$, which might be dependent, $E[X + Y]$ = $E[X] + E[Y]$

The general case, for variables $X_1, X_2, \dots X_n$ and constants $c_1, \dots ,c_n$, 

$$E[\sum_{i = 1}^{n}c_iX_i] = \sum_{i = 1}^{n}(c_i \cdot  E[X_i])$$

(you can move in the expectation)

## Proof of Linearity of Expectation

Proof for two discrete random variables:

$$
E[X + Y] = \sum_{x}^{}\sum_{y}^{}{(x+y)(P(X = x, Y = y))}
= \sum_{x}^{}{}
$$

## Mathematical Expectation Def - RV with Finitely many outcomes

possible outcomes : $x_1,x_2, \dots x_k$, k finite. 

respective probabilities of happening:
$p_1, \dots p_k$, k finite. 

Then $\mathbb{E}[X] = x_1p_1 + \dots + x_kp_k$

and since all probabilities must statisfy unity ($p_1 + \dots + p_k = 1$) then expectation can be thought of as the *weighted average of the x_j* outcomes with the weights being the $p_j$ probabilities.

Special case: if all outcomes are equiprobable ($p_1 = \dots = p_k$), expectation is the *average*

## Ex 0 : If X is outcome of roll of fair sided die, $E[X]$ is?

insert pic

## Ex 1 : X is gain from a 1 dollar bet in roulette, what is $E[X]$?

insert pic

## Mathematical Expectation Def - RV with countably infinite many outcomes

$E[X] = \sum_{i = 1}^{\infty} x_ip_i$

where $x_1, x_2,\dots$ are the possible outcomes of $X$

and $p_1, p_2, \dots$ are the respective probabilites for the outcomes. 

## Issues with $E[X]$ for countably infinite series

Reimann Series Theorem shows that some infinite sum values depend on summand order, and since outcomes of rv $X$ have no set order, so $E[X]$ is only well defined on **absolutely convergent** infinite sum (then there is a finite sum so summand order cannot change outcome)

OW $X$ is said to not have finite expectation. 


## Expectation of RVs with Density



## Bias (of an estimator)


## What is an *unbiaed estimator*?

When $E{X}$ of the estimator  `==` $E[X]$ of the true parameter. 



## Variance of a random variable

## Define MSE Function 

$$MSE(m) = \mathbb{E}[(Y - m)^2]$$

where $\mathbb{E}$ is defined as 

or 

$$MSE(\hat{Y}) = \frac{1}{n} \sum_{i=1}^{n}(Y - \hat{Y})^2$$


## Decomposition of MSE of an estimator into Bias - Variance:

- This shows that in the case of **unbiased estimators**, the MSE and variance are equivalent. 

- $MSE(\hat{\theta}) = \text{bias}^2(\hat{\theta}) + \text{variance}(\hat{\theta})$

- trick is set $\mu = \mathbb{E}[\theta]$ 
- TODO: is $\mu$ a constant then?

$$ 
\begin{align}
& MSE(\hat{\theta}) \\
=&  \mathbb{E}[(\theta - \hat{\theta})^2] \\
=& \mathbb{E}[((\hat{\theta} - \mu) + (\mu - \theta))^2] \\
=& \mathbb{E}[(\theta - \mu)^2 + 2(\mu - \theta)(\theta - \mu)]
\end{align}
$$


## Derive Optimization for MSE Function 


## Critcisms of MSE 

The use of mean squared error without question has been criticized by the decision theorist James Berger. Mean squared error is the negative of the expected value of one specific utility function, the quadratic utility function, which may not be the appropriate utility function to use under a given set of circumstances. There are, however, some scenarios where mean squared error can serve as a good approximation to a loss function occurring naturally in an application.[10]

Like variance, **mean squared error has the disadvantage of heavily weighting outliers.[11] This is a result of the squaring of each term, which effectively weights large errors more heavily than small ones**. This property, undesirable in many applications, has led researchers to use alternatives such as the mean absolute error, or those based on the median.

## Differences between supervised and unsupervised learning?

Supervised

1. input data is labeled and "known" (example of model?)
2. Has a feedback mechanism (what types)
3. Most common supervised learning:
- decision trees 
- logistic regression
- support vector machine

Unsupervised :
1. input data is unlabeled 
2. no feedback mechanism (is this true?)
3. Common algos are : 
- k means clustering
- hierarchical clustering
- apriori


## Logistic Function 

- S-shaped curve 
- $\frac{1}{1 + e^{input}}$
- takes any real valued number and maps it to $(0,1)$


## How Does Logistic Regression Work?

- classification algorithm
- works when the outcome is binary
    - so the output needs be **discrete** rather than continuous
- works when input data is linearly seperable
- at its core, uses an equation (that you can write down) as the representation, like linear regression
    - but instead spits out an output modeled by 0 or 1

Flow:

0. get your linear equation coffieints to feed into $input$
1. uses S-shaped curve (logistic function) 
$\frac{1}{1 + e^{input}}$
2. 

