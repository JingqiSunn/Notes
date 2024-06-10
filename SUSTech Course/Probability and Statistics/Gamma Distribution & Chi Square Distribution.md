#### Gamma Distribution & Chi Square Distribution

##### Gamma Distribution

###### Basic Concept

**Probability Distribution Function**
$$
\text{Gamma}(x|\alpha,\beta)=\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}, x\in(0,\infty)
$$

> *Examine Validity of Probability Distribution Function*

1. $f(x)>0$​
   $$
   \begin{aligned}
   \forall x \in(0,\infty),\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}\geq 0
   \end{aligned}
   $$

2. $\int_{-\infty}^{\infty}f(x)dx=1$​
   $$
   \begin{aligned}
   \int_{-\infty}^{\infty}f(x)dx
   =&\int_{0}^{\infty}\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}dx\\
   =&\frac{\beta}{\Gamma(\alpha)}\int_{0}^{\infty}\beta ^{\alpha -1} x^{\alpha-1}e^{-\beta x}dx\\
   =&\frac{1}{\Gamma(\alpha)}\int_{0}^{\infty}\beta ^{\alpha -1} x^{\alpha-1}e^{-\beta x}d(\beta x)\\
   =&\frac{1}{\Gamma(\alpha)}\int_{0}^{\infty}(\beta x)^{\alpha-1}e^{-\beta x}d(\beta x)\\
   =&\frac{1}{\Gamma(\alpha)}\int_{0}^{\infty}x^{\alpha-1}e^{-x}dx\\
   =&\frac{1}{\Gamma(\alpha)}\cdot \Gamma(\alpha)\\
   =&1
   \end{aligned}
   $$

> *Expectation*

$$
\begin{aligned}
E(x)
=&\int _{-\infty}^{\infty}x\cdot f(x)dx\\
=&\int _{0}^{\infty}x\cdot \frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}dx\\
=&\int _{0}^{\infty}\frac{\beta^\alpha}{\Gamma(\alpha)}x^{(\alpha+1)-1}e^{-\beta x}dx\\
=&\frac{1}{\beta\cdot\Gamma(\alpha)}\int _{0}^{\infty}(\beta x)^{(\alpha+1)-1}e^{-\beta x}d(\beta x)\\
=&\frac{1}{\beta\cdot\Gamma(\alpha)}\int _{0}^{\infty}x^{(\alpha+1)-1}e^{-x}dx\\
=&\frac{\Gamma(\alpha +1)}{\beta\cdot\Gamma(\alpha)}\\
=&\frac{\alpha}{\beta}
\end{aligned}
$$

> *Variance*

$$
\begin{aligned}
D(x)
=&E(x-E(x))^2\\
=&E(x^2)-(E(x))^2\\
=&\int_{-\infty}^{\infty}x^2f(x)dx-\frac{\alpha^2}{\beta^2}\\
=&\int_{0}^{\infty}x^2\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}dx-\frac{\alpha^2}{\beta^2}\\
=&\frac{1}{\beta^2\cdot\Gamma(\alpha)}\int_{0}^{\infty}(\beta x)^{(\alpha+2)-1}e^{-\beta x}d(\beta x)-\frac{\alpha^2}{\beta^2}\\
=&\frac{1}{\beta^2\cdot\Gamma(\alpha)}\int_{0}^{\infty}x^{(\alpha+2)-1}e^{-x}dx-\frac{\alpha^2}{\beta^2}\\
=&\frac{\Gamma(\alpha +2)}{\beta^2\cdot\Gamma(\alpha)}-\frac{\alpha^2}{\beta^2}\\
=&\frac{(\alpha+1)\alpha-\alpha^2}{\beta^2}\\
=&\frac{\alpha}{\beta^2}\\
\end{aligned}Mathematical Operation
$$

###### Mathematical Operation

> $\{X\sim \text{Gamma}(x|\alpha,\beta),\alpha =1\}\vdash \{X\sim \text{Exponential}(\beta)\}$

$$
\begin{aligned}
\text{Gamma}(x|\alpha,\beta)
=&\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}, x\in(0,\infty),\alpha = 1\\
=&\frac{\beta}{\Gamma(1)}e^{-\beta x}, x\in(0,\infty)\\
=&\beta e^{-\beta x}, x\in(0,\infty)\\
\sim&\text{ Exponential}(\beta)
\end{aligned}
$$

> $\{X\sim \text{Gamma}(x|\alpha,\beta),c>0\}\vdash \{Y=cX\sim \text{Gamma}(\alpha,\frac{\beta}{c})\}$

$$
\begin{aligned}
F_Y(y)
=&P(Y\leq y)\\
=&P(cX\leq y)\\
=&P(X\leq \frac{y}{c})\\
=&F_X(\frac{y}{c})\\
\end{aligned}
$$

