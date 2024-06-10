#### The Gamma Function

###### Reason For Existence

*Factorial*
$$
n!=n(n-1)...2\cdot1,\text{ where n is a positive integer}
$$
But think about a situation when $\text{n}$ is not a positive integer, we somehow want a continuous function to describe more things containing the factorial, so that is the reason for the existence of the gamma function.

###### Basic Concept

**The Gamma Function**
$$
\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx
$$

> $\Gamma (1)=1$ 

$$
\begin{aligned}
\Gamma(1)
=&\int_0^\infty x^{1-1}e^{-x}dx\\
=&\int_0^\infty e^{-x}dx\\
=&-e^{-x}\Bigg|_{0}^{\infty}\\
=&1
\end{aligned}
$$

> [!NOTE]
>
> We can see that $\Gamma(1)=0!$ which is the basic connection between the gamma function and the factorial operation.

> $\Gamma (\alpha+1)=\alpha\Gamma(\alpha)$

$$
\begin{aligned}
\Gamma(\alpha+1)
=&\int_0^{\infty}x^{\alpha+1-1}e^{-x}dx\\
=&\int_0^{\infty}x^{\alpha}e^{-x}dx\\
=&-\int_0^{\infty}x^\alpha d(e^{-x})\\
=&-(x^\alpha e^{-x}\Bigg|_0^{\infty}-\int_0^{\infty}e^{-x}d(x^\alpha))\\
=&\int_0^{\infty}e^{-x}d(x^\alpha)\\
=&\alpha\int_0^\infty x^{\alpha-1}e^{-x}dx\\
=&\alpha\Gamma(\alpha)
\end{aligned}
$$

> [!NOTE]
>
> We can see that it is corresponding to the equation $(n+1)!=(n+1)\times n!$

> $\Gamma (\frac{1}{2})=\sqrt{\pi}$

$$
\begin{aligned}
\Gamma(\frac{1}{2})
=&\int_{0}^{\infty}x^{\frac{1}{2}-1}e^{-x}dx\\
=&\int_{0}^{\infty}x^{-\frac{1}{2}}e^{-x}dx\\
=&2\times\int_{0}^{\infty}e^{-x}d\sqrt{x}\\
=&2\times\int_{0}^{\infty}e^{-x^2}dx\\
=&\int_{-\infty}^{\infty}e^{-x^2}dx\\
=&\sqrt{\int_{-\infty}^{\infty}e^{-x^2}dx\cdot \int_{-\infty}^{\infty}e^{-x^2}dx}\\
=&\sqrt{\int_{-\infty}^{\infty}e^{-x^2}dx\cdot \int_{-\infty}^{\infty}e^{-y^2}dy}\\
=&\sqrt{\int_{-\infty}^{\infty}\int_{-\infty}^{\infty}e^{-(x^2+y^2)}dxdy}\\
=&\sqrt{\int_{0}^{2\pi}\int_{0}^{\infty}e^{-r^2}rdrd\theta}\\
=&\frac{1}{\sqrt{2}}\times\sqrt{\int_{0}^{2\pi}\int_{0}^{\infty}e^{-r^2}dr^2d\theta}\\
=&\frac{1}{\sqrt{2}}\times\sqrt{\int_{0}^{2\pi}\int_{0}^{\infty}e^{-x}dxd\theta}\\
=&\frac{1}{\sqrt{2}}\times\sqrt{\int_{0}^{2\pi}-e^{-x}\Bigg|_0^{\infty}d\theta}\\
=&\frac{1}{\sqrt{2}}\times\sqrt{2\pi}\\
=&\sqrt{\pi}
\end{aligned}
$$

###### Other Resources

https://www.youtube.com/watch?v=c7_F4P71E2E&amp;ab_channel=PhysicsandMathLectures

https://www.youtube.com/watch?v=nZUuHN21zH4&amp;t=29s&amp;ab_channel=BriTheMathGuy

