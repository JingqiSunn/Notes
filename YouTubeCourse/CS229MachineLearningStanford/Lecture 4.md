#### Lecture 4

#### Perceptron and Generalized Linear Model

##### Logistic Regression 

###### Unique Function

$$
g(z)=\frac{1}{1+e^{-z}}
$$

###### Hypothetical Function 

$$
h_\Theta(X^{(i)})=g(\Theta^TX^{(i)})
$$

###### Updating Function 

$$
\Theta_j=\Theta_j+\alpha(Y^{(i)}-h_\Theta(X^{(i)}))X^{(i)}_j
$$

##### Perception Regression

###### Unique Function 

$$
g(z)=\begin{cases}1\quad z\geq0\\0\quad z< 0\end{cases}
$$

###### Hypothetical Function

$$
h_\Theta(X^{(i)})=g(\Theta^TX^{(i)})
$$

###### Updating Function

$$
\Theta_j=\Theta_j+\alpha(Y^{(i)}-h_\Theta(X^{(i)}))X^{(i)}_j
$$

> [!NOTE]
>
> The detailed derivation will not be offered, and you can understand the updating function as a movement of rotation.

##### Exponential Family

###### Probability Density Function 

$$
P(y;\eta)=b(y)\exp(\eta^TT(y)-a(\eta))
$$

$$
y \text{ here is the data}
$$

$$
\eta \text{ is the natural parameter}
$$

$$
T(y)\text{ is the sufficient statistic, in the course the value of it will always be }y
$$

$$
b(y) \text{ is the base measure}
$$

$$
a(\eta)\text{ is the log partition funciton}
$$

> **Bernoulli Distribution** 
>
> *Probability Density Function*
> $$
> P(y;\phi)=\phi^y(1-\phi)^{(1-y)}
> $$
> Where $\phi$ is the probability of the event.
>
> *Transform It into the Form of Exponential Family*
> $$
> \begin{aligned}
> P(y;\phi)
> &=\phi^y(1-\phi)^{(1-y)}\\
> &=\exp(\log(\phi^y(1-\phi)^{(1-y)}))\\
> &=\exp(\log((\frac{\phi}{1-\phi})^y\cdot(1-\phi))\\
> &=\exp(y\log(\frac{\phi}{1-\phi})+\log{(1-\phi)})\\
> \end{aligned}
> $$
> So that we can see that for the Bernoulli Distribution, we have that
> $$
> P(y;\phi)=\exp(y\log(\frac{\phi}{1-\phi})+\log{(1-\phi)})=b(y)\exp(\eta^TT(y)-a(\eta))
> $$
>  Where
> $$
> b(y)=1
> $$
>
> $$
> \eta =\log(\frac{\phi}{1-\phi});\phi = \frac{1}{1+e^{-\eta}}
> $$
>
> $$
> T(y)=y
> $$
>
> $$
> a(\eta)=-\log(1-\phi)=-\log(1-\frac{1}{1+e^{-\eta}})=\log(1+e^\eta)
> $$

> **Gaussian Distribution(with fixed variance)**
>
> > [!NOTE]
> >
> > Assume that $\sigma^2 = 1$
>
> *Probability Density Function*
> $$
> P(y;\mu) = \frac{1}{\sqrt{2\pi}}\exp(-\frac{(y-\mu)^2}{2})
> $$
> *Transform It into the Form of Exponential Family*
> $$
> \begin{aligned}
> P(y;\mu)
> &=\frac{1}{\sqrt{2\pi}}\exp(-\frac{(y-\mu)^2}{2})\\
> &=\frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}\exp(\mu y-\frac{1}{2}\mu^2)
> \end{aligned}
> $$
> So that we can see that for the Gaussian Distribution, we have that
> $$
> P(y;\mu)
> =\frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}\exp(\mu y-\frac{1}{2}\mu^2)=b(y)\exp(\eta^TT(y)-a(\eta))
> $$
> Where
> $$
> b(y)=\frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}
> $$
>
> $$
> \eta = \mu
> $$
>
> $$
> T(y)=y
> $$
>
> $$
> a(\eta)=\frac{1}{2}\mu^2=\frac{1}{2}\eta^2
> $$

