#### Lecture 3

#### Locally Weighted and Logic Regression

##### Recalling the Description

> 1. $(X^{(i)},Y^{(i)})$ is the $i^{th}$​ training point
> 2. $X^{(i)}\in R^{(n+1)\times1}$, $X^{(i)}_0 = 1$
> 3. $Y^{(i)}\in R^{1\times 1}$
> 4. $m$ is the total number of training examples
> 5. $n$ is the total number of the features
> 6. $h_\Theta(X^{(i)})=\sum_{j=0}^{n}\Theta_jX^{(i)}_j$​
> 7. $h_\Theta(X)=\Theta^T X$
> 8. $J(\Theta) = \frac{1}{2}\sum_{i=1}^{m}(h_\Theta(X^{(i)})-Y^{(i)})^2$ is called the **cause function**

> [!NOTE]
>
> The regression mentioned in the last lecture is linear regression, which means in that kind of definition, we can just you function $\Theta_0 +\Theta_1X_1$ to estimate the result. However, there are other options like 
>
> 1. $\Theta_0+\Theta_1X_1+\Theta_2X_2^2$
> 2. $\Theta _0+\Theta_1 X_1+\Theta_2\sqrt{X_2}+\Theta_3\log(x)$​
>
> So here we introduce the **Locally Weighted Regression**.

##### Locally Weighted Regression

###### Classification

> 1. Parametric Learning Algorithm
>
>    *Fit fixed set of parameters ($\Theta_i$) to data.*
>
> 2. Non-Parametric Learning Algorithm
>
>    *Amount of data/parameters you need to keep grows(linearly) with the size of data*

> [!NOTE]
>
> The reason for the birth of locally weighted regression is that If we are given a data set in the shape of curve, then a global fitted line may not give a good prediction in the local area. One solution to this concern is that we can weight the sample points by the distance between it and the local area you are focusing on.
>
> To conclude, it is just a weighted version of linear regression.

###### Strategy

> Fit $\Theta$ to minimize 
> $$
> \sum_{i=1}^mW^{(i)}(Y^{(i)}-\Theta^TX^{(i)})^2
> $$
> Where $W^{(i)}$ is a weighting function:
> $$
> W^{(i)}=\exp(-\frac{(X^{(i)}-x)^2}{2\tau^2})
> $$
> You can notice that when $\Big|X^{(i)}-x\Big|$ is small then $W^{(i)}\rightarrow 1$. When $\Big|X^{(i)}-x\Big|$ is big then $W^{(i)}\rightarrow 0$.
>
> > [!TIP]
> >
> > You have to adjust the value of $\tau$ to avoid the result to be overfitting or overloosing.

##### Probability Interpretation of Linear Regression

> Why **least square**?

Assume that $Y^{(i)}=\Theta^TX^{(i)}+\epsilon^{(i)}$, where $\epsilon^{(i)}$ is an error of unmodelled effects, random noise.

Also we assume that $\epsilon^{(i)}$ obeys a normal distribution which is $N(0,\sigma^2)$.

So that 
$$
P(\epsilon^{(i)})=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(\epsilon^{(i)})^2}{2\sigma^2})
$$
And we also assume that the variable $\epsilon$ is independently distributed.

This implies that 
$$
P(Y^{(i)}|X^{(i)},\Theta)=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2})
$$
which is in another way that 
$$
(Y^{(i)}\Big|X^{(i)},\Theta)\sim N(\Theta^TX^{(i)},\sigma^2)
$$

> [!TIP]
>
> $P(Y^{(i)}|X^{(i)},\Theta)$ is not a notation of conditional distribution, it just means that $\Theta$ is just a fixed parameter.

**Maximum Likelihood Estimation**

Here is a definition 
$$
L(\Theta) = P(Y\Big|X;\Theta)=\prod_{i=1}^mP(Y^{(i)}\Big|X^{(i)};\Theta)=\prod_{i=1}^{m}\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2})
$$
$L(\Theta)$ is called the likelihood of the parameters, it is just an application of probability and statistics.
$$
l(\Theta)=\log(L(\Theta))
$$
So that as we learn in probability and statistic class, we can find that 
$$
\begin{aligned}
l(\Theta)
&=\log(L(\Theta))\\
&=\log(\prod_{i=1}^{m}\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2}))\\
&=\sum_{i=1}^{m}(\log(\frac{1}{\sqrt{2\pi}\sigma})-\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2})\\
&=m\log(\frac{1}{\sqrt{2\pi}\sigma})-\sum_{i=1}^{m}\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2}
\end{aligned}
$$
And our aim is to choose $\Theta $ to maximize $L(\Theta)$, which is also to maximize $l(\Theta)$.

And everything can be changed to minimizing $\sum_{i=1}^{m}\frac{(Y^{(i)}-\Theta^TX^{(i)})^2}{2\sigma^2}$, considering $\sigma$ is a constant we have defined ahead. 

