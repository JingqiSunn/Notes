## Fourier Transformation

#### Fourier Series

Here we will review two major part of the knowledge of **Fourier Series**, and the detail will not be mentioned here.

The only important thing to mention here is to take the following steps as a linear transformation from two spaces.

##### Input Space

$$
\text{DT:: }\C ^N
$$

$$
\text{CT:: }\C^{\infty}
$$

##### Output Space

$$
\text{DT:: }e^{jk\omega_0 t},k=0,1,2,3,...,N-1,\omega_0 = \frac{2\pi}{N}
$$

$$
\text{CT:: }e^{jk\omega_0 t}, k =-\infty,...,-1,0,1,...,\infty, \omega_0 = \frac{2\pi}{N}
$$

> [!NOTE]
>
> And all these bases in the output space are all orthogonally eigenvectors.

Here are the projection parameters.
$$
\text{DT:: }a_k =\frac{1}{N}\sum_{n=0}^{N-1}x[n]e^{-jk\omega_0n}
$$

$$
\text{CT:: }a_k = \frac{1}{N}\int_{0}^{N}x[n]e^{-jk\omega_0 n}dn
$$

 Here is the expression after the linear transformation.
$$
\text{DT:: }x[t]=\sum_{k=0}^{N-1}a_ke^{jk\omega_0 t}
$$

$$
\text{CT:: }x(t)=\sum_{k=-\infty}^{\infty}a_ke^{jk\omega_0 t}
$$

**Eigenvalue**

Let's consider continuous time situation.

Suppose we put the eigenvector $e^{kj\omega_0 t}$ into the system with unit impulse response $h(t)$

So we have 
$$
y(t)=x(t)*h(t)=h(t)*x(t)=\int_{-\infty}^{\infty}h(\tau)x(t-\tau)d\tau=\int_{-\infty}^{\infty}h(\tau)e^{kj\omega_0 (t-\tau)}d\tau=\int_{-\infty}^{\infty}h(\tau)e^{-kj\omega_0\tau }d\tau\cdot x(t)
$$
So we get that for continuous time situation, we have eigenvalue to be 
$$
H(j\omega) =\int_{-\infty}^{\infty}h(\tau)e^{-j\omega\tau }d\tau
$$
Now let us consider the situation of discrete time situation.

Suppose we put the eigenvector $e^{kj\omega_0 n}$ into the system with unit impulse response $h[n]$

So we have 
$$
y[n]=x[n]*h[n]=h[n]*x[n]=\sum_{\tau = -\infty}^{\infty}h[\tau]x[n-\tau]=\sum_{\tau = -\infty}^{\infty}h[\tau]e^{kj\omega_0 (n-\tau)}=\sum_{\tau= -\infty}^{\infty}h[\tau]e^{-kj\omega_0 \tau}\cdot x[n]
$$
So we get that for discrete time situation, we have eigenvalue to be 
$$
H(e^{j\omega})=\sum_{k = -\infty}^{\infty}h[\tau]e^{-j\omega \tau}
$$

> [!CAUTION]
>
> As we have mentioned in the class, if a signal can be represented by discrete $e^{j\omega t}$, then the signal is periodic. However, in our daily life, most of the signals are aperiodic, and there are two solution for this.
>
> 1. Just repeat the aperiodic signal to create a periodic signal.
> 2. Use the Fourier Transformation.
>
> We can always use the first strategy, but it is somehow not so efficient.

#### Fourier Transformation

As we have mentioned before, we know that there is one way to deal with aperiodic signal which is to create periodic signal from aperiodic signal and then apply the method of **Fourier Series** on it.

We will not consider infinity here, we will take the infinity afterwards.

Suppose any aperiodic signal $x(t)$ has a finite length of duration $T$, then $\tilde{x}(t)$ will be the repeating version of $x(t)$.

We will focus on the **Fourier Series** of the signal $\tilde{x}(t)$ because it has the same value as $x(t)$ in the necessary interval. 

