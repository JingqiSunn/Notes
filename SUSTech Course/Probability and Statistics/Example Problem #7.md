#### Example Problem #7

> $X$~$N(\mu,\sigma^2)$, $Y=aX+b$, $a\neq 0$.
>
> Ask the distribution for $Y$.

*Solution:*
$$
X=g(Y)=\frac{Y-b}{a}
$$

$$
f_X(x)=\frac{1}{\sqrt{2\pi}\sigma}\cdot e^\frac{-(x-\mu)^2}{2\sigma^2}
$$


$$
\begin{aligned}
F_Y(y)=&P(Y\le y)\\
=&P(aX+b\le y)\\
=&P(X\le \frac{y-b}{a})\\
=&F_X(\frac{y-b}{a})
\end{aligned}
$$

$$
\begin{aligned}
f_Y(y)=&\frac{d}{dy}(F_Y(y))\\
=&\frac{d}{dy}F_X(\frac{y-b}{a})\\
=&|(\frac{y-b}{a})'|f_X(\frac{y-b}{a})\\
=&|\frac{1}{a}|\cdot \frac{1}{\sqrt{2\pi}\sigma}\cdot e^\frac{-(\frac{y-b}{a}-\mu)^2}{2\sigma^2}\\
=&\frac{1}{\sqrt{2\pi}|a|\sigma}\cdot e^\frac{-(y-(a\mu+b))^2}{2(|a|\sigma)^2}\\
\end{aligned}
$$

So we have $Y$~$N(a\mu+b,(|a|\sigma)^2)$