That is why we set
$$
J(\Theta) = \frac{1}{2}\sum_{i=1}^{m}(h_\Theta(X^{(i)})-Y^{(i)})^2
$$

> [!WARNING]
>
> So that the basic reason for use least square as the cause function is that we assume the error obey the normal distribution. If you change the distribution of $\epsilon$, then we may have a different preferred cause function.

##### Classification Problem

###### Binary Classification

> $Y^{(i)}\in\{0,1\}$

> [!IMPORTANT]
>
> In this kind of problem, I am sure that linear regression is not a good estimating strategy.
>
> So **never use linear regression for classification problems**.
>
> So we need the **Logistic Regression**

##### Logistic Regression

###### Background

> We want $h_{\Theta}(X)\in[0,1]$

To do this, we need to put our former output into another progress.

###### Mathematical Strategy

$$
h_{\Theta}(X^{(i)})=g(\Theta^TX^{(i)})
$$

$$
g(z)=\frac{1}{1+e^{-z}},\text{which is called sigmoid function or the logistic function.}
$$

> [!NOTE]
>
> The most important advantage of this function is that the range of it is $[0,1]$, and it can be really good representation of probability.

> [!IMPORTANT]
>
> Here is an important assumption that 
> $$
> P(Y^{(i)}=1\Big|X^{(i)};\Theta)=h_\Theta(X^{(i)})
> $$
>
> $$
> P(Y^{(i)}=0\Big|X^{(i)};\Theta)=1-h_\Theta(X^{(i)})
> $$
>
> And now we can divide the value of $Y^{(i)}$ in to 0 and 1.

So the **Equation **is
$$
Y^{(i)} \in\{0,1\}
$$

$$
P(Y^{(i)}\Big|X^{(i)};\Theta)=(h_\Theta(X^{(i)}))^{Y^{(i)}}(1-h_\Theta(X^{(i)}))^{1-Y^{(i)}}
$$

$$
h_{\Theta}(X^{(i)})=g(\Theta^TX^{(i)}),g(z)=\frac{1}{1+e^{-z}}
$$

Then you can notice that 

1. When $Y^{(i)}=1$, we have $P(Y^{(i)}\Big|X^{(i)};\Theta)=h_\Theta(X^{(i)})$​
2. When $Y^{(i)}=0$, we have $P(Y^{(i)}\Big|X^{(i)};\Theta)=1-h_\Theta(X^{(i)})$

###### Using Maximizing Likelihood to analyze the Former Equation

> [!NOTE]
>
> You can notice that there is no more term of $\epsilon$ in this kind of problem, and the variable $Y^{(i)}$ follows another distribution, which as mentioned before, can lead to a different cause function.

**Some Mathematical Background**

We first want to find the derivative of the sigmoid function.
$$
\begin{aligned}
\frac{\partial}{\partial z}g(z)
&=\frac{\partial}{\partial z}\frac{1}{1+e^{-z}}\\
&=-\frac{1}{(1+e^{-z})^2}\frac{\partial}{\partial z}(1+e^{-z})\\
&=\frac{1}{(1+e^{-z})^2}e^{-z}\\
&=g(z)(1-g(z))
\end{aligned}
$$
It will be really useful in the later computation.

**Mathematical Proof**
$$
L(\Theta)=\prod_{i=1}^{m}(h_\Theta(X^{(i)}))^{Y^{(i)}}(1-h_\Theta(X^{(i)}))^{1-Y^{(i)}}
$$

$$
\begin{aligned}
l(\Theta)
&=\log(L(\Theta))\\
&=\log(\prod_{i=1}^{m}(h_\Theta(X^{(i)}))^{Y^{(i)}}(1-h_\Theta(X^{(i)}))^{1-Y^{(i)}})\\
&=\sum_{i=1}^{m}(Y(i)\log(h_\Theta(X^{(i)}))+(1-Y^{(i)})\log(1-h_\Theta(X^{(i)})))
\end{aligned}
$$

Then what we need to do is to find the suitable $\Theta$ to maximize $l(\Theta)$.

Here we will use the **Batch Gradient Ascent**

Which is keeping updating 
$$
\Theta_j = \Theta_j +\alpha\frac{\partial}{\partial\Theta_j}l(\Theta)
$$
This is very similar to the Batch Gradient Descent in the linear regression.

> [!IMPORTANT]
>
> So now what we need to do is to find the value of $\frac{\partial}{\partial\Theta_j}l(\Theta)$

