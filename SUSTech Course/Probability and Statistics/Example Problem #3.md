#### Example Problem #3

> $X$~$N(\mu,\sigma_1^2)$, $Y$~$N(2\mu,\sigma_2^2)$, and they are independent, $P(X-Y\ge 1)=\frac{1}{2}$
>
> Ask the value of $\mu$.

*Solution:*
$$
\begin{aligned}
P(X-Y\ge 1)=&\int_{-\infty}^{\infty}\int_{1+Y}^{\infty}f_X(x)\cdot f_Y(y)dxdy\\
=&\int_{-\infty}^{\infty}\int_{1+Y}^{\infty}\frac{1}{\sqrt{2\pi}\sigma_1}e^\frac{-(x-\mu)^2}{2\sigma_1^2} \frac{1}{\sqrt{2\pi}\sigma_2}e^\frac{-(y-2\mu)^2}{2\sigma_2^2} dxdy\\
=&
\end{aligned}
$$
I will just stop here, because I don't have the ability to finish this proof, but I can offer a conclusion.

> Given $X$~$N(\mu_1,\sigma_1^2)$, $Y$~$N(\mu_2,\sigma_2^2)$.
>
> $(aX+bY)$~$N(a\mu_1+b\mu_2,a^2\sigma_1^2+b^2\sigma_2^2)$

Then in this question we will find that $(X-Y)$~$(-\mu,\sigma_1^2+\sigma_2^2)$.

So we have 
$$
\mu = -1
$$
