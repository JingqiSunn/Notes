#### Example Problem #8

> $f(x,y)=Ce^{-3y}$, $0<x<y$.
>
> Ask the value of $C$, whether independent.

$$
\begin{aligned}
&\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}f(x,y)dxdy\\
=&\int_{0}^{\infty}\int_{0}^{y}f(x,y)dxdy\\
=&\int_{0}^{\infty}\int_{0}^{y}Ce^{-3y}dxdy\\
=&\int_{0}^{\infty}Cye^{-3y}dy\\
=&\frac{C}{9}
\end{aligned}
$$

$$
\frac{C}{9}=1\\
C=9
$$

$$
f(x,y)=9e^{-3y},0<x<y
$$

$$
\begin{aligned}
f_X(x)=&\int_{-\infty}^{\infty}f(x,y)dy\\
=&\int_{x}^{\infty}f(x,y)dy\\
=&\int_{x}^{\infty}9e^{-3y}dy\\
=&3e^{-3x}
\end{aligned}
$$

$$
\begin{aligned}
f_Y(y)=&\int_{-\infty}^{\infty}f(x,y)dx\\
=&\int_{0}^{y}f(x,y)dx\\
=&\int_{0}^{y}9e^{-3y}dx\\
=&9ye^{-3y}
\end{aligned}
$$

$$
f_X(x)\cdot f_Y(y)\neq f_{XY}(x,y)
$$

So they are dependent.