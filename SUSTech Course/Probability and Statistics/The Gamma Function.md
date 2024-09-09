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

**Visualization**

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 0

<img src="T:\Notes\Photo\2.jpg" alt="2" style="zoom:25%;" />

> [!NOTE]
>
> You can notice that the value of the Gamma Function has a huge jump around an integer 0

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 1

<img src="T:\Notes\Photo\1.jpg" alt="1" style="zoom:25%;" />

> [!NOTE]
>
> You can notice that the value of the Gamma Function at $\alpha = 1$ and $2$​ are very similar, actually they are the same

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 2

<img src="T:\Notes\Photo\3.jpg" alt="3" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 3

<img src="T:\Notes\Photo\4.jpg" alt="4" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 4

<img src="T:\Notes\Photo\5.jpg" alt="5" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$​ is near 5

<img src="T:\Notes\Photo\6.jpg" alt="6" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$​ is near 6

<img src="T:\Notes\Photo\7.jpg" alt="7" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$​ is near 7

<img src="T:\Notes\Photo\8.jpg" alt="8" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 8

<img src="T:\Notes\Photo\9.jpg" alt="9" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is near 9

<img src="T:\Notes\Photo\10.jpg" alt="10" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$​ is near 10

<img src="T:\Notes\Photo\11.jpg" alt="11" style="zoom:25%;" />

> $\Gamma(\alpha)=\int_0^{\infty}x^{\alpha -1}e^{-x}dx$, when $\alpha$ is in the interval of $(0,\infty)$

<img src="T:\Notes\Photo\12.jpg" alt="12" style="zoom:22%;" />

> [!NOTE]
>
> You can notice that the graph of the Gamma Function concaves up, which lead us to the derivative of the Gamma Function.

$$
\begin{aligned}
\frac{d}{d\alpha}\Gamma(\alpha)
=&\frac{d}{d\alpha}\int_0^{\infty}x^{\alpha -1}e^{-x}dx\\
=&\int_0^{\infty}\frac{d}{d\alpha}x^{\alpha -1}e^{-x}dx\\
=&\int_0^{\infty}(\alpha-1)x^{\alpha -2}\cdot \ln x \cdot e^{-x}dx\\
=&(\alpha-1)\int_0^{\infty}x^{\alpha -2}\cdot \ln x \cdot e^{-x}dx\\
=&(\alpha-1)\int_0^{\infty}(\ln x) \cdot (x^{\alpha -2}\cdot e^{-x}dx)\\
=&(\alpha-1)[\ln x\cdot \int x^{\alpha -2}\cdot e^{-x}dx\Bigg|_0^{\infty}- \int_0^{\infty}x^{\alpha -2}\cdot e^{-x}dx\frac{1}{x}]\\
=&(\alpha -1)\cdot \Gamma(\alpha - 1)-\int_0^{\infty}x^{\alpha -3}\cdot e^{-x}dx\\
=&(\alpha -1)\cdot \Gamma(\alpha - 1)-\Gamma(\alpha - 2)\\
=&


\end{aligned}
$$



###### Other Resources

https://www.youtube.com/watch?v=c7_F4P71E2E&amp;ab_channel=PhysicsandMathLectures

https://www.youtube.com/watch?v=nZUuHN21zH4&amp;t=29s&amp;ab_channel=BriTheMathGuy

https://en.wikipedia.org/wiki/Gamma_function











