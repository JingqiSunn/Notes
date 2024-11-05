#### Lecture 6

#### Support Vector Machines

##### Naive Bayes

###### Syntax

$$
X^{(i)}=\begin{bmatrix}X_1^{(i)}\\X_2^{(i)}\\...\\X_n^{(i)}\\\end{bmatrix}
$$

$$
X^{(i)}_j=\iota\{\text{whether $j$ appears in the email $i$}\}
$$

There are three parameters
$$
P(Y^{(i)}=1)=\phi_{Y^{(i)}}
$$

$$
P(X^{(i)}_j = 1\Big| Y^{(i)}=0)=\phi_{j\Big| Y^{(i)}=0}
$$

$$
P(X^{(i)}_j = 1\Big| Y^{(i)}=1)=\phi_{j\Big| Y^{(i)}=1}
$$

###### Assumption

$$
\begin{aligned}
P(X_1,...,X_{10000}\Big| Y)
&=P(X_1\Big| Y)P(X_2\Big|X_1, Y)P(X_3\Big|X_1,X_2, Y)...P(X_{10000}\Big|..., Y)\\
&=^{assume} P(X_1\Big| Y)P(X_2\Big| Y)P(X_3\Big| Y)...P(X_{10000}\Big|Y)\\
\end{aligned}
$$

Which is to be simplified as 
$$
P(X^{(i)}\Big| Y^{(i)})=\prod_{j=1}^{n}P(X^{(i)}_j\Big| Y^{(i)})
$$

###### Result of Maximum Likelihood

$$
\phi _{Y^{(i)}}=\frac{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}{m}
$$

$$
\phi_{j\Big|Y^{(i)}=0}=\frac{\sum_{i=1}^m\iota\{X^{(i)}_j=1,Y^{(i)}=0\}}{\sum_{i=1}^m\iota\{Y^{(i)}=0\}}
$$

$$
\phi_{j\Big|Y^{(i)}=1}=\frac{\sum_{i=1}^m\iota\{X^{(i)}_j=1,Y^{(i)}=1\}}{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}
$$

> [!NOTE]
>
> The biggest problems is $\phi_{j\Big|Y^{(i)}=0}$ and $\phi_{j\Big|Y^{(i)}=1}$​ is all zero. But that doesn't mean that the chance is totally zero.
>
> The solution to this kind of problem is to take a technique called the **Plus Moving**.

###### Plus Moving

We just add one success and one failure to the whole data, so every kind of situation at least has one chance of appearance.

**General Expression**
$$
X\in\{1,2,...,k\}
$$

$$
P(X=j)=\frac{\sum_{i=1}^{m}\iota\{X^{(i)}=j\}}{m}
$$

**For Naive Bayes**
$$
\phi_{j\Big| Y=0}=\frac{\sum_{i=1}^m\iota\{X^{(i)}_j=1,Y^{(i)}=0\}+1}{\sum_{i=1}^{m}\iota\{Y^{(i)}=0\}+2}
$$
So this kind of strategy can greatly avoid the appearance of zero in the parameters.

> [!NOTE]
>
> If the data is continuous, then you can create some blocks to change it into discrete data.

###### Disadvantage of Multi-variate Bernoulli Event Model

The traditional naive base has a problem that it there is no difference between the time one word appears.

##### New Bayes( the Multinomial Event Model)

###### Syntax

$$
\text{Dictionary}=\begin{bmatrix}\text{a}\\\text{avoid}\\...\\\text{zed}\end{bmatrix}
$$

$$
X^{(i)}\in\begin{bmatrix}X^{(i)}_1\\X^{(i)}_2\\...\\X^{(i)}_n\\\end{bmatrix}
$$

$$
X_j^{(i)}\in\{1,2,3,...,10000\}
$$

$$
\text{The maximum value of the interval depends on the size of the dictionary.}
$$

$$
n=\text{The length of the email}
$$

###### Assumption

$$
P(X^{(i)}\Big|Y^{(i)})=\prod_{j=1}^mP(X_j^{(i)}\Big|Y^{(i)})
$$

> [!NOTE]
>
> This is exact the same equation used for assumption for the naive bayes we have mentioned before.

###### Parameters

$$
\phi_{Y^{(i)}}=P(Y^{(i)}=1)
$$

$$
\phi_{k\Big|Y^{(i)}=0}=P(X_j^{(i)}=k\Big|Y^{(i)}=0), \text{which means the chance of word $j$ being $k$ of $Y^{(i)}=0$}
$$

