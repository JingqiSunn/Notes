#### The Beta Function

###### Derive the Beta Function

$$
\begin{aligned}
\Gamma (x)\Gamma(y)
=&\int_0^{\infty}t^{x-1}e^{-t}dt\cdot\int_0^{\infty}s^{y-1}e^{-s}ds\\
=&\int_0^{\infty}\int_0^{\infty}t^{x-1}e^{-t}s^{y-1}e^{-s}dtds\\
=&\int_0^{\infty}\int_0^{\infty}t^{x-1}s^{y-1}e^{-(t+s)}dtds\\
\text{Substitution : }& t+s=\omega=\omega(1-\tau+\tau)=\omega(1-\tau)+\omega\tau\\
\text{That is }&t=\omega(1-\tau),s=\omega\tau,\omega\in(0,\infty),\tau\in(0,1)\\
\text{The Jacobi matrix determinant is : }&\det\begin{bmatrix}1-\tau&-\omega\\\tau&\omega\end{bmatrix}=\omega\\
=&\int_0^{\infty}\int_0^{1}({\omega(1-\tau)})^{x-1}(\omega\tau)^{y-1}e^{-\omega}\omega d\tau d\omega\\
=&\int_0^{\infty}\int_0^{1}\omega^{x-1}\omega^{y-1}(1-\tau)^{x-1}\tau^{y-1}e^{-\omega}\omega d\tau d\omega\\
=&\int_0^{\infty}\omega ^{x+y-1}e^{-\omega}d\omega\cdot\int_0^{1}(1-\tau)^{x-1}\tau^{y-1}d\tau\\
=&\Gamma(x+y)\cdot\int_0^{1}(1-\tau)^{x-1}\tau^{y-1}d\tau\\
\end{aligned}
$$

So we got a proper expression of the Beta Function is $\int_0^{1}(1-\tau)^{x-1}\tau^{y-1}d\tau$, which is equal to $\frac{\Gamma (x)\cdot\Gamma(y)}{\Gamma (x+y)}$

###### Basic Concept

**The Beta Function**
$$
B(a,b)=\frac{\Gamma(a)\cdot\Gamma{(b)}}{\Gamma(a+b)}=\int_0^{1}(1-\tau)^{a-1}\tau^{b-1}d\tau\\
$$

###### Detailed Data

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240610152329445.png" alt="image-20240610152329445" style="zoom:12%;" />

###### Other Resources

https://www.youtube.com/watch?v=bYS64NrR9vQ&amp;ab_channel=FlammableMaths

