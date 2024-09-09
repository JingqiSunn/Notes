#### Lecture 2 

#### Linear Regression and Gradient Descent

##### Supervised Learning

> **Definition**: *You have a data set and you feed it into the learning algorithm, helping the algorithm to make good prediction.* 
>
> **Syntax**: 
>
> *$h$(Hypothesis)*
>
> **Design**: 
>
> ```mermaid
> graph TD
> A(inputDataSet)--> B(h) --> C(OutputPrediction)
> 
> ```
>
> **How to represent $h$**
> $$
> h(x)=\theta_0+\theta_1 h
> $$
>
> > [!NOTE]
> >
> > The equation above is a simplified one when we only have one input. However in the daily life, there are lots more inputs, so here we have the complicated one.
> > $$
> > h(x)=\sum_{j=0}^n\theta_jx_j
> > $$
> > On the equation above, we have $n$ to be the total number of the variables, and we can define $x_0$​​ to be 1 all the time.
> >
> > Or we can represent it in the term of matrix multiplication.
> > $$
> > h(x)=\Theta^T\cdot X
> > $$
> > where
> > $$
> > \Theta = \begin{bmatrix}\theta_0\\\theta_1\\\theta_2\\...\\\theta_n\end{bmatrix},\quad X=\begin{bmatrix}x_0\\x_1\\x_2\\...\\x_n\end{bmatrix}=\begin{bmatrix}1\\x_1\\x_2\\...\\x_n\end{bmatrix}
> > $$
> > **Syntax:**
> >
> > $\Theta$ is called parameters, $m$ is called the number of examples, $n$ is called the number of features of the example, $X$ is input features, $Y$ is called the output or the target variable, $(X,Y)$ is called the training example, and $(X^{(i)},Y^{(i)})$ is called the $i^{th}$​ training example.
> >
> > If you have $n$ features then you will have $n+1$​ dimension vector.
> >
> > **Strategy:**
> >
> > The final target is to find the parameter $\Theta$ such that $h(X)$ to be closest to $y$​.
> >
> > ##### Linear Regression
> >
> > > **Definition**: *We have to choose* $\Theta$ *to minimize* $J(\Theta)=\frac{1}{2}\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)})^2$, which in the term of linear algebra is $$\frac{1}{2}|(h_{\Theta}(X))^{T}-Y|^2$$
> >
> > The reason we put $\frac{1}{2}$ is that it will make everything after taking the derivative easier.
>
> Example:
>
> | Size | Number Of Rooms | Price |
> | :--: | :-------------: | :---: |
> | 2104 |        3        |  400  |
> | 1416 |        2        |  232  |
> | 1534 |        3        |  315  |
> | 852  |        2        |  128  |

##### Gradient Descent

> **Definition:** *It is a strategy in math*.
>
> **General Strategy**:
>
> 1. Start with some $\Theta$
> 2. Keep changing $\Theta$ to reduce $J(\Theta)$
>
> **Disadvantage**: It will maybe be trapped in the local minima.
>
> **Mathematical Strategy:**
> $$
> \Theta_j = \Theta_j-\alpha\frac{\partial}{\partial \Theta_j}J(\Theta),j = 0,1,2,...,n\text{ and $\alpha$ is called the learning rate.}
> $$
>
> $$
> \begin{aligned}
> \Theta_j 
> &= \Theta_j-\alpha\frac{\partial}{\partial \Theta_j}J(\Theta)\\
> &=\Theta_j-\alpha\frac{\partial}{\partial \Theta_j}(\frac{1}{2}(\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)})^2))\\
> &=\Theta_j - \frac{\alpha}{2}\sum_{i=1}^{m}\frac{\partial}{\partial \Theta_j}((h_{\Theta}(X^{(i)})-Y^{(i)})^2)\\
> &=\Theta_j - \frac{\alpha}{2}\sum_{i=1}^{m}\cdot 2\cdot (h_{\Theta}(X^{(i)})-Y^{(i)}) \frac{\partial}{\partial \Theta_j}(h_{\Theta}(X^{(i)})-Y^{(i)})\\
> &=\Theta_j - \alpha\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)}) \frac{\partial}{\partial \Theta_j}(h_{\Theta}X^{(i)})\\
> &=\Theta_j - \alpha\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)}) \frac{\partial}{\partial \Theta_j}(\Theta_j\cdot X^{(i)}_j)\\
> &=\Theta_j - \alpha\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)})X^{(i)}_j\\
> \end{aligned}
> $$
>
> > [!IMPORTANT]
> >
> > We can notice that when the number of $i$ is really huge, then doing even just one step in Gradient Descent can cost huge amount of calculation. So this kind of Gradient Descent is called the **Batch Gradient Descent**.
>
> **Mathematical Strategy Result:**
> $$
> \Theta_j = \Theta_j-\alpha\frac{\partial}{\partial \Theta_j}J(\Theta)=\Theta_j - \alpha\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)})X^{(i)}_j
> $$

