#### Normal Distribution

##### Univariate Normal Distribution

###### Basic Concept

**Probability Distribution Function**
$$
N(x|\mu,\sigma^2)=\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$
> *Examine Validity of Probability Distribution Function*

1. $f(x)\geq 0$​
   $$
   \forall x\in \R,\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}\geq 0
   $$

2. $\int_{-\infin}^{\infin}f(x)d(x)=1$​
   $$
   \begin{aligned}
   \int_{-\infin}^{\infin}f(x)d(x)
   =&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
   =&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx\\
   =&\sqrt{(\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx)\cdot(\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx)}\\
   =&\sqrt{(\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx)\cdot(\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{y^2}{2\sigma^2}}dy)}\\
   =&\sqrt{(\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}(\frac{1}{\sqrt{2\pi}\sigma})^2\cdot e^{-\frac{x^2}{2\sigma^2}}\cdot e^{-\frac{y^2}{2\sigma^2}}dxdy)}\\
   =&\sqrt{(\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}\frac{1}{2\pi\sigma^2}\cdot e^{-\frac{x^2+y^2}{2\sigma^2}}dxdy)}\\
   =&\sqrt{(\int_{0}^{2\pi}\int_{0}^{\infty}\frac{1}{2\pi\sigma^2}\cdot e^{-\frac{r^2}{2\sigma^2}}rdrd\theta)}\\
   =&\sqrt{(\int_{0}^{2\pi}\int_{0}^{\infty}\frac{1}{4\pi\sigma^2}\cdot e^{-\frac{r^2}{2\sigma^2}}dr^2d\theta)}\\
   =&\sqrt{(\int_{0}^{2\pi}\int_{0}^{\infty}\frac{1}{4\pi\sigma^2}\cdot e^{-\frac{x}{2\sigma^2}}dxd\theta)}\\
   =&\sqrt{(\int_{0}^{2\pi}(-\frac{1}{2\pi}e^{-\frac{x}{2\sigma^2}})\Bigg|_{0}^{\infty}d\theta)}\\
   =&\sqrt{(\int_{0}^{2\pi}\frac{1}{2\pi}\theta)}\\
   =&1\\
   \end{aligned}
   $$

> *Expectation*

$$
\begin{aligned}
E(x)
=&\int_{-\infin}^{\infin}xf(x)d(x)\\
=&\int_{-\infty}^{\infty}\frac{x}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}\frac{x-\mu}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx+\int_{-\infty}^{\infty}\frac{\mu}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\mu+\int_{-\infty}^{\infty}\frac{x-\mu}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\mu+\int_{-\infty}^{\infty}\frac{x}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx\\
=&\mu
\end{aligned}
$$
> *Variance*

$$
\begin{aligned}
D(x)
=&E(x-E(x))^2\\
=&\int_{-\infin}^{\infin}(x-E(x))^2f(x)dx\\
=&\int_{-\infin}^{\infin}(x-\mu)^2f(x)dx\\
=&\int_{-\infin}^{\infin}(x-\mu)^2\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\int_{-\infin}^{\infin}(x-\mu)^2\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}d(x-\mu)\\
=&\int_{-\infin}^{\infin}x^2\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx\\
=&\frac{1}{\sqrt{2\pi}\sigma}\int_{-\infin}^{\infin}x^2e^{-\frac{x^2}{2\sigma^2}}dx\\
=&\frac{1}{\sqrt{2\pi}\sigma}\int_{-\infin}^{\infin}x^2\frac{-\sigma^2}{x}de^{-\frac{x^2}{2\sigma^2}}\\
=&\frac{1}{\sqrt{2\pi}\sigma}\int_{-\infin}^{\infin}-\sigma^2xde^{-\frac{x^2}{2\sigma^2}}\\
=&\frac{1}{\sqrt{2\pi}\sigma}(-\sigma^2xe^{-\frac{x^2}{2\sigma^2}}\Bigg|_{-\infty}^{\infty}+\int_{-\infty}^{\infty}e^{-\frac{x^2}{2\sigma^2}}\cdot\sigma^2dx)\\
=&\frac{1}{\sqrt{2\pi}\sigma}\int_{-\infty}^{\infty}e^{-\frac{x^2}{2\sigma^2}}\cdot\sigma^2dx\\
=&\frac{\sigma}{\sqrt{2\pi}}\int_{-\infty}^{\infty}e^{-\frac{x^2}{2\sigma^2}}dx\\
=&\frac{\sigma}{\sqrt{2\pi}}\sqrt{2\pi}\sigma\\
=&\sigma^2
\end{aligned}
$$

