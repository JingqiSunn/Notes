#### Lecture 7

#### Kernels

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

> **The Reason of Equivalence of Step Two and Three**
> $$
> \frac{Y^{(i)}(W^TX^{(i)}+b)}{||W||}\geq \Gamma,i=1,2,3,...,m,\text{ Maximize $\Gamma$}
> $$
> Set $||W||=\frac{1}{\Gamma}$
>
> So that we will have $Y^{(i)}(W^TX^{(i)}+b)\geq 1$ and we need to minimize $||W||.$

>  **How to Solve the Geometric Margin**
>
>  One Conclusion is that 
>  $$
>  W=\sum_{i=1}^m\beta_i Y^{(i)}X^{(i)}=\sum_{i=1}^m\alpha_iX^{(i)}
>  $$
>  which means that the parameter $W$ can be expressed as a linear combination of the training example.
>
>  **Intuition One**
>
>  > [!NOTE]
>  >
>  > We have to remember one thing that the idea of functional margin is from the logistic regression. And the way to solve the logistic regression is to do the Gradient Descent. Which is that for scholastic one 
>  > $$
>  > \Theta_j=\Theta_j-\alpha(h_\Theta(X^{(i)})-Y^{(i)})X^{(i)}
>  > $$
>
>  You can see that in the updating rule shown above, in the every steps' updating, you just add some multiple $X^{(i)}$ to the parameter $\Theta$. And $\Theta $ is all the same as $W$ despite the tradition of $X^{(i)}_0=1$
>
>  And the conclusion is also true for the batch gradient Descent. 
>
>  **Intuition two**
>
>  The margin is always in the same space of the training $X^{(i)}$ so that it can be represented as a linear combination of the $X^{(i)}$​.
>
>  **Solve the Geometric Margin Problem**
>
>  In the optimize margin classifier mentioned in the previous section, we have the third kind of representation of this problem is that 
>
>  - Minimize $||W||^2$ such that 
>
>  $$
>  Y^{(i)}(W^TX^{(i)}+b)\geq 1
>  $$
>
>  And we have already introduced our conclusion that 
>  $$
>  W=\sum_{i=1}^m\alpha_i Y^{(i)}X^{(i)}=\sum_{i=1}^m\beta_iX^{(i)}
>  $$
>  So what we need is to minimize $W^TW$ under the condition that $W=\sum_{i=1}^m\alpha_i Y{(i)}X^{(i)}=\sum_{i=1}^m\beta_iX^{(i)}$.
>
>  That is 
>  $$
>  \begin{aligned}
>  \min (W^TW)
>  &=\min((\sum_{i=1}^m\alpha_i Y{(i)}X^{(i)})^T\sum_{j=1}^m\alpha_j Y{(j)}X^{(j)})\\
>  &=\min(\sum_{i=1}^m\sum_{j=1}^m\alpha_i\alpha_jY^{(i)}Y^{(j)}<X^{(i)},X^{(j)}>)\\
>  \end{aligned}
>  $$
>  And we have the previous conclusion that 
>  $$
>  Y^{(i)}(W^TX^{(i)}+b)\geq 1
>  $$
>
>  $$
>  Y^{(i)}(\sum_{j=1}^m\alpha_jY^{(j)}X^{(j)}X^{(i)}+b)\geq 1
>  $$
>
>  $$
>  Y^{(i)}(\sum_{j=1}^m\alpha_jY^{(j)}<X^{(j)},X^{(i)}>+b)\geq 1
>  $$
>
>  After complex derivation we can draw a conclusion that the problem can be further simplified to be 
>  $$
>  \max(\sum_{i=1}^m\alpha_i-\frac{1}{2}\sum_{i=1}^m\sum_{j=1}^mY^{(i)}Y^{(j)}<X^{(i)},X^{(j)}>)
>  $$
>  such that $\alpha_i\geq 0$ and $\sum_{i=1}^m Y^{(i)}\alpha_i=0$
>
>  1. Solve the parameter
>
>  2. Make the prediction
>
>  $$
>  \begin{aligned}
>    h_{W,b}(X^{(i)})
>    &=g(W^TX^{(i)}+b)\\
>    &=g((\sum_{j=1}^m\alpha_jY^{(j)}X^{(j)})^TX^{(i)}+b)\\
>    &=g(\sum_{j=1}^m\alpha_jY^{(j)}<X^{(j)},X^{(i)}>+b)\\
>    \end{aligned}
>  $$

##### Kernel Trick

###### Steps

1. Write your algorithm in terms of $<X^{(i)},X^{(j)}>$

