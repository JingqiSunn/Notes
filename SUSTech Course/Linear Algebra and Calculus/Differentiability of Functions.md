#### Differentiability of $f(x)$ and $f(x,y)$

##### Differentiability of $f(x)$

> *Definition:*
>
> $f(x)$ is differentiable when $\lim_{x\rightarrow x_0}\frac{f(x_0)-f(x)}{x_0-x}=\lim_{\Delta x\rightarrow 0 }\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=f'(x_0)$, which ask the limit to exist and also we will set that limit to be the derivative of $f(x)$ around that point.
>
> *Corollary:*
> $$
> \lim_{\Delta x\rightarrow 0 }\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=f'(x_0)\\
> \lim_{\Delta x\rightarrow 0 }(\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}-f'(x_0))=0
> $$
> If we set 
> $$
> \varepsilon(\Delta x)=\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}-f'(x_0)
> $$
> Then we will have 
> $$
> \lim_{\Delta x\rightarrow 0 }\varepsilon(\Delta x)=0\\
> \frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}-f'(x_0)=\varepsilon(\Delta x)\\
> f(x_0+\Delta x)-f(x_0)-f'(x_0)\Delta x=\varepsilon(\Delta x)\Delta x\\
> f(x_0+\Delta x)-f(x_0)=f'(x_0)\Delta x+\varepsilon(\Delta x)\Delta x\\
> $$
> So the corollary is when $f(x)$ is differentiable when $x=x_0$, then we will have 
>
> 1. $$
>    \lim_{\Delta x\rightarrow 0 }\varepsilon(\Delta x)=0\\
>    $$
>
> 2. $$
>    f(x_0+\Delta x)-f(x_0)=f'(x_0)\Delta x+\varepsilon(\Delta x)\Delta x\\
>    $$
>
> > [!NOTE]
> >
> > You will find that in the field of the $f(x,y)$, we have already couldn't define the definition of the differentiability using the same definition form in the definition of which for $f(x)$, so we will just use the similar way of the corollary as above to solve this problem.

##### Differentiability of $f(x,y)$

> *Definition:*
>
> 1. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_1(\Delta x,\Delta y)\Delta x=0
>    $$
>
> 2. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_2(\Delta x,\Delta y)\Delta y=0
>    $$
>
> 3. $$
>    f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0)=f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y
>    $$

**Differentiability Means Continuity**

> *Definition:*
>
> $f(x,y)$ is differentiable at $(x_0,y_0)$,
>
> Then we have $f(x,y)$ is Continuous at $(x_0,y_0)$.
>
> *Proof:*
>
> When we have $f(x,y)$ is differentiable at $(x_0,y_0)$,
>
> Then we have some conclusions.
>
> 1. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_1(\Delta x,\Delta y)\Delta x=0
>    $$
>
> 2. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_2(\Delta x,\Delta y)\Delta y=0
>    $$
>
> 3. $$
>    f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0)=f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y
>    $$
>
> Then we will have that 
> $$
> \begin{aligned}
> &\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}(f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0))\\
> =&\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}(f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y)\\
> =&\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}f_x(x_0,y_0)\Delta x+\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}f_y(x_0,y_0)\Delta y+\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_1(\Delta x,\Delta y)\Delta x+\lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_2(\Delta x,\Delta y)\Delta y\\
> =&0+0+0+0\\
> =&0
> \end{aligned}
> $$
> So we have 
> $$
> \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}(f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0))=0
> $$
> And it proves that $f(x,y)$ now is continuous at $(x_0,y_0)$.

##### Continuity of Partial Derivative Entails the Differentiability of the Function

> *Definition:*
>
> $f_x(x,y)$ is continuous at $x_0$, $f_y(x,y)$ is continuous at $y_0$,
>
> Then we will have $f(x,y)$ is differentiable at $(x_0,y_0)$.
>
> *Proof:*
>
> It will not be offered here.