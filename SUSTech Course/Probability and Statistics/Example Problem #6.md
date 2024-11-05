#### Example Problem #6

> $X$~$Geo(p)$, $Y$~$Geo(p)$.
>
> Ask $P(X=Y)$.

*Solution:*
$$
f_{XY}(x,y)=(1-p)^{x-1}p(1-p)^{y-1}p
$$

$$
f_{XY}(x=y=k)=(1-p)^{2k-2}p^2
$$

$$
\begin{aligned}
P(X=Y)=&\sum_{k=1}^\infty f_{XY}(x=y=k)\\
=&\sum_{k=1}^\infty (1-p)^{2k-2}p^2\\
=&p^2\frac{1}{1-(1-p)^2}\\
=&\frac{p^2}{-p^2+2p}\\
=&\frac{p}{-p+2}
\end{aligned}
$$

