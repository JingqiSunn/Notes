#### Multi-Variable Function

##### Limit

###### Definition

> $$
> \frac{((\forall \epsilon >0)\and( \exist \delta>0))\rightarrow((0<\sqrt{(x-x_0)^2+(y-y_0)^2}<\delta)\rightarrow(|f(x,y)-L|<\epsilon)) }{\lim_{(x,y)\rightarrow(x_0.y_0)f(x,y)}=L}
> $$
>
> *Example*
>
> > Find $\lim_{(x,y)\rightarrow(0,0)}\frac{4xy^2}{x^2+y^2}$
>
> ***Solution#1: By Definition***
>
> *Step#1: Guess out the value of the limit.*
>
> We can see that the power of the numerator is 3 while the power of denominator is 2, considering the limit is when x, y are all approaching to zero, so I can guess that the limit is 0.
>
> *Step#2: Find the expression of $\delta$ with the help of $\epsilon$.*
>
> Now we have already assume that the value of the limitation is 0.
> $$
> \begin{aligned}
> |f(x,y)-L|=&|\frac{4xy^2}{x^2+y^2}-0|\\
> =&\frac{4|x|y^2}{x^2+y^2}\\
> \leq&4|x|\\
> \leq&4\sqrt{x^2+y^2}\\
> =&4\delta\\
> \leq&\epsilon
> \end{aligned}
> $$
> So what we need now is to let 
> $$
> 4\delta\leq\epsilon
> $$
>
> $$
> \delta\leq\frac{\epsilon}{4}
> $$
>
> To make it more convenient I want to choose $\delta$ to be $\frac{\epsilon}{4}$.
>
> *Step#3: Write the proof in the sequence of the definition.*
> $$
> \forall\epsilon>0,\exist\delta=\frac{\epsilon}{4}>0
> $$
> Whenever 
> $$
> 0\leq\sqrt{(x-0)^2+(y-0)^2}\leq\delta=\frac{\epsilon}{4}
> $$
>
> $$
> \begin{aligned}
> |f(x,y)-L|=&|\frac{4xy^2}{x^2+y^2}-0|\\
> =&\frac{4|x|y^2}{x^2+y^2}\\
> \leq&4|x|\\
> \leq&4\sqrt{x^2+y^2}\\
> \le	&4\delta\\
> \leq&\epsilon
> \end{aligned}
> $$
>
> So we prove that the limitation of $\lim_{(x,y)\rightarrow(0,0)}\frac{4xy^2}{x^2+y^2}$​ is 0.
>
> ***Solution#2: By Orientational Approach***
>
> > [!NOTE]
> >
> > Let us recall the general understanding of the limitation of the single variable function, if the limitation approaching from the  positive direction of the coordinate and the negative direction of the coordinate are all exists and the same.
> >
> > So in the two variable function if we want to prove the limitation exist, we can notice that there is no longer only one axis, there are two axis, which can construct out a plate.
> >
> > So now we just need to make sure that the limitation found out by approaching from all the direction from that plate should all exist and turn out to have the same value.
> >
> > So we can use the substitution of variables, when we can use $x=x_0+r\cos\theta$, $y=y_0+r\sin\theta$. And we can let $r\rightarrow0$, and $\theta$ should take any value which controls the direction that the approaching movement is happening.
>
> *Step#1: Variable Substitution*
> $$
> x=r\cos\theta,y=r\sin\theta
> $$
> *Step#2: Find The Limitation*
> $$
> \begin{aligned}
> &\lim_{(x,y)\rightarrow(0,0)}\frac{4xy^2}{x^2+y^2}\\
> =&\lim_{r\rightarrow 0}\frac{4r\cos\theta(4r\sin\theta)^2}{r^2\cos^2\theta+r^2\sin^2\theta}\\
> =&\lim_{r\rightarrow 0}\frac{64r^3\sin^2\theta\cos\theta}{r^2}\\
> =&0
> \end{aligned}
> $$
> So we prove that the limitation of $\lim_{(x,y)\rightarrow(0,0)}\frac{4xy^2}{x^2+y^2}$​ is 0.
>
> *Example*
>
> > Prove $\lim_{(x,y)\rightarrow(0,0)}\frac{y}{x}$​ doesn't exist.
>
> ***Solution***
>
> *Step#1: Variable Substitution One*
> $$
> x=m,y=2m
> $$
> *Step#2: Find The Limitation One*
> $$
> \begin{aligned}
> &\lim_{(x,y)\rightarrow(0,0)}\frac{y}{x}\\
> =&\lim_{m\rightarrow 0}\frac{2m}{m}\\
> =&2
> \end{aligned}
> $$
> *Step#3: Variable Substitution Two*
> $$
> x=m,y=3m
> $$
> *Step#4: Find The Limitation Two*
> $$
> \begin{aligned}
> &\lim_{(x,y)\rightarrow(0,0)}\frac{y}{x}\\
> =&\lim_{m\rightarrow 0}\frac{3m}{m}\\
> =&3
> \end{aligned}
> $$
> *Step#5: Comparation*
> $$
> 2\neq 3
> $$
> So we prove that $\lim_{(x,y)\rightarrow(0,0)}\frac{y}{x}$ doesn't exist.

##### Continuity

###### Definition

