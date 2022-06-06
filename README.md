# Deep Learning
notes and work on deep learning. 

The aim of these is to synthesize theory from several different "classical" sources and introduce insights from newer literature. 

See `statistical_theory_background.md` in repo for some of the needed math background. 



- [Measures](#measures)
  - [Distances](#distances)
  - [Distance Example 01](#distance-example-01)
  - [Distance Example 02](#distance-example-02)
- [Optimization of Classifiers and Choice of Distance](#optimization-of-classifiers-and-choice-of-distance)
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

## Distances 

Then distances we often use in vector math are $L_p$ distances. 

$$
L_p 
\\ = d(a,b)_p
\\ = ||a-b||_p 
\\ = (\sum_{i=1}^{n}{(a_i - b_i)})^{1/p}
$$

## Distance Example 01 

If we have two images and we want to perform a nearest neighbors classification on them, we use the $L_1$ distance, treating the images as matrices and pixels as entires. Then 

$L_1 = d(a,b)_1 = ||a - b|| = \sum_{i=1}^{n}{a_i - b_i}$ 

where 

$a_i \in a, b_i \in b$


are pixel values of image 1 and image 2, respectively. 

## Distance Example 02 

The Euclidian distance is $L_2$, or the **vector norm** linear algebra.

# Optimization of Classifiers and Hyperparameter Tuning

When training something like a k nearest neighbors classifier, we have a choice for what k is. 

Tuning this $k$, as well as tuning the choice for the distance metric $L_p$, is called tuning a hyperparameter. 

Usually, selecting the best parameter is a matter of trial and error. You try training the classifier on several hyperparameter combinations before deciding which configuration is best. 

# First Equation for a Straightforward Neural Net 