###### Stochastic Gradient Descent

> **Pseudo Code** (do the same thing for every $j$)
>
> ```
> repeat{
> 	For i = 1 to n{
> 		 \Theta_j = \Theta_j - \alpha(h_{\Theta}(X^{(i)})-Y^{(i)})X^{(i)}_j
> 	}
> }
> ```
>
> > [!NOTE]
> >
> > You can see that in the Stochastic Gradient Descent, we just choose one training example randomly each time to calculate for a pseudo gradient, this kind of strategy can mostly save time for computation.
> >
> > It will take a slowly, noisy, kind of random path.
> >
> > It is not really converge, but it really does a good job when you have a really big data set.

##### Normal Equation (Part One)

> **Definition**: *It is a strategy that is only available for linear regression that can get the optimal parameter $\Theta$ directly.*
>
> **Syntax/Notation**
> $$
> \nabla_{\Theta}J(\Theta)=\begin{bmatrix}\frac{\partial}{\partial \Theta_0}J\\\frac{\partial}{\partial \Theta_1}J\\\frac{\partial}{\partial \Theta_2}J\\...\\\frac{\partial}{\partial \Theta_n}J\end{bmatrix}, \Theta\in \R^{n+1}
> $$
> **Mathematical Strategy**
> $$
> \nabla_{\Theta}J(\Theta)=\begin{bmatrix}\frac{\partial}{\partial \Theta_0}J\\\frac{\partial}{\partial \Theta_1}J\\\frac{\partial}{\partial \Theta_2}J\\...\\\frac{\partial}{\partial \Theta_n}J\end{bmatrix} = \vec{0}
> $$
>
> > [!NOTE]
> >
> > If you can solve this equation, you can directly get the value of $\Theta$​ that ensures a local minimum

##### Other Mathematical Background

> $tr(A)=tr(A^T)$

*Proof:*

We set $A\in R^{n\times n}$, then we will have that 
$$
\begin{aligned}
tr(A)
&= A_{11}+A_{22}+...+A_{nn}\\
&= A^T_{11}+A^T_{22}+...+A^T_{nn}\\
&= tr(A^T)
\end{aligned}
$$
So we can get the conclusion that 
$$
tr(A)=tr(A^T)
$$

> Define $f(A)=tr(AB)$, $\nabla_Af(A)$ is of the same size of $A$ while $\nabla_Af(A)_{ij}=\frac{\partial}{\partial A_{ij}}f(A)$, then we can have $\nabla_Af(A)=B^T$

*Proof:*

If we set $A\in R^{m\times n}$, then we can have that if we need $AB$ to be an square matrix, we need $B\in R^{n\times m}$,

And we can get that $\nabla_Af(A)\in R^{m\times n}$, which is the same size of $B^T$,
$$
\begin{aligned}
\nabla_Af(A)_{ij}
&=\frac{\partial}{\partial A_{ij}}f(A)\\
&=\frac{\partial}{\partial A_{ij}}tr(AB)\\
&=\frac{\partial}{\partial A_{ij}}(A_{ij}\cdot B_{ji}+...)\\
&=B_{ji}\\
&=B^T_{ij}
\end{aligned}
$$
So that we prove that $\nabla_Af(A)=B^T$

> $tr(AB) = tr(BA)$

*Proof:*
$$
\begin{aligned}
tr(AB)
&=\sum_{i=1}^{m}\sum_{j=1}^{n}A_{ij}\cdot B_{ji}\\
&=\sum_{i=1}^{m}\sum_{j=1}^{n}B_{ij}\cdot A_{ji}\\
&= tr(BA)
\end{aligned}
$$
So we proved that $tr(AB)=tr(BA)$

> [!NOTE]
>
> For the similar reason we have $tr(ABC)=tr(CAB)$

> $\nabla_A tr(AA^T C)=CA+C^TA$

*Proof:*

In my definition if matrix $E\in R^{3\times 4}$, it means that the matrix has 3 rows and 4 columns.