As we learned in the former part.
$$
\text{CT:: }\tilde{x}(t)=\sum_{k=-\infty}^{\infty}a_ke^{jk\omega_0 t}
$$
Now we have to do 
$$
\begin{aligned}
&a_k \\
=&\frac{1}{T}\int _{-\frac{T}{2}}^{\frac{T}{2}} \tilde{x}(t)e^{-jk\omega_0 t}dt\\
=&\frac{1}{T}\int _{-\infty}^{\infty} x(t)e^{-jk\omega_0 t}dt\\
\end{aligned}
$$
So we have 
$$
a_k = \frac{1}{T}X(j\omega),X(j\omega) =\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt
$$
We used to have 
$$
\text{CT:: }x(t)=\sum_{k=-\infty}^{\infty}a_ke^{jk\omega_0 t}
$$
So this time we have 
$$
\begin{aligned}
x(t)&=\sum_{k=-\infty}^{\infty}a_ke^{jk\omega_0 t}\\
&=\sum_{k=-\infty}^{\infty}\frac{1}{T}X(j\omega)e^{jk\omega_0 t}\\
&=\sum_{k=-\infty}^{\infty}\frac{\omega }{2\pi}X(j\omega)e^{j\omega t}\\
&=\frac{1}{2\pi}\sum_{k=-\infty}^{\infty}\omega X(j\omega)e^{j\omega t}\\
\end{aligned}
$$
We can find that this is like a Riemann sum, now when $T$ is getting to the $\infty$, we will find $\omega_0 = \frac{2\pi}{T}$ getting smaller and smaller, which means that the selection of $\omega $ is now continuous. Although it is still some multiple of a fundamental frequency, but it is so small that it is like continuous.

So we bring $T\rightarrow \infty$, we will have 
$$
\begin{aligned}
x(t)&=\sum_{k=-\infty}^{\infty}a_ke^{jk\omega_0 t}\\
&=\sum_{k=-\infty}^{\infty}\frac{1}{T}X(j\omega)e^{jk\omega_0 t}\\
&=\sum_{k=-\infty}^{\infty}\frac{\omega }{2\pi}X(j\omega)e^{j\omega t}\\
&=\frac{1}{2\pi}\sum_{k=-\infty}^{\infty}\omega X(j\omega)e^{j\omega t}\\
&=\frac{1}{2\pi}\int _{-\infty}^\infty X(j\omega)e^{j\omega t}d\omega
\end{aligned}
$$
So we have the **conclusion** that 
$$
\text{CT:: }x(t)=\frac{1}{2\pi}\int _{-\infty}^\infty X(j\omega)e^{j\omega t}d\omega, X(j\omega )=\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt
$$

$$
\text{CT:: }a_k = \frac{1}{T}X(j\omega),X(j\omega) =\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt 
$$

And what is defined is 

**Fourier Transform**
$$
X(j\omega )=\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt
$$
**Inverse Fourier Transform**
$$
x(t)=\frac{1}{2\pi}\int _{-\infty}^\infty X(j\omega)e^{j\omega t}d\omega
$$

#### Some Important Conclusion

> About Unit Impulse Function

We have 
$$
X(j\omega )=\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt
$$
So for Unit Impulse function, we have 
$$
X(j\omega ) =\int _{-\infty}^{\infty} \delta (t)e^{-j\omega  t}dt=e^{-j\omega t}\Bigg|_{t=0}=1
$$
**We have**
$$
\delta (t)=\frac{1}{2\pi}\int _{-\infty}^\infty e^{j\omega t}d\omega
$$

> Fact about $CTFT$

- $$
  X(0)=\int _{-\infty}^{\infty} x(t)e^{-j\omega  t}dt=\int _{-\infty}^{\infty} x(t)dt
  $$

- $$
  x(0)=\frac{1}{2\pi}\int _{-\infty}^\infty X(j\omega)d\omega
  $$

> Unit conclusion of periodic signals

When 
$$
X(j\omega )=\delta (\omega -\omega_0)
$$
Then we have 
$$
x(t)=\frac{1}{2\pi}\int _{-\infty}^\infty X(j\omega)e^{j\omega t}d\omega=\frac{1}{2\pi}e^{j\omega _0 t}
$$
So we can see that there exists corresponding pairs.
$$
X(j\omega )=2\pi\delta (\omega -\omega_0) \rightarrow x(t)=e^{j\omega _0 t}
$$

> When signal is originally periodic.

When the signal is originally periodic, we have that 
$$
x(t)=\sum_{k=-\infty}^{\infty}a_k e^{jk\omega_0 t}
$$
Then we will have 
$$
X(j\omega )=\sum_{k=-\infty}^\infty a_k2\pi\delta (\omega -\omega_0)
$$