2. Let there be some mapping from $X^{(i)}$ to $\phi(X^{(i)})$

   > [!NOTE]
   >
   > For example we can have 
   > $$
   > X^{(i)}\rightarrow\phi(X^{(i)})=\begin{bmatrix}X^{(i)}\\{X^{(i)}}^2\\...\end{bmatrix}
   > $$
   >
   > $$
   > \begin{bmatrix}X^{(i)}_1\\X^{(i)}_2\end{bmatrix}\rightarrow\phi(X^{(i)})=\begin{bmatrix}X^{(i)}_1\\X^{(i)}_2\\{X^{(i)}_1}^2\\{X^{(i)}_2}^2\\...\end{bmatrix}
   > $$
   >
   > That means you can enlarge the dimension of your feature vector.

3. Find a way to compute $K(X^{(i)},X^{(j)})=\phi(X^{(i)})^T\phi(X^{(j)})$

4. Replace $<X^{(i)},X^{(j)}>$ in the algorithm with $K(X^{(i)},K^{(j)})$

###### Practical Trick to Reduce the Computational Complexity

Suppose we have 
$$
X^{(i)}\in R^{n},X^{(j)}\in R^{n}
$$

$$
\phi(X^{(i)})\in R^{n^2}=\begin{bmatrix}X^{(i)}_1X^{(i)}_1\\X^{(i)}_1X^{(i)}_2\\X^{(i)}_1X^{(i)}_3\\...\\X^{(i)}_nX^{(i)}_n\end{bmatrix}
$$

$$
\phi(X^{(j)})\in R^{n^2}=\begin{bmatrix}X^{(j)}_1X^{(j)}_1\\X^{(j)}_1X^{(j)}_2\\X^{(j)}_1X^{(j)}_3\\...\\X^{(j)}_nX^{(j)}_n\end{bmatrix}
$$

So we got that the computational complexity of $\phi(X^{(i)})\phi(X^{(j)})$ is $O(n^2)$

But we can have some tricks to improve it.

**Result**
$$
K(X^{(i)},X^{(j)}) = (\phi(X^{(i)}))^T\phi(X^{(j)})=((X^{(i)})^T X^{(j)})^2
$$
We can see that after this kind of transformation, we can achieve the same task with the time complexity $O(n)$

**Proof**
$$
\begin{aligned}
K(X^{(i)},X^{(j)})
&=(\phi(X^{(i)}))^T\phi(X^{(j)})\\
&=\sum_{h=1}^n\sum_{k=1}^n((X^{(i)}_hX^{(i)}_k)(X^{(j)}_hX^{(j)}_k))\\
&=(\sum_{h=1}^nX^{(i)}_hX^{(j)}_h)(\sum_{k=1}^nX^{(i)}_kX^{(j)}_k)\\
&=((X^{(i)})^T X^{(j)})^2
\end{aligned}
$$
**Application One**

If we make some changes to the predefined feature lecture. 

Previously, we defined the feature vector as 
$$
\phi(X^{(i)})\in R^{n^2+2n+1}=\begin{bmatrix}X^{(i)}_1X^{(i)}_1\\X^{(i)}_1X^{(i)}_2\\X^{(i)}_1X^{(i)}_3\\...\\X^{(i)}_nX^{(i)}_n\\\sqrt{2c}X^{(i)}_1\\\sqrt{2c}X^{(i)}_2\\...\\\sqrt{2c}X^{(i)}_n\\c\end{bmatrix}
$$

$$
\phi(X^{(j)})\in R^{n^2+2n+1}=\begin{bmatrix}X^{(j)}_1X^{(j)}_1\\X^{(j)}_1X^{(j)}_2\\X^{(j)}_1X^{(j)}_3\\...\\X^{(j)}_nX^{(j)}_n\\\sqrt{2c}X^{(j)}_1\\\sqrt{2c}X^{(j)}_2\\...\\\sqrt{2c}X^{(j)}_n\\c\end{bmatrix}
$$

Then now we will have the similar conclusion that 
$$
K(X^{(i)},X^{(j)})=((X^{(i)})^TX^{(j)}+c)^2,c\in R
$$
**Application Two**

You may not be satisfied by the second degree, and the kernel can do lot more. You can define a number $d$

Then we can have 
$$
K(X^{(i)},X^{(j)})=((X^{(i)})^TX^{(j)}+c)^d
$$
Then if the $d$ has the value of $5$, then we can say that all kinds of polynomials under the power of $5$ are all involved in the expression,  which can support us to do the better prediction.

> [!NOTE]
>
> Most of the sample points in the daily life are always non-linear in our first dimensional space, but if we can make some linear feature of the data points by using kernel to introduce the higher dimensional space.

##### How to Make Kernels

###### Principle

- If $X^{(i)},X^{(j)}$ are similar, which means in the similar direction in the space. Then we will have $K(X^{(i)},X^{(j)})=(\phi(X^{(i)})^T\phi(X^{(j)}))$ to be large.
- If $X^{(i)},X^{(j)}$ are not similar, we will have $K(X^{(i)},X^{(j)})=(\phi(X^{(i)})^T\phi(X^{(j)}))$ to be small.

