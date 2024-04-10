#### Derivative of Functions

> [!CAUTION]
>
> I will not show the details for $f(x)$ here.

##### The Derivative of $f(x,y)$

> *Definition:*
> $$
> f_x(x,y)=\frac{\part}{\part x}f(x,y)\\
> f_y(x,y)=\frac{\part}{\part y}f(x,y)\\
> $$
> *Proof:*
>
> > [!NOTE]
> >
> > There is no need to prove it, which is just the same method of finding the derivative of $f(x)$.

##### The Derivative of $f(x(t),y(t))$

> *Conclusion:*
>
> $x(t_0)=x_0$, $y(t_0)=y_0$, $f(x,y)$ is differentiable at $(x_0,y_0)$, $x(t),y(t)$ are differentiable at $t_0$,
>
> Then we will have $f(x(t),y(t))$ is differentiable at $t=t_0$, and the derivative is 
> $$
> \frac{df(x(t),y(t))}{d(t)}=f_x(x(t),y(t))\cdot x'(t)+f_y(x(t),y(t))\cdot y'(t)=\frac{\part f}{\part x}\cdot \frac{dx}{dt}+\frac{\part f}{\part y}\cdot \frac{dy}{dt}
> $$
> *Proof:*
>
> Suppose the function is differentiable at $t=t_0$,
> $$
> \begin{aligned}
> \frac{df(x(t),y(t))}{dt}\Bigg|_{t=t_0}
> =&\lim_{\Delta t\rightarrow 0}\frac{f(x(t_0+\Delta t),y(t_0+\Delta t))-f(x(t_0),y(t_0))}{\Delta t}\\
> =&\lim_{\Delta t\rightarrow 0}\frac{f_x(x(t_0),y(t_0))\Delta x+f_y(x(t_0),y(t_0))\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y}{\Delta t}\\
> =&f_x(x(t),y(t))\cdot x'(t)+f_y(x(t),y(t))\cdot y'(t)\\
> =&\frac{\part f}{\part x}\cdot \frac{dx}{dt}+\frac{\part f}{\part y}\cdot \frac{dy}{dt}
> \end{aligned}
> $$