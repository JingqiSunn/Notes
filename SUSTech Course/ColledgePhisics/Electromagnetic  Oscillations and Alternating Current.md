#### Electromagnetic  Oscillations and Alternating Current

##### LC Circuit

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504181626884.png" alt="image-20240504181626884" style="zoom:50%;" />

If we set the direction of the circuit to be counterclockwise and the up polar plate is the positive side, we can find 
$$
i = \frac{dq}{dt}
$$

$$
\frac{q}{C}+L\frac{di}{dt}=0
$$

$$
q+CLq''=0
$$

Set 
$$
q=A\cos{(\omega t+\phi)}
$$

$$
A\cos{(\omega t+\phi)}-CL\omega^2A\cos{(\omega t+\phi)}=0
$$

$$
1-CL\omega^2=0
$$

$$
\omega = \frac{1}{\sqrt{CL}}
$$

We also know that 
$$
q_0=Q,i_0=0
$$

$$
q=A\cos{(\frac{1}{\sqrt{CL}} t+\phi)}
$$

$$
i=-A\frac{1}{\sqrt{CL}}\sin{(\frac{1}{\sqrt{CL}} t+\phi)}
$$

$$
A\cos{\phi}=Q,-A\frac{1}{\sqrt{CL}}\sin{\phi}=0
$$

$$
\phi = 0,A=Q
$$

$$
q=Q\cos{(\frac{1}{\sqrt{CL}} t)}
$$

###### RLC Circuit

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504184046338.png" alt="image-20240504184046338" style="zoom:50%;" />

If we set the direction of the circuit to be counterclockwise and the up polar plate is the positive side, we can find 
$$
i = \frac{dq}{dt}
$$

$$
\frac{q}{C}+\frac{dq}{dt}R+L\frac{di}{dt}=0
$$

$$
q+CRq'+LCq''=0
$$

set
$$
q=Ae^{\omega t}
$$

$$
Ae^{\omega t}+CR\omega Ae^{\omega t}+LC\omega^2Ae^{\omega t}=0
$$

$$
1+CR\omega+LC\omega^2=0
$$

$$
\omega^2+\frac{R}{L}\omega+\frac{1}{LC}=0
$$

Set
$$
\alpha = \frac{R}{2L},\omega_0=\frac{1}{\sqrt{CL}},\zeta=\frac{\alpha}{\omega_0}=\frac{R}{2}\sqrt{\frac{C}{L}}
$$

$$
\Delta=\frac{R^2}{L^2}-4\frac{1}{LC}=4\alpha^2-4\omega_0^2=4(\alpha^2-\omega_0^2)
$$

> **Situation#1: Overdamped Response**
>
> *Condition:*
> $$
> \alpha > \omega_0
> $$
> *Behavior:*
> $$
> \omega^2+\frac{R}{L}\omega+\frac{1}{LC}=0
> $$
>
> $$
> \omega^2+2\alpha\omega+\omega_0^2=0
> $$
>
> $$
> \Delta=\frac{R^2}{L^2}-4\frac{1}{LC}=4\alpha^2-4\omega_0^2=4(\alpha^2-\omega_0^2)>0
> $$
>
> $$
> \text{Two Real Roots}
> $$
>
> $$
> \begin{aligned}
> \omega_1=&\frac{-2\alpha+\sqrt{4(\alpha^2-\omega_0^2)}}{2}\\
> =&-\alpha+\sqrt{(\alpha^2-\omega_0^2)}\\
> =&-\omega_0(\zeta-\sqrt{(\zeta^2-1)})
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
> \omega_2=&\frac{-2\alpha-\sqrt{4(\alpha^2-\omega_0^2)}}{2}\\
> =&-\alpha-\sqrt{(\alpha^2-\omega_0^2)}\\
> =&-\omega_0(\zeta+\sqrt{(\zeta^2-1)})
> \end{aligned}
> $$
>
> $$
> q=A_1e^{-\omega_0(\zeta-\sqrt{(\zeta^2-1)})t}+A_2e^{-\omega_0(\zeta+\sqrt{(\zeta^2-1)})t}
> $$
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504190307704.png" alt="image-20240504190307704" style="zoom:33%;" />

