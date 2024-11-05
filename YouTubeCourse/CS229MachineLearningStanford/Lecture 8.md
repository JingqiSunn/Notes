#### Lecture 8 

#### Data Splits, Models and Cross-Validation

##### Bias and Variance

Suppose we have a set of data, and we can choose several different form of formula to approach it.

1. $$
   Q_0+Q_1X
   $$

2. $$
   Q_0+Q_1X+Q_2X^2
   $$

3. $$
   Q_0+Q_1X+Q_2X^2+Q_3X^3+Q_4X^4+Q_5X^5
   $$

And they will show different kinds of performance in the bias and variance.

So maybe there will be three kinds of result:

1. Underfit, High Bias
2. Just Right
3. Overfit, High Variance

This may not only happen in the fitting problem, but also take place in the classification problem.

So suppose we have two features, and I use a higher dimensional feature vector to represent it as follows:
$$
\phi(X)=\begin{bmatrix}X_1\\X_2\\X_1^2\\X_2^2\\X_1X_2\\X_1^3X_2\\...\end{bmatrix}
$$
And this may lead to overfitting for some noisy data points.

So here what you can do is to add a term of regularization:
$$
\min_\Theta\frac{1}{2}\sum_{i=1}^m||Y^{(i)}-\Theta^TX^{(i)}||^2+\frac{\lambda}{2}||\Theta||^2
$$
And this kind of strategy have some result in less complexity in the parameter $\Theta$, and the parameter $\lambda$ can control how well the result is fitting. 

Or if you want to use the logistic regression, and you may use the maximum likelihood estimation.

So after adding the regularization term:
$$
\arg\max(\sum_{i=1}^n\log P(Y^{(i)}\Big|X^{(i)};\Theta)-\lambda||\Theta||^2)
$$

> [!TIP]
>
> You can normalize the data before you set up a model.

###### How to Find the Regularization

$$
S=\{X^{(i)},Y^{(i)}\}
$$

$$
P(\Theta\Big| S)=\frac{P(S\Big|\Theta)P(\Theta)}{P(S)}
$$

$$
\arg(\max_\Theta(P(\Theta\Big|\Theta)))=\arg(\max_\Theta( P(S\Big|\Theta)P(\Theta)))=\arg(\max_\Theta((\prod_{i=1}^mP(Y^{(i)}\Big|X^{(i)};\Theta))P(\Theta)))
$$

If you set the distribution of $\Theta$ to be the natural distribution.

###### How to Find the Just Right Balance

1. Split your data set into training, development and test sets.
2. Train each model(option for the degree of polynomial) on $S_{train}$, get some hypothesis.
3. Measure error on $S_{development}$, pick model with lowest error on $S_{development}$.
4. If you want to have a paper, then do a separate test on a test set