> $$
> \frac{(f(x,y)\text{ is defined at }(x_0,y_0))\and(\lim_{(x,y)\rightarrow (x_0,y_0)}f(x,y)\text{ exists})\and(\lim_{(x,y)\rightarrow (x_0,y_0)}f(x,y)=f(x_0,y_0))}{f(x,y)\text{ is continuous at }(x_0,y_0)}
> $$
>
> > [!NOTE]
> >
> > Basically you can use this definition to check nearly all the continuity problems in multi-variables problem, but maybe in the future there may exists more easier way.

##### Derivative

> [!CAUTION]
>
> I will make the example by two variable function.
>
> But there is something different from the mono variable function, because we need to introduce the definition of partial derivative here.

###### Definition

> $$
> \frac{\partial f(x,y)}{\partial x}\Bigg|_{(x_0,y_0)}=\frac{f(x,y_0)}{dx}\Bigg|_{x=x_0}=\lim_{h\rightarrow 0}\frac{f(x_0+h,y_0)-f(x_0,y_0)}{h}
> $$
>
> $$
> \frac{\partial f(x,y)}{\partial y}\Bigg|_{(x_0,y_0)}=\frac{f(x_0,y)}{dy}\Bigg|_{y=y_0}=\lim_{h\rightarrow 0}\frac{f(x_0,y_0+h)-f(x_0,y_0)}{h}
> $$

##### Differentiability

###### Definition

> **Mono Variable Function**
> $$
> \frac{\lim_{x\rightarrow x_0}\frac{f(x_0)-f(x)}{x_0-x}=\lim_{\Delta x\rightarrow 0 }\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=f'(x_0)}{f(x)\text{ is differentiable at }x_0}
> $$
>
> > [!NOTE]
> >
> > Actually we can see that we can not find the information about partial derivative in this version of definition, which means it can not be directly used in the two variable function.
>
> *Corollary:*
>
> 1. $$
>    \lim_{\Delta x\rightarrow 0 }\varepsilon(\Delta x)=0\\
>    $$
>
> 2. $$
>    f(x_0+\Delta x)-f(x_0)=f'(x_0)\Delta x+\varepsilon(\Delta x)\Delta x\\
>    $$
>
> *Proof of the Corollary:*
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
> So we prove the corollary.
>
> **Two Variable Function**
>
> > [!NOTE]
> >
> > We can not directly use the definition of the mono variable derivativity on the two variable function but we can still use the corollary of it.
>
> 1. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_1(\Delta x,\Delta y)=0
>    $$
>
> 2. $$
>    \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_2(\Delta x,\Delta y)=0
>    $$
>
> 3. $$
>    f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0)=f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y
>    $$

##### Differentiability Implies Continuity

> [!NOTE]
>
> I will use the example of two variable function.

We know the differentiability of $f(x,y)$ at $(x_0,y_0)$, which means that we can use the definition of differentiability.

1. $$
   \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_1(\Delta x,\Delta y)=0
   $$

2. $$
   \lim_{(\Delta x,\Delta y)\rightarrow(0,0)}\varepsilon_2(\Delta x,\Delta y)=0
   $$

3. $$
   f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0)=f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y+\varepsilon_1(\Delta x,\Delta y)\Delta x+\varepsilon_2(\Delta x,\Delta y)\Delta y
   $$

So we have 
$$
\lim_{(\Delta x,\Delta y)\rightarrow (0,0)}(f(x_0+\Delta x，y_0+\Delta y)-f(x_0,y_0))=0
$$
According to the definition of continuity, we proved the continuity.

##### Continuous of Partial Derivative Implies Continuity

> [!WARNING]
>
> Here are some conclusions that we can use them directly, but I did not give out the proof here.

> ###### The Mixed Derivative Theorem
>
> $$
> \frac{f,f_x,f_y,f_{xy},f_{yx}\text{ are all continuous at (a,b)}}{f_{xy}(a,b)=f_{yx}(a,b)}
> $$
>
> ###### Corollary of Theorem 3
>
> $$
> \frac{f_x,f_y,f\text{ are continuous throughout an open region }R}{f \text{ is differentiable at every point of } R}
> $$

##### Chain Rule

> *Definition:*
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
>
> > [!NOTE]
> >
> > The result for higher dimensional situation is the same.

##### The Partial derivative of Implicit Function

> *Definition:*
> $$
> \frac{F(x,y)=0}{\frac{\partial x}{\partial y}=-\frac{F_y}{F_x}}
> $$
> *Proof:*
> $$
> F(x,y)=0
> $$
> If we take the partial derivative of the variable  $y$ on both side of the equation than we will have 
> $$
> F_x(x,y)\frac{\partial x}{\partial y}+F_y(x,y)\frac{\partial y}{\partial y}=\frac{\partial}{\partial y}0=0
> $$
>
> $$
> \frac{\partial x}{\partial y}=-\frac{F_y}{F_x}
> $$
>
> > [!NOTE]
> >
> > The formula for the higher dimensional situation are basically in the same as the two variable function.

##### Gradient Vector

> *Definition:*
> $$
> \frac{F(x,y)\text{ is partially differntiable at }(a,b) }{\nabla F=\begin{bmatrix}F_x(a,b)\\F_y(a,b)\end{bmatrix}}
> $$
> *Meaning:*
>
> It describe the two partial derivative's behavior around a particular point.

##### Directional Derivative



##### Other resources