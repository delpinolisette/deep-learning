# Deep Learning
notes and work on deep learning. 

The aim of these is to synthesize theory from several different "classical" sources and introduce insights from newer literature. 

See `statistical_theory_background.md` in repo for some of the needed math background. 


- [Measures](#measures)
  - [$L_p$ Distances](#l_p-distances)
  - [$L_p$ distances are metrics](#l_p-distances-are-metrics)
  - [Distance Example 01](#distance-example-01)
  - [Distance Example 02](#distance-example-02)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Gradient Descent](#gradient-descent)
- [First Equation for a Straightforward Neural Net](#first-equation-for-a-straightforward-neural-net)


# Measures 

Measures that we use to measure distances (ex: between images in nearest neighbors) include $L_p$ distances. 

From real analysis, we know a metric is a *bivariate* operator $d: X \times Y \mapsto \mathbb{R}^n$ that is nonnegative, has identity, symmetry, and obeys the triangle inequality. AKA

1. $d(a,b) \geq 0$
2. $d(a,b) = 0 \iff a = b$
3. $d(a,b) = a(b,a)$
4. $d(a,b) \leq d(a,c) + d(b,c)$

We call $d$ *pseudometric* if it is nonnegative, has symmetry, and obeys the triangle inequality. 

We call $d$ *quasimetric* if it obeys all conditions except symmetry. 


## $L_p$ Distances 

Then distances we often use in vector math are $L_p$ distances. 

$$
L_p 
\\ = d(a,b)_p
\\ = \lVert a-b \rVert_p 
\\ = (\sum_{i=1}^{n}{(a_i - b_i)})^{1/p}
$$

## $L_p$ distances are metrics

You can prove that $L_p$ distances are valid metrics, like this: 

Notice that for any $p \in \mathbb{N}$ that you replace in the formula for $L_p$, we have nonnegativity, identity, symmetry, and triangle inequality. 

## Distance Example 01 

If we have two images and we want to perform a nearest neighbors classification on them, we use the $L_1$ distance, treating the images as matrices and pixels as entires. Then 

$L_1$

$d(a,b)_{1}$

$\lVert a - b \rVert$

$$L_1 d(a,b)_{1} =  \sum_{i=1}^{n}{a_i - b_i}$$

$$
L_{1} = d(a,b)_{1} = \lVert a - b \rVert = \sum_{i=1}^{n}{a_i - b_i}
$$ 

where 

$a_i \in a, b_i \in b$

are pixel values of image 1 and image 2, respectively. 

## Distance Example 02 

The Euclidian distance is $L_2$, or the **vector norm** linear algebra.

# Hyperparameter Tuning

When training something like a k nearest neighbors classifier, we have a choice for what k is. 

Tuning this $k$, as well as tuning the choice for the distance metric $L_p$, is called tuning a hyperparameter. 

Usually, selecting the best parameter is a matter of trial and error. You try training the classifier on several hyperparameter combinations before deciding which configuration is best. 

## Function Gradients 

Recall from multivariable calc that the gradient of a multivariate function $f$ is the vector $\nabla f(a)$ whose compoenents are partial derivaties of $f$ with respect to each variable: 

$$
f(a) = (Df(a_1), Df(a_2), \dots Df(a_n))
$$

# Gradient Descent

Then gradient descent is the method of using the gradient vector to find the local min of a (hopefully) convex loss function. 

So, if we have the MSE(L2 loss) function on $f(m,b)$, where $m$ is the mean, $b$ is the bias, then the gradient is :



$$
f(m,b) = (Df(m), Df(b))
$$

# First Equation for a Straightforward Neural Net 















