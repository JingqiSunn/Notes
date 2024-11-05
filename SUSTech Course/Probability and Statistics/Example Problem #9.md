### Example Problem #7

> $X_1,X_2,...,X_{10}$~$\pi(0.2)$.
>
> Ask $P(\sum_{k=1}^{10}X_k\ge 2)$

*Solution:*
$$
f_{X_i}(x=k)=\frac{\lambda^k}{k!}e^{-\lambda }
$$
I will prove another thing first.

> *Definition:*
>
> $Y$~$\pi(\lambda_1)$, $Z$~$\pi(\lambda_2)$,
>
> Then $(Y+Z)$~$\pi(\lambda_1+\lambda_2)$.
>
> *Proof:*
> $$
> \begin{aligned}
> P(Y+Z=n)=&\sum_{k=0}^{n}P(Y=k)\cdot P(Z=n-k)\\
> =&\sum_{k=0}^{n}\frac{\lambda_1^k}{k!}e^{-\lambda_1}\cdot \frac{\lambda_2^{n-k}}{(n-k)!}e^{-\lambda_2}\\
> =&e^{-\lambda_1-\lambda_2}\sum_{k=0}^{n}\frac{\lambda_1^k\cdot \lambda_2^{n-k}}{k!\cdot (n-k)!}\\
> =&\frac{e^{-\lambda_1-\lambda_2}}{n!}\sum_{k=0}^{n}\frac{n!}{k!\cdot (n-k)!}\cdot \lambda_1^k\cdot \lambda_2^{n-k}\\
> =&\frac{(\lambda_1+\lambda_2)^n}{n!}\cdot e^{-\lambda_1-\lambda_2}
> \end{aligned}
> $$

So in this question, $\sum_{k=1}^{10}X_k$~$\pi(2)$
$$
\begin{aligned}
&P(\sum_{k=1}^{10}X_k\ge 2)\\
=&1-P(\sum_{k=1}^{10}X_k< 2)\\
=&1-\sum_{x=0}^{1}\frac{2^{x}}{x!}e^{-2}\\
=&1-\frac{1}{e^2}-\frac{2}{e^{2}}\\
=&1-\frac{3}{e^2}
\end{aligned}
$$