$$
\begin{aligned}
f_Y(y)
=&\frac{d}{dy}F_Y(y)\\
=&\frac{d}{dy}F_X(\frac{y}{c})\\
=&f_X(\frac{y}{c})\Bigg|\frac{dx}{dy}\Bigg|\\
=&\frac{\beta^\alpha}{\Gamma(\alpha)}(\frac{y}{c})^{\alpha-1}e^{-\beta (\frac{y}{c})}\frac{1}{c}\\
=&\frac{(\frac{\beta}{c})^\alpha}{\Gamma(\alpha)}y^{\alpha-1}e^{-(\frac{\beta}{c}) y}\\
\end{aligned}
$$

Then we have $Y\sim \text{ Gamma }(y|\alpha,\frac{\beta}{c})$

> $\{X_i\sim \text{Gamma}(x_i|\alpha_i,\beta),i\in[1,n],i\in\Z\}\vdash \{\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)\}$

Set $Z=\Sigma _{i=1}^{n}X_i$​

Proof One:
$$
\begin{aligned}
F_Z(z)
&=P(Z\leq z)\\
&=P(\Sigma _{i=1}^{n}X_i\leq z)\\
&=\int\int\int...\int f(x_n)\cdot f(x_{n-1})\cdot f(x_{n-2})... f(x_2)\cdot f(x_1)dx_ndx_{n-1}...dx_2dx_1\\
\end{aligned}
$$
You can see that in this kind of situation, proof by the probability distribution function is too complex, which is not a good choice.
Proof Two:

What we already have is $M_X(t)=E(e^{tX})$ as the moment generating function.

Then we can see that 
$$
\begin{aligned}
M_{(\Sigma_{i=1}^{n} X_i)}(t)
&=E(e^{t(\Sigma_{i=1}^{n} X_i)})\\
&=\prod_{i=1} ^n E(e^{tX_i})\\
&=\prod_{i=1} ^n (\frac{\beta}{\beta-t})^{\alpha_i}\\
&=(\frac{\beta}{\beta-t})^{\sum_{i=1}^n\alpha}\\
\end{aligned}
$$
According to the moment generating function we can see that $\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)$​.

> $\{X_i\sim \text{Exponential}(\beta),i\in[1,n],i\in\Z\}\vdash \{\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|n,\beta)\}$​

We have already proved two theorems:

1. $\{X\sim \text{Gamma}(x|\alpha,\beta),\alpha =1\}\vdash \{X\sim \text{Exponential}(\beta)\}$
2. $\{X_i\sim \text{Gamma}(x_i|\alpha_i,\beta),i\in[1,n],i\in\Z\}\vdash \{\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)\}$

Then according to the two theorems above:
$$
\begin{aligned}
&1.~~~~~X_i\sim \text{Exponential}(\beta)~~~~~~~~~~~~~~~~~~~~&Premise\\
&2.~~~~~X_i\sim \text{Exponential}(\beta)\rightarrow X_i\sim \text{Gamma}(x_i|1,\beta)~~~~~~~~~~~~~~~~~~~~&Premise\\
&3.~~~~~X_i\sim \text{Gamma}(x_i|\alpha_i,\beta)\rightarrow \Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)~~~~~~~~~~~~~~~~~~~~&Premise\\
&4.~~~~~X_i\sim \text{Gamma}(x_i|1,\beta)~~~~~~~~~~~~~~~~~~~~&\rightarrow e:1,2\\
&5.~~~~~\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|n,\beta)~~~~~~~~~~~~~~~~~~~~&\rightarrow e:4,3\\
\end{aligned}
$$
So we proved that $\{X_i\sim \text{Exponential}(\beta),i\in[1,n],i\in\Z\}\vdash \{\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|n,\beta)\}$.

###### Moment Generating Function

> $\{X\sim \text{Gamma}(x|\alpha,\beta),t<\beta\}\vdash \{M_X(t)=(\frac{\beta}{\beta-t})^\alpha\}$​

$$
\begin{aligned}
M_X(t)
=&E(e^{tX})\\
=&\int_{-\infty}^{\infty}e^{tx}\cdot f(x)dx\\
=&\int_{0}^{\infty}e^{tx}\cdot \frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}dx\\
=&\frac{\beta^\alpha}{\Gamma(\alpha)}\int_{0}^{\infty} x^{\alpha-1}e^{-(\beta-t) x}dx\\
=&\frac{\beta^\alpha}{\Gamma(\alpha)\cdot(\beta-t)^{\alpha}}\int_{0}^{\infty} ((\beta-t)x)^{\alpha-1}e^{-(\beta-t) x}d((\beta-t) x)\\
=&\frac{\beta^\alpha}{\Gamma(\alpha)\cdot(\beta-t)^{\alpha}}\int_{0}^{\infty} x^{\alpha-1}e^{-x}dx\\
=&\frac{\Gamma (\alpha)\beta^\alpha}{\Gamma(\alpha)\cdot(\beta-t)^{\alpha}}\\
=&(\frac{\beta}{\beta-t})^\alpha
\end{aligned}
$$

