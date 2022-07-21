# Deep Learning
notes and work on deep learning. 

The aim of these is to synthesize theory from several different "classical" sources and introduce insights from newer literature. 

See `statistical_theory_background.md` in this repo [here](https://github.com/delpinolisette/deep-learning/blob/main/statistical_theory_background.md) for some of the needed math background. 



- [Measures](#measures)
  - [$L_p$ Distances](#l_p-distances)
  - [$L_p$ distances are metrics](#l_p-distances-are-metrics)
  - [Distance Example 01](#distance-example-01)
  - [Distance Example 02](#distance-example-02)
- [Hyperparameter Tuning](#hyperparameter-tuning)
  - [Function Gradients](#function-gradients)
- [Gradient Descent](#gradient-descent)


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
L_p = \lVert a-b \rVert_p = (\sum_{i=1}^{n}{(a_i - b_i)})^{1/p}
$$

## $L_p$ distances are metrics

You can prove that $L_p$ distances are valid metrics, like this: 

Notice that for any $p \in \mathbb{N}$ that you replace in the formula for $L_p$, we have nonnegativity, identity, symmetry, and triangle inequality. 

So, $L_p := d(a,b)_p$

## Distance Example 01 

If we have two images and we want to perform a nearest neighbors classification on them, we use the $L_1$ distance, treating the images as matrices and pixels as entires. Then 

$L_1 = d(a,b)_{1}$, so 

$$L_1 = \lVert a - b \rVert_1 =  \sum_{i=1}^{n}{a_i - b_i}$$


where $a_i \in a, b_i \in b$ are pixel values of image 1 and image 2, respectively. 

## Distance Example 02 

The Euclidian distance is $L_2$, or the **vector norm** linear algebra.

# Hyperparameter Tuning

When training something like a k nearest neighbors classifier, we have a choice for what k is. 

Tuning this $k$, as well as tuning the choice for the distance metric $L_p$, is called tuning a hyperparameter. 

Usually, selecting the best parameter is a matter of trial and error. You try training the classifier on several hyperparameter combinations before deciding which configuration is best. 

## Function Gradients 

Recall from multivariable calculus that the gradient of a multivariate function $f$ is the vector $\nabla f(a)$ whose compoenents are partial derivaties of $f$ with respect to each variable: 

$$
\nabla f(a) = (Df(a_1), Df(a_2), \dots Df(a_n))
$$

## Vector-Valued Function Gradients 

We can also define the gradient on vector-valued functions in an alternative way (this one was popular in problem sets for my real analysis class) which relates it to the derivative

Say $f$ maps a column vector $a = (a_1, \dots a_n)^{\intercal}$ from $\mathbb{R}^n$ to $\mathbb{R}$. 

Then the gradient $\nabla f$ must satisfy:

$$
f(a + \epsilon h) = f(a) + \epsilon(\nabla f(a))^{\intercal} h + O(\epsilon^2)
$$

Where $\epsilon h$ is some random perturbation.

# Gradient Descent

Then gradient descent is the method of using the gradient vector to find the local min of a (hopefully) convex loss function. 

So, if we have the MSE($L_2$ loss) function $$f(m,b) = \frac{1}{n}\sum_{i = n}^{n}{(y_i - \hat{y_i})^2} =\\ $$ 

where $m$ is the mean, $b$ is the bias, then the gradient is

$$
f(m,b) = (Df(m), Df(b)) 
\\ = \begin{bmatrix}
  Df(m) \\
  Df(b)
\end{bmatrix} 
\\ = \begin{bmatrix}
\sum_{i = 1}^{n} 2(y_i -  \hat{y_i}) \frac{\partial{f}}{\partial{m}}\hat{y_i} \\
\sum_{i = 1}^{n} 2(y_i -  \hat{y_i}) \frac{\partial{f}}{\partial{b}}\hat{y_i}
\end{bmatrix}
$$

Gradient Descent then minimizes this function step by step (where the step size is determined by the learning rate)



issue : that thing doesnt render properly on readme - ton of bugs. need to make a pdf copy of these. 