Firstly we define the size of $A$ to be $m\times n$, then we have $A^T\in R^{n\times m}$, so that $A A^T$ is in $R^{m\times m }$.

To make $AA^TC$ being able to have a trace, then we can find that the size of $C$ has to be $m\times m$.

According to the definition of $\nabla_A f(A)$ we can find that the size of $\nabla_A tr(AA^T C)$ is the same as the size of $A$ which is in $R^{m\times n}$. 

Let us look at $CA+C^TA$, the size of it is actually also in $R^{m\times n}$.

The next step is to prove that the component in the same position are the same.
$$
\begin{aligned}
\nabla_A tr(AA^T C)_{ij}
&=\frac{\partial}{\partial A_{ij}}tr(AA^T C)\\
&=\frac{\partial}{\partial A_{ij}}(\sum_{k=1}^m(AA^T)_{ik}C_{ki}+\sum_{k=1}^m(AA^T)_{ki}C_{ik})\\
&=\frac{\partial}{\partial A_{ij}}(\sum_{k=1}^mA_{ij}A^T_{jk}C_{ki}+\sum_{k=1}^mA_{kj}A^T_{ji}C_{ik})\\
&=\sum_{k=1}^{m}(C_{ik}+C_{ki})\cdot A_{kj}
\end{aligned}
$$

$$
\begin{aligned}
(CA+C^TA)_{ij}
&=\sum_{k=1}^{m}C_{ik}\cdot A_{kj}+\sum_{k=1}^{m}C^T_{ik}\cdot A_{kj}\\
&=\sum_{k=1}^{m}(C_{ik}+C_{ki})\cdot A_{kj}
\end{aligned}
$$

So we proved that $\nabla_A tr(AA^T C)=CA+C^TA$

> $\nabla_\Theta (\Theta^T A\Theta)=(A+A^T)\Theta$, $\Theta$ is a column vector in $R^{n\times 1}$

*Proof:*

We have proved that $\nabla_A tr(AA^T C)=CA+C^TA$

And here we can see that $\Theta^T A\Theta$ is actually a scalar here, so that we have 
$$
\Theta^T A\Theta = tr(\Theta^T A\Theta)
$$
According to the rule of matrix multiplication, we can get that the size of matrix $A$ is $n\times n$

Also we can work out that 
$$
\begin{aligned}
tr(\Theta^T A\Theta)
&=\sum_{i=1}^{n}\Theta^T_{1i}(A\Theta)_{i1}\\
&=\sum_{j=1}^{n}\sum_{i=1}^{n}\Theta^T_{1i}A_{ij}\Theta _{j1}\\
&=\sum_{j=1}^{n}\sum_{i=1}^{n}\Theta_{i1}A_{ij}\Theta _{j1}\\
\end{aligned}
$$

$$
\begin{aligned}
tr(\Theta \Theta^TA)
&=\sum_{i=1}^{n}\sum_{j=1}^{n}(\Theta\Theta^T)_{ji}A_{ij}\\
&=\sum_{i=1}^{n}\sum_{j=1}^{n}\Theta _{j1}\Theta _{i1}A_{ij}\\
\end{aligned}
$$

So we can find a conclusion that 
$$
tr(\Theta ^TA\Theta)=tr(\Theta \Theta^T A), \text{$\Theta$ is a column vector}
$$
Using the conclusion we just proved above, we can figure out that 
$$
\begin{aligned}
\nabla_\Theta (\Theta^T A\Theta)
&=\nabla_\Theta (tr(\Theta^T A\Theta))\\
&=\nabla_\Theta (tr(\Theta \Theta^T A))\\
&=A\Theta+A^T\Theta
\end{aligned}
$$
So that we proved that $\nabla_\Theta (\Theta^T A\Theta)=(A+A^T)\Theta$

> $\nabla_{\Theta}(\Theta^TX)=X$, $\Theta$ is a column vector in $R^{n\times 1}$, $X$ is a column vector in $R^{n\times 1}$

*Proof:*

We have already known that $\Theta \in R^{n\times 1},X\in R^{n\times 1}$.

So that the size of $\nabla_{\Theta}(\Theta^TX)$ is $n\times 1$, and the size of $X$ is also $n\times 1$