$$
\begin{aligned}
\frac{\partial}{\partial\Theta_j}l(\Theta)
&=\frac{\partial}{\partial\Theta_j}\sum_{i=1}^{m}(Y(i)\log(h_\Theta(X^{(i)}))+(1-Y^{(i)})\log(1-h_\Theta(X^{(i)})))\\
&=\sum_{i=1}^{m}(Y(i)\frac{\partial}{\partial\Theta_j}\log(h_\Theta(X^{(i)}))+(1-Y^{(i)})\frac{\partial}{\partial\Theta_j}\log(1-h_\Theta(X^{(i)})))\\
&=\sum_{i=1}^{m}(Y(i)\frac{1}{h_\Theta(X^{(i)})}\frac{\partial}{\partial\Theta_j}(h_\Theta(X^{(i)}))+(1-Y^{(i)})\frac{1}{1-h_\Theta(X^{(i)})}\frac{\partial}{\partial\Theta_j}(1-h_\Theta(X^{(i)})))\\
&=\sum_{i=1}^{m}(Y(i)\frac{1}{h_\Theta(X^{(i)})}\frac{\partial}{\partial\Theta_j}(g(\Theta^TX^{(i)}))+(1-Y^{(i)})\frac{1}{1-h_\Theta(X^{(i)})}\frac{\partial}{\partial\Theta_j}(1-g(\Theta^TX^{(i)})))\\
&=\sum_{i=1}^{m}(Y(i)\frac{1}{h_\Theta(X^{(i)})}g(\Theta^TX^{(i)})(1-g(\Theta^TX^{(i)}))\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)})-(1-Y^{(i)})\frac{1}{1-h_\Theta(X^{(i)})}g(\Theta^TX^{(i)})(1-g(\Theta^TX^{(i)}))\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)}))\\
&=\sum_{i=1}^{m}(Y(i)\frac{1}{h_\Theta(X^{(i)})}h_\Theta(X^{(i)})(1-h_\Theta(X^{(i)}))\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)})-(1-Y^{(i)})\frac{1}{1-h_\Theta(X^{(i)})}h_\Theta(X^{(i)})(1-h_\Theta(X^{(i)}))\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)}))\\
&=\sum_{i=1}^{m}(Y(i)(1-h_\Theta(X^{(i)}))\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)})-(1-Y^{(i)})h_\Theta(X^{(i)})\frac{\partial}{\partial\Theta_j}(\Theta^TX^{(i)}))\\
&=\sum_{i=1}^{m}(Y(i)(1-h_\Theta(X^{(i)}))X_j^{(i)}-(1-Y^{(i)})h_\Theta(X^{(i)})X_j^{(i)})\\
&=\sum_{i=1}^{m}(Y^{(i)}-h_\Theta(X^{(i)}))X^{(i)}_j
\end{aligned}
$$

Then we have the **Updating Equation** is 
$$
\Theta_j = \Theta_j +\alpha\sum_{i=1}^{m}(Y^{(i)}-h_\Theta(X^{(i)}))X^{(i)}_j
$$

> [!NOTE]
>
> There are always two ways for updating the parameter, the one is gradient descent, and another one is the Newton's Method.

##### Newton's Method

> Example
>
> You have a function $f$ and you want to find the value of $\Theta $ such that $f(\Theta)=0$
>
> > [!NOTE]
> >
> > When you want to find the minimum point of some function, then you can just apply the Newton's method to the derivative function of it.
>
> If we want minimizing $l(\Theta)$, then we need to find the point that $l'(\Theta)=0$

###### Step for Newton's Method

- Find one initial value of the $\Theta$.
- Get the point of $(\Theta,f(\Theta))$.
- Calculate the tangent line on that point of the curve.
- Find the interaction of that line with the axis, get a new value for $\Theta$.
- Restart from step 2.

> [!NOTE]
>
> I think the advantage of this method is that it can lead to a quicker convergence wehn you are approaching to the optimal value of $\Theta$

###### Simplified Mathematical Representation

$$
\Theta ^{(t+1)}=\Theta^{(t)}-\frac{f(\Theta^{(t)})}{f'(\Theta^{(t)})}
$$

> [!NOTE]
>
> If here we let $f(\Theta^{(t)})$ to be $l'(\Theta^{(t)})$
>
> When we will have
> $$
> \Theta ^{(t+1)}=\Theta^{(t)}-\frac{l'(\Theta^{(t)})}{l''(\Theta^{(t)})}
> $$
> But the question here is how to calculate the first derivative and the second derivative of $l(\Theta^{(i)})$.

###### Complete Mathematical Representation

$$
\Theta^{(t+1)}=\Theta^{(t)}+H^{-1}\nabla_\Theta(l(\Theta))
$$

$$
\text{$H$ is the Hessian matrix}
$$

$$
H_{ij}=\frac{\partial^2l(\Theta)}{\partial(\Theta_{i1})\partial(\Theta_{j1})}
$$

> [!NOTE]
>
> You can notice that when the number of features is not really big, then we can see that by using the Newton's Method, the value of $\Theta$ can converge very fast, because it needs less iteration to give a bigger step.
>
> However, when the number of $n$ is really big, it is really not a good idea to apply the Newton's Method, for it need lots of computation time to achieve an inverse of a super large matrix.