And here is one example of a suitable Kernel Function. 
$$
K(X^{(i)},X^{(j)})=\exp(-\frac{||X^{(i)}-X^{(j)}||^2}{2\sigma^2})
$$
So why it is a good Kernel Function?

> [!NOTE]
>
> It turns out that it is a kernel function called the Gaussian Kernel.
>
> The most commonly used Kernel is called the linear kernel
> $$
> K(X^{(i)},X^{(j)})=(X^{(i)})^TX^{(j)}
> $$
>
> $$
> \phi(X^{(i)})=X^{(i)}
> $$
>
> I think more than half of the models before actually used this kernel, because it did not introduce a higher dimensional space.
>
> **Gaussian Kernel**
> $$
> \phi(X^{(i)})\in R^{\infty}
> $$
> This kernel use the whole dimension, and it will not take too much computation.

**Reasons**

1. $$
   K(X^{(i)},X^{(i)})=0
   $$

2. But the most important principle is that whether $K(X^{(i)},X^{(j)})=(\phi(X^{(i)})^T\phi(X^{(j)}))$ for some suitable $X^{(i)}$

   > [!NOTE]
   >
   > Here we will use our mathematical approach to try to explain this theorem.
   >
   > Let $\{X^{(1)},X^{(2)},...,X^{(d)}\}$ are $d$ our training points.
   >
   > Let $K\in R^{d\times d}$ which is a override definition of $K$, here $K$ is a kernel matrix. 
   > $$
   > K_{ij}=K(X^{(i)},X^{(j)})
   > $$
   > Now give a vector $z$, we will have
   > $$
   > \begin{aligned}
   > z^TKz
   > &=\sum_{i=1}^d\sum_{j=1}^dz_iK_{ij}z_j\\
   > &=\sum_{i=1}^{d}\sum_{j=1}^dz_i(\phi(X^{(i)}))^T\phi(X^{(j)})z_j\\
   > &=\sum_{k=1}^d\sum_{i=1}^{d}\sum_{j=1}^dz_i\phi(X^{(i)})_k\phi(X^{(j)})_kz_j\\
   > &=\sum_{k=1}^d(\sum_{i=1}^dz_i\phi(X^{(i)})_k)^2\\
   > &\geq 0
   > \end{aligned}
   > $$
   > which means that the kernel matrix is positive semi definite.
   >
   > And the first reason mentioned will be satisfied.
   >
   > **Theorem(Mercer)**
   >
   > > $K$ is a valid function such that there exist corresponding to make sure $K(X^{(i)},X^{(j)})=(\phi(X^{(i)}))^T\phi(X^{(j)})$ if and only if for any $d$ points the matrix is positive semi definite.

**Problem**

When your data set is a little bit noisy, then for example you used the Gaussian Kernel. There will be two problem:

1. You will find it really hard to separate all the data set.
2. Overfitting.

To fix this kind of problem, we have to introduce **linear norm soft margin support vector machine**

##### Linear Norm Soft Margin Support Vector Machine

This is just a little adjustment on the very basic kind of geometric margin.

In the geometric machine, one of the three equivalence goal is minimize $||W||^2$ such that 
$$
Y^{(i)}(W^TX^{(i)}+b)\geq 1
$$
But maybe it is because of this kind of strict rule that leads to the overfitting training problem. 

The target of linear norm soft margin support vector machine is to change some condition and loose some constraint.

Here is how it works:
$$
\min(\frac{1}{2}||W||^2+c\sum_{i=1}^m\xi_i)
$$
such that 
$$
Y^{(i)}(W^TX^{(i)}+b)\geq 1-\xi_i,i=1,2,3,...,m
$$

$$
\xi_i\geq 0
$$

Then little bad noisy sample points will not influence badly on the whole distribution result.

To control how loose it is, you can change the value of $\xi$.

There is some conclusion of the parameter for the geometric margin previous this section as followed
$$
\max(\sum_{i=1}^m\alpha_i-\frac{1}{2}\sum_{i=1}^m\sum_{j=1}^mY^{(i)}Y^{(j)}<X^{(i)},X^{(j)}>)
$$
such that $\alpha_i\geq 0$ and $\sum_{i=1}^m Y^{(i)}\alpha_i=0$

And here the solution just need some basic adjustment.

**Solution for Parameter**
$$
\max(\sum_{i=1}^m\alpha_i-\frac{1}{2}\sum_{i=1}^m\sum_{j=1}^mY^{(i)}Y^{(j)}<X^{(i)},X^{(j)}>)
$$
such that $0\leq \alpha_i\leq c$ and $\sum_{i=1}^m Y^{(i)}\alpha_i=0$

Here $c$ is the parameter we choose in the linear norm soft margin support vector machine.