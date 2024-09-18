#### Exponential Signals

##### Syntax

- CT signals
  $$
  x(t) = e^{j\omega t}
  $$

- DT signals
  $$
  x[n]=e^{j\omega n}
  $$

The expression above both have a real and imaginary part, but that is what we see in the Cartesian form.

However in polar form, according to the Euler's relation, what we can see are magnitude and phase.
$$
e^{jx}=\cos{x}+j\sin{x}
$$
So here we can transform the formula of the exponential signals into the form in the polar form.

- CT signals 
  $$
  x(t)=\cos(\omega t)+j\sin(\omega t)
  $$

- DT signals
  $$
  x[n]=\cos(\omega n)+j\sin(\omega n)
  $$

> [!NOTE]
>
> Based on the knowledge of the wave function, and here we have a basic assumption that 
> $$
> \text{the angular frequency is } |\omega_0|,\text{ which will replace the $\omega$ in the original formula}
> $$
> We can figure out that 
>
> 1. $$
>    T_0=\frac{2\pi}{|\omega_0|}
>    $$

###### Some Conclusion for CT

> $e^{j\omega_0 t}$ is always periodic

*Proof:*
$$
x(t)=e^{j\omega_0 t}=\cos{\omega_0 t}+j\sin{\omega_0 t}
$$
Then we can find that 
$$
\begin{aligned}
x(t+\frac{2\pi}{\omega_0})
&=\cos{\omega_0 (t+\frac{2\pi}{\omega_0})}+j\sin{\omega_0 (t+\frac{2\pi}{\omega_0})}\\
&=\cos{(\omega_0 t+2\pi)}+j\sin{(\omega_0 t+2\pi)}\\
&=\cos{\omega_0 t}+j\sin{\omega_0 t}\\
&=x(t)
\end{aligned}
$$
So there is at least one proper solution for the fundamental period that 
$$
T_0 = \frac{2\pi}{|\omega_0|}
$$

> [!NOTE]
>
> And there is one other conclusion that a larger $\omega_0$ means a higher frequency.

###### Some Conclusion for CT

> $e^{j\omega_0 n}$ is periodic only when $\omega_0$ is a rational multiple of $2\pi$

*Proof:*

Let's first suppose $e^{j\omega_0 n}$ is periodic.
$$
\begin{aligned}
x[n]
&=x[n+N]
\end{aligned}
$$
for some $N$ as a rational number.
$$
\begin{aligned}
x[n]
&=x[n+N]\\
&=e^{j\omega_0{(n+N)}}\\
&=e^{j\omega_0{n}}\cdot e^{j\omega_0{N}}\\
&=x[n]\cdot e^{j\omega_0{N}}
\end{aligned}
$$
Then we will have $e^{j\omega_0{N}}=1$
$$
\begin{aligned}
1 
&=\cos{(\omega_0 N)}+j\sin{(\omega_0 N)}
\end{aligned}
$$
So that we got 
$$
\omega_0 N = 2\pi m, \text{where $m$ is an integer, $N$ is an integer}
$$
The conclusion is that $e^{j\omega_0 n}$ is periodic only when $\omega_0$ is a rational multiple of $2\pi$.