###### Property

- If we apply the maximum likelihood problem on the exponential family, we can see it is concave.
- Negative Log Likelihood is convex.
- $E(y;\eta) = \frac{\partial}{\partial \eta}a(\eta)$
- $Var(y;\eta)=\frac{\partial^2}{\partial \eta^2}a(\eta)$

##### Generalized Linear Model

> [!NOTE]
>
> We can choose some good classes from the exponential family to build some good linear regression.

| Data Type |    Distribution    |
| :-------: | :----------------: |
|   Real    |      Gaussian      |
|  Binary   |     Bernoulli      |
|   Count   |      Poisson       |
|  $R^{+}$  | Gamma, Exponential |

###### Design Choice

1. $y\Big|x;\Theta\sim$ Exponential Family
2. $\eta=\Theta^TX,\Theta\in R^n,X\in R^n$
3. Test Time: Output $h_\Theta (X)=E(y\Big|x;\Theta)$

###### Design Step

1. Get the input $X$
2. Transformation $\eta = \Theta^T X$
3. Find the suitable distribution in the exponential family
   - In the Using $h_\Theta(X)=E(y\Big|x;\eta)$
   - In Training, ​maximizing $\log(\prod _{i=1}^{m}P(Y^{(i)};\Theta^TX^{(i)}))$

###### Detail During Train Time

> [!NOTE]
>
> Because of the property of the exponential family, the learning rule for the generalized linear models are the same.
> $$
> \Theta _j=\Theta_j+\alpha(Y^{(i)}-h_\Theta(X^{(i)}))X^{(i)}_j
> $$

###### Terminology

1. $\eta$ is the natural parameter
2. $\mu=E(y;\eta)=g(\eta)=\frac{\partial}{\partial\eta}a(\eta)$ is the Canonical Response Function
3. $\eta =g^{-1}(\mu)$ is the Canonical Link Function

###### Three Parameters

- Model Parameter(The one we are trying to learn)
  $$
  \Theta
  $$

- Natural Parameter
  $$
  \eta
  $$

- Canonical Parameter
  $$
  \phi\text{ for Bernoulli Distribution }
  $$

  $$
  \mu\sigma^2\text{ for Gaussian Distribution}
  $$

  $$
  \lambda\text{ for Poisson Distribution}
  $$

##### Softmax Regression

###### Syntax Background

- $k$ is the number of the classes
- $X^{(i)}\in \R^{(n+1)}$
- $n$ is the number of the features
- Label $y=[\{0,1\}^k]$​
- $\Theta\in\R^{k\times (n+1)}=\begin{bmatrix}---\Theta_{1}---\\---\Theta_{2}---\\...\\---\Theta_{k}---\\\end{bmatrix}$

> [!NOTE]
>
> In this kind of strategy you will have a set of parameter $\Theta$​ for each class.
>
> And you can think it as a super combination class of perceptron regression.

###### Step

1. Use the $\Theta$ and $X$ to find all the $\Theta^TX$ for each class.
2. Find the $\exp(\Theta^TX)$, because they will all be positive.
3. Normalize everything, $\frac{e^{\Theta^TX}}{\sum e^{\Theta^TX}}$ and it will give a probability distribution in the bar chart.

> [!NOTE]
>
> But we can notice that the difference between some classes may not be such obvious, so that we need to decrease the cross entropy between the classes.
> $$
> \begin{aligned}
> CrossEntropy(P,\hat{P})
> &=-\sum_{y\in\text{all classes}}P(y)\log\hat{P}(y)\\
> &=-\log\hat{P}(y_0)\\
> &=-\log\frac{e^{\Theta^TX}}{\sum e^{\Theta^TX}}
> \end{aligned}
> $$