So that we have the size of $\nabla_{\Theta}(\Theta^TX)$ and $X$ are the same, the next step is to confirm that the entry in each positions are the same.
$$
\begin{aligned}
\nabla_{\Theta}(\Theta^TX)_{i1}
&=\frac{\partial}{\partial \Theta_{i1}}(\Theta^TX)\\
&=\frac{\partial}{\partial \Theta_{i1}}\sum_{j=1}^n(\Theta_{j1}X_{j1})\\
&=\frac{\partial}{\partial \Theta_{i1}}(\Theta _{i1}X_{i1})\\
&=X_{i1}
\end{aligned}
$$
So that we proved $\nabla_{\Theta}(\Theta^TX)=X$

##### Normal Equation (Part Two)

> [!NOTE]
>
> Based on the complemental mathematical information above, we can continue to push forwards this strategy.

> **Transform**
>
> The reason for this is that the mathematical information we have is all based on the linear algebra. More specific, is the matrix multiplication. So that it seems a good idea that to transform $J(\Theta)$ into the form of matrix multiplication.
>
> What we have here is $\nabla_{\Theta}J(\Theta)=\begin{bmatrix}\frac{\partial}{\partial \Theta_0}J\\\frac{\partial}{\partial \Theta_1}J\\\frac{\partial}{\partial \Theta_2}J\\...\\\frac{\partial}{\partial \Theta_n}J\end{bmatrix}, \Theta\in \R^{n+1}$.
> $$
> J(\Theta)=\frac{1}{2}\sum_{i=1}^{m}(h_{\Theta}(X^{(i)})-Y^{(i)})^2
> $$
> *Syntax/Notation:*
> $$
> X= \begin{bmatrix}---(X^{(1)})^T---\\---(X^{(2)})^T---\\...\\---(X^{(m)})^T---\\\end{bmatrix}
> $$
>
> $$
> \Theta=\begin{bmatrix}\theta_0\\\theta_1\\...\\\theta_n\\\end{bmatrix}
> $$
>
> $$
> Y = \begin{bmatrix}Y^{(1)}\\Y^{(2)}\\...\\Y^{(m)}\\\end{bmatrix}
> $$
>
> $$
> H_\Theta(X)=\begin{bmatrix}h_\Theta(X^{(1)})\\h_\Theta(X^{(2)})\\...\\h_\Theta(X^{(3)})\\\end{bmatrix}=X\cdot \Theta=\begin{bmatrix}(X^{(1)})^T\Theta\\(X^{(2)})^T\Theta\\...\\(X^{(m)})^T\Theta\\\end{bmatrix}
> $$
>
> *Result:*
>
> Then we find that 
> $$
> J(\Theta) = \frac{1}{2}(X\Theta-Y)^T(X\Theta-Y)
> $$
>
> > [!NOTE]
> >
> > Now we have already achieve a better form of the function $J(\Theta)$
>
> **Find the Normal Equation**
> $$
> \begin{aligned}
> \nabla _\Theta J(\Theta) 
> &=\nabla_{\Theta}\frac{1}{2}(X\Theta-Y)^T(X\Theta-Y)\\
> &=\nabla_{\Theta}\frac{1}{2}(\Theta^TX^TX\Theta-\Theta^TX^TY-Y^TX\Theta+Y^TY)\\
> &=\nabla_{\Theta}\frac{1}{2}(\Theta^TX^TX\Theta-2\Theta^TX^TY+Y^TY)\\
> &=\nabla_{\Theta}\frac{1}{2}(\Theta^TX^TX\Theta)-\nabla_{\Theta}(\Theta^TX^TY)+\nabla_{\Theta}\frac{1}{2}(Y^TY)\\
> &=\frac{1}{2}(X^TX\Theta+(X^TX)^T\Theta)-\nabla_{\Theta}(\Theta^TX^TY)\\
> &=X^TX\Theta-\nabla_{\Theta}(\Theta^TX^TY)\\
> &=X^TX\Theta-X^TY
> \end{aligned}
> $$
> The normal equation is just
> $$
> X^TX\Theta-X^TY = \vec{0}
> $$
>
> $$
> X^TX\Theta=X^TY
> $$
>
> $$
> \Theta=(X^TX)^{-1}X^TY
> $$
>
> > [!IMPORTANT]
> >
> > Actually we can explain the mathematical formula of the normal equation with the knowledge from the four space of a matrix.
> >
> > The target of our strategy is to find the best $\Theta$ so that $X\Theta -Y$ has the shortest length.
> >
> > What we know is that the shortest distance from the vector to a plate is the vertical orthogonal length. So that we need $X\Theta -Y$ is orthogonal with $X$, which means 
> > $$
> > X^T(X\Theta -Y)=\vec{0}
> > $$
> > This is another explanation of how the normal function comes.

