> **Situation#2: Critically Damped Response**
>
> *Condition:*
> $$
> \alpha = \omega_0
> $$
> *Behavior:*
> $$
> \omega^2+\frac{R}{L}\omega+\frac{1}{LC}=0
> $$
>
> $$
> \omega^2+2\alpha\omega+\omega_0^2=0
> $$
>
> $$
> \begin{aligned}
> \omega_1=\omega_2=&\frac{-2\alpha+\sqrt{4(\alpha^2-\omega_0^2)}}{2}\\
> =&-\alpha+\sqrt{(\alpha^2-\omega_0^2)}\\
> =&-\alpha
> \end{aligned}
> $$
>
> $$
> q=Ae^{-\alpha t}
> $$
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504191020744.png" alt="image-20240504191020744" style="zoom:33%;" />

> **Situation#3: Underdamped Response (Damped oscillations)**
>
> *Condition:*
> $$
> \alpha < \omega_0
> $$
> *Behavior:*
> $$
> \omega^2+\frac{R}{L}\omega+\frac{1}{LC}=0
> $$
>
> $$
> \omega^2+2\alpha\omega+\omega_0^2=0
> $$
>
> $$
> \begin{aligned}
> \omega_1=&\frac{-2\alpha+\sqrt{4(\alpha^2-\omega_0^2)}}{2}\\
> =&-\alpha+\sqrt{(\alpha^2-\omega_0^2)}\\
> =&-\omega_0(\zeta-\sqrt{(1-\zeta^2)}i)
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
> \omega_2=&\frac{-2\alpha-\sqrt{4(\alpha^2-\omega_0^2)}}{2}\\
> =&-\alpha-\sqrt{(\alpha^2-\omega_0^2)}\\
> =&-\omega_0(\zeta+\sqrt{(1-\zeta^2)}i)
> \end{aligned}
> $$
>
> $$
> q=A_1e^{-\omega_0(\zeta-\sqrt{(1-\zeta^2)}i)t}+A_2e^{-\omega_0(\zeta+\sqrt{(1-\zeta^2)}i)t}
> $$
>
> $$
> q=Be^{-\alpha t}\cos{(\omega_0\sqrt{1-\zeta^2}t+\phi)}
> $$
>
> $$
> q=Qe^{-\frac{R}{2L} t}\cos{(\omega_0\sqrt{1-\zeta^2}t+\phi)}
> $$
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504192326434.png" alt="image-20240504192326434" style="zoom:33%;" />

###### Forced Oscillations in LCR Circuits

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504192629518.png" alt="image-20240504192629518" style="zoom:50%;" />

If now I suppose the upper plate of the capacitance is positive, then we will have 
$$
i=\frac{dq}{dt}
$$
We are given that the Electromotive Force to be 
$$
\xi = \xi_m\sin(\omega_d t-\phi)
$$

$$
\xi-\frac{dq}{dt}R-\frac{q}{C}-L\frac{di}{dt}=0
$$

$$
\xi_m\sin(\omega_d t-\phi)-q'R-\frac{q}{C}-Lq''=0
$$

$$
q''+\frac{R}{L}q'+\frac{1}{CL}q=\frac{\xi_m}{L}\sin(\omega_d t-\phi)
$$

Set
$$
q=q_0+q_p
$$
We have already solve the problem with $q_0$ in the previous few problems.

Set
$$
q_p = A\cos(\omega_dt-\phi)+B\sin{(\omega_d t-\phi)}
$$

$$
-A\omega_d^2+B\omega_d\frac{R}{L}+\frac{A}{CL}=0
$$

$$
-B\omega_d^2-A\omega_d\frac{R}{L}+\frac{B}{CL}=\frac{\xi_m}{L}
$$

$$
B(\omega_0^2-\omega_d^2)-2A\alpha\omega_d=\frac{\xi_m}{L}
$$

$$
A(\omega_0^2-\omega_d^2)+2B\alpha\omega_d=0
$$