##### Chi Square Distribution

###### Basic Concept

**Probability Distribution Function**
$$
X\sim \chi^2(v)=\text{Gamma}(\frac{v}{2},\frac{1}{2}),v>0
$$

$$
\chi^2(x|v)=\frac{2^{-\frac{v}{2}}}{\Gamma(\frac{v}{2})}x^{\frac{v}{2}-1}e^{-\frac{x}{2}}, x\in(0,\infty)
$$

> *Examine Validity of Probability Distribution Function*

It is just a special version of the gamma distribution, so that we will not prove it again here.

> Expectation

$$
E(X)=\frac{\alpha}{\beta}==\frac{\frac{v}{2}}{\frac{1}{2}}=v
$$

> Variance

$$
D(X)=\frac{\alpha}{\beta^2}=\frac{\frac{v}{2}}{(\frac{1}{2})^2}=2v
$$

###### Mathematical Operation

> $\{X\sim \text{N}(0,1)\}\vdash \{Y=X^2\sim \chi^2(1)\}$

$$
\begin{aligned}
F_Y(y)
&=P(Y\leq y)\\
&=P(X^2\leq y)\\
&=P(-\sqrt{y}\leq X\leq \sqrt{y})\\
&=F_X(\sqrt{y})-F_X(-\sqrt{y})\\
\end{aligned}
$$

$$
\begin{aligned}
f_Y(y)
&=\frac{d}{dy}F_Y(y)\\
&=\frac{d}{dy}(F_X(\sqrt{y})-F_X(-\sqrt{y}))\\
&=f_X(\sqrt{y})\cdot \frac{d}{dy}(\sqrt{y})-f_X(-\sqrt{y})\cdot \frac{d}{dy}(-\sqrt{y})\\
&=\frac{1}{\sqrt{2\pi}}e^{-\frac{y}{2}}\cdot\frac{1}{2\sqrt{y}}+\frac{1}{\sqrt{2\pi}}e^{-\frac{y}{2}}\cdot\frac{1}{2\sqrt{y}}\\
&=\frac{1}{\sqrt{2\pi y}}e^{-\frac{y}{2}}\\
&=\frac{2^{-\frac{1}{2}}}{\Gamma(\frac{1}{2})}y^{\frac{1}{2}-1}e^{-\frac{y}{2}}\\
\end{aligned}
$$

So we get $\{X\sim \text{N}(0,1)\}\vdash \{Y=X^2\sim \chi^2(1)\}$.

> $\{X_i\sim \chi^2(v_i)\}\vdash \{\sum_{i=1}^nX_i\sim\chi^2(\sum_{i=1}^nv_i)\}$

We have two basic knowledge:

1. $\{X_i\sim \text{Gamma}(x_i|\alpha_i,\beta),i\in[1,n],i\in\Z\}\vdash \{\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)\}$
2. $X\sim \chi^2(v)=\text{Gamma}(\frac{v}{2},\frac{1}{2}),v>0$

We can prove the new theorem based on the theorems above.
$$
\begin{aligned}
&1.~~~~~X_i\sim \chi^2(v_i)~~~~~~~~~~~~~~~~~~~~&Premise\\
&2.~~~~~X_i\sim \chi^2(v_i)\rightarrow X_i\sim \text{Gamma}(\frac{v_i}{2},\frac{1}{2}),v>0~~~~~~~~~~~~~~~~~~~~&Theorem\\
&3.~~~~~X_i\sim \text{Gamma}(x_i|\alpha_i,\beta)\rightarrow  \Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\Sigma _{i=1}^{n}\alpha_i,\beta)~~~~~~~~~~~~~~~~~~~~&Theorem\\
&4.~~~~~X_i\sim \text{Gamma}(\frac{v_i}{2},\frac{1}{2}),v>0~~~~~~~~~~~~~~~~~~~~&\rightarrow e:1,2\\
&5.~~~~~\Sigma _{i=1}^{n}X_i\sim \text{Gamma}(\Sigma _{i=1}^{n}x_i|\frac{\Sigma _{i=1}^{n}v_i}{2},\frac{1}{2})~~~~~~~~~~~~~~~~~~~~&\rightarrow e:4,3\\
&6.~~~~~\sum_{i=1}^nX_i\sim\chi^2(\sum_{i=1}^nv_i)~~~~~~~~~~~~~~~~~~~~&Theorem:2\\
\end{aligned}
$$

###### Detailed Data

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240610121844457.png" alt="image-20240610121844457" style="zoom:33%;" />