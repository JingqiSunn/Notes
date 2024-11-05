#### Example Problem #2

> Given $X$~$EXP(\lambda)$, $Y$~$EXP(\lambda)$.
>
> Ask distribution of $\min(X,Y)$.

*Solution:*

This kind of questions are always recommended to find the distribution function first.
$$
\begin{aligned}
F_{XY}(z)=&1-F_{XY}(x\ge z, y\ge z)\\
=&1-F_{XY}(x\ge z)\cdot F_{XY}(y\ge z)\\
=&1-(1-F_X(z))\cdot(1- F_Y(z))\\
=&F_X(z)+F_Y(z)-F_X(z)\cdot F_Y(z)
\end{aligned}
$$

$$
\begin{aligned}
f_{XY}(z)=&\frac{d}{dz}F_{XY}(z)\\
=&\frac{d}{dz}(F_X(z)+F_Y(z)-F_X(z)\cdot F_Y(z))\\
=&\lambda e^{-\lambda z}+\lambda e^{-\lambda z}-2\times(1-e^{-\lambda z})(\lambda e^{-\lambda z})\\
=&2\lambda e^{-2\lambda z}
\end{aligned}
$$

So we proved that the distribution of $\min(X,Y)$ is $EXP(2\lambda)$