$$
\phi_{k\Big|Y^{(i)}=1}=P(X_j^{(i)}=k\Big|Y^{(i)}=1)
$$

###### Result After Maximum Likelihood 

$$
\phi_{k\Big|Y^{(i)}=0}=\frac{\sum_{i=1}^m\Big(\iota\{Y^{(i)}=0\}\sum_{j=1}^n\iota\{X^{(i)}_j=k\}\Big)+1}{\sum_{i=1}^m\Big(\iota\{Y^{(i)}=0\}\cdot n^{(i)}\Big)+\text{dictionary size}}
$$

> [!NOTE]
>
> You can notice that we also use the plus one rule here.

> [!NOTE]
>
> Comparing to the linear regression, the Naive Byes will be much faster, because we don't need to use the gradient descent or something like that.

##### Support Vector Machine

> [!NOTE]
>
> In the logistic regression we mentioned before, the algorithm will not perform well when the edge is not linear, maybe the only way is to add $x^2$ kinds of parameters in the vector, but it is still not really practical.

###### Problem

How to deal with some **not linear cases**?

Although the support vector machine is not working as well as the linear regression in most kind of problems, but it can be a good choice some times.

###### List of Knowledge 

1. Optimal Margin Classifier(Separatable Case)
2. Kernel
3. Inseparable Case(Not Separatable Case)

###### Optimal Margin Classifier

> **Function Margin**
> $$
> h_\Theta (X^{(i)})=g(\Theta^TX^{(i)})
> $$
> and the function $g(x)$ is the sigmoid function.
>
> *Predict:*
>
> - "$1$" if $\Theta^TX^{(i)}\geq 0$, that is when $h_\Theta(X^{(i)})=g(\Theta^TX^{(i)})\geq 0.5$​
> - "$0$" if $\Theta^TX^{(i)}< 0$, that is when $h_\Theta(X^{(i)})=g(\Theta^TX^{(i)})< 0.5$​
>
> **That Means**
>
> 1. If $Y^{(i)}=1$, we hope that $\Theta ^TX^{(i)}>>0$
> 2. If $Y^{(i)}=0$, we hope that $\Theta ^TX^{(i)}<<0$​
>
> **Geometric Margin**
>
> You can notice the situation that there are several seemingly suitable choice for a logistic regression, so which one to be chosen can be a good question.

**Notation**

- Labels 
  $$
  Y^{(i)}\in\{-1,+1\}
  $$

- Have hypothesis output value in $\{-1,+1\}$

- $$
  g(z)=\begin{cases}1,\text{if $z\geq 0$}\\
  -1，\text{otherwise}\end{cases}
  $$


**Mathematical Result**

In this kind of strategy, we will drop $X^{(i)}_0=1$ convention.
$$
h_{W,b}(X^{(i)})=g(W^TX^{(i)}+b)
$$
Functional margin of hyperplane defined by $(W,b)$ with respect to $(X^{(i)},Y^{(i)})$
$$
\hat\Gamma^{(i)}=Y^{(i)}(W^TX^{(i)}+b)
$$

- If $Y^{(i)}=1$, we want $W^TX^{(i)}+b>>0$
- If $Y^{(i)}=-1$, we want $W^TX^{(i)}+b<<0$​
- If $\hat\Gamma^{(i)}>0$, that means $h(X^{(i)})=Y^{(i)}$

Function margin with respect to training set 
$$
\hat\Gamma = \min_{i}\hat\Gamma^{(i)},i=1,2,3,...,m
$$
This time we assume that the training set is linear separatable.

One great way to maximize the function margin is to multiply the parameter $W$ and $b$ by the same factor.

To prevent this way of cheating, we can impose a constraint that is 
$$
||W||=1
$$

$$
(W,b)\rightarrow(\frac{W}{||W||},\frac{b}{||W||})
$$

###### Step to Optimize Margin Classifier(Each of those are equivalence)

- Choose $W,b$ to maximize $\Gamma$

- Maximize $\Gamma$ such that 
  $$
  \frac{Y^{(i)}(W^TX^{(i)}+b)}{||W||}\geq \Gamma,i=1,2,3,...,m
  $$

- Minimize $||W||^2$ such that 
  $$
  Y^{(i)}(W^TX^{(i)}+b)\geq 1
  $$