###### Mathematical Operation

> $\{X\sim N(0,1),r\in\N\}\vdash E(X^{2r+1})=0$

$$
\begin{aligned}
E(X^{2r+1})
=&\int_{-\infty}^{\infty}x^{2r+1}f(x)dx\\
=&\int_{-\infty}^{\infty}x^{2r+1}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}x^{2r+1}\frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}dx\\
=&0
\end{aligned}
$$

> $\{X\sim N(0,1),r\in\N\}\vdash E(X^{2r})=\frac{2r!}{2^rr!}$​

$$
\begin{aligned}
E(X^{2r+1})
=&\int_{-\infty}^{\infty}x^{2r}f(x)dx\\
=&\int_{-\infty}^{\infty}x^{2r}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}x^{2r}\frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}dx\\
\end{aligned}
$$

> $\{X\sim N(\mu,\sigma^2)\}\vdash (a+bX)\sim N(a+b\mu,b^2\sigma^2)$​

Set $Z=a+bX$
$$
\begin{aligned}
F_Z(z)
=&P(Z<z)\\
=&P(a+bX<z)\\
=&P(X<\frac{z-a}{b})\\
=&F_X(\frac{z-a}{b})
\end{aligned}
$$

$$
\begin{aligned}
f_Z(z)
=&\frac{d}{dz}(F_X(\frac{z-a}{b}))\\
=&f_X(\frac{z-a}{b})\cdot|\frac {dx}{dz}|\\
=&\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(\frac{z-a}{b}-\mu)^2}{2\sigma^2}}\cdot\frac{1}{|b|}\\
=&\frac{1}{\sqrt{2\pi}|b|\sigma}e^{-\frac{(z-a-b\mu)^2}{2b^2\sigma^2}}\\
\end{aligned}
$$

$$
Z\sim N(a+b\mu,b^2\sigma^2)
$$

> $\{X\sim N(\mu,\sigma^2)\}\vdash \frac{X-\mu}{\sigma}\sim N(0,1)$

We have already proved that $\{X\sim N(\mu,\sigma^2)\}\vdash (a+bX)\sim N(a+b\mu,b^2\sigma^2)$

When $a=-\frac{\mu}{\sigma},b=\frac{1}{\sigma}$, $(a+bX)\sim N(0,1)$​

###### Moment Generating Function

> $\{X\sim N(\mu,\sigma^2)\}\vdash \{M_X(t)=e^{\mu t+0.5\sigma^2 t^2}\}$

$$
\begin{aligned}
M_X(t)
=&E(e^{tX})\\
=&\int_{-\infty}^{\infty}e^{tx}f(x)dx\\
=&\int_{-\infty}^{\infty}e^{tx}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2-2\mu x+\mu^2-2t\sigma^2x}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2-(2\mu+2t\sigma^2) x+\mu^2}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-(\mu+t\sigma^2))^2-(2t\mu\sigma^2+t^2\sigma^4)}{2\sigma^2}}dx\\
=&\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-(\mu+t\sigma^2))^2}{2\sigma^2}+\frac{2t\mu\sigma^2+t^2\sigma^4}{2\sigma^2}}dx\\
=&e^{\frac{2t\mu\sigma^2+t^2\sigma^4}{2\sigma^2}}\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-(\mu+t\sigma^2))^2}{2\sigma^2}}dx\\
=&e^{\frac{2t\mu\sigma^2+t^2\sigma^4}{2\sigma^2}}\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(x-(\mu+t\sigma^2))^2}{2\sigma^2}}d(x-(\mu+t\sigma^2))\\
=&e^{\frac{2t\mu\sigma^2+t^2\sigma^4}{2\sigma^2}}\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{x^2}{2\sigma^2}}dx\\
=&e^{\frac{2t\mu\sigma^2+t^2\sigma^4}{2\sigma^2}}\\
=&e^{t\mu+0.5t^2\sigma^2}\\
\end{aligned}
$$

###### Detailed Data

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240608102731426.png" alt="image-20240608102731426" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240609085540858.png" alt="image-20240609085540858" style="zoom:33%;" />