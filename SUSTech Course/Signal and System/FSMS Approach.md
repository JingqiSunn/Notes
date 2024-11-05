#### FSMS Approach For Discrete Time Case

##### Target System

Linear Time-Invariant System

> [!NOTE]
>
> The reason we need these kinds of special characteristics is that we need to use the linearity to work out the target input by the linear combination of the basic input set. The reason we need it to be time invariant is to make sure that we can use our basic input data set regardless the fact that the time is actually shifting.

##### Origin

We always believe that there exists some sets of inputs with limited size that can represent all kinds of other inputs by simply the linear combination.

And it is obvious that if we use the ==Unit Impulse Function== as the input signal. Although there is only one signal input in the signal set, but it is in fact quite enough to represent any kind of input signal while able to yield all the possible output signal given the linear time-invariant system.

##### A General Way to Find the output of Input Signal

###### How to represent all the input by Unit Impulse Function

Suppose we have several known input and output pairs.
$$
x_1[n]\rightarrow y_1[n]
$$

$$
x_2[n]\rightarrow y_2[n]
$$

$$
x_3[n]\rightarrow y_3[n]
$$

$$
...
$$

So we may find a linear combination that (maybe you can use some knowledge of time-invariant which can help you do the shifting)
$$
x[n]=\sum_ka_kx_k[n]
$$

###### How to represent all the output by Unit Impulse Response

Then according to the property of Linearity, we can represent the output signal by
$$
y[n]=\sum_ka_ky_k[n]
$$
That is the basic idea of the later knowledge.

##### Use Unit Impulse Function to Represent Any possible Output

###### Some Definitions

1. Unit Impulse Function
   $$
   \delta [n] = \cases{0,\quad n\neq 0\\1,\quad n=0}\quad, n\in \Z
   $$

2. Unit impulse Response 

$$
h[n],\text{ which is the output for an unit impulse input}
$$

###### How to represent all the input by Unit Impulse Function

We have already known that 
$$
\delta [n] = \cases{0,\quad n\neq 0\\1,\quad n=0}\quad, n\in \Z
$$
Then we can use the property of time-invariant to produce more kinds of input signals.
$$
\delta [n-k] = \cases{0,\quad n\neq k\\1,\quad n=k}\quad, n\in \Z
$$
It is just like a sift that can scan over all parts of the target signal while giving out a corresponding parameter.

So it is easy to find out that 
$$
\begin{aligned}
x[n]
&=...+x[-2]\delta[n+2]+x[-1]\delta[n+1]+x[0]\delta[n]+x[1]\delta[n-1]+x[2]\delta[n-2]\\
&=\sum_{k=-\infty}^{+\infty}x[k]\delta[n-k]
\end{aligned}
$$

###### How to represent all the output by Unit Impulse Response

And we know the fact that unit impulse response is the output for an unit impulse input, marked has $h[n]$
$$
\delta[n]\rightarrow h[n]
$$
We have **Time-Invariant**
$$
\delta[n-k]\rightarrow h[n-k]
$$
So according to the property of linearity, we have
$$
y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]=x[n]*h[n]
$$
when $*$ is the sign of convolution.

> [!NOTE]
>
> We can drawn a conclusion here that the output of any discrete time linear time-invariant system is a convolution of the input signal with the unit-sample response.
>
> As a result, **any discrete time linear time-invariant system are completely characterized by its unit sample response**.

##### Another Way to Under the Expression $y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]$

> [!NOTE]
>
> Just now we have worked out the expression of the output signal based on the unit impulse response, but what we have already done focused more on the whole body of the output signal, maybe we can analyze the relationship when we get a slice of the output signal.

What we have is 
$$
y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]
$$
Now we suppose $n$ is a constant, and we are curious about the value of the output signal at that time instance.

We can notice that when we set $n$ to be a constant then the function is all about $k$, there is only one variable left.
$$
\sum_{k=-\infty}^{+\infty}x[k]h[n-k]
$$
That means you just need to find the graph of $h[n-k]$ which is a flipped version of $h[n]$ while $x[k]$ looks all  the same as $x[n]$.

Which you can see will be very convenient to calculate.

And here you can have the **Toeplitz Matrix**
$$
\begin{bmatrix}
y[-N]\\
y[-N+1]\\
...\\
y[N-1]\\
y[N]
\end{bmatrix}
=\begin{bmatrix}
h[0]&h[-1]&...&h[-2N+1]&h[-2N]\\
h[1]&h[0]&...&h[-2N+2]&h[-2N+1]\\
...&...&...&...&...\\
h[2N-1]&h[2N-2]&...&h[0]&h[-1]\\
h[2N]&h[2N-1]&...&h[1]&h[0]\\
\end{bmatrix}
\begin{bmatrix}
x[-N]\\
x[-N+1]\\
...\\
x[N-1]\\
x[N]
\end{bmatrix}
$$

> [!NOTE]
>
> I personally think the first method is much easier.

##### Property of the Unit Impulse Function

###### When $h[n]=\delta[n]$

$$
y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]=\sum_{k=-\infty}^{+\infty}x[k]\delta[n-k]=x[n]
$$

###### When $h[n]=\delta[n-n_0]$

$$
y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]=\sum_{k=-\infty}^{+\infty}x[k]\delta[n-k-n_0]=x[n-n_0]
$$

###### When $h[n]=u[n]$

$$
y[n]=\sum_{k=-\infty}^{+\infty}x[k]h[n-k]=\sum_{k=-\infty}^{+\infty}x[k]u[n-k]=\sum_{k=-\infty}^{n}x[k]
$$

##### Some Nonlinear System May Have the Same Impulse Response as LTI

==If you use the unit impulse function as the input signal, then after scanning, you will find the result will be the same among several different systems.==

But I think you can make sure that you can have only one unique LTI system, and some other looser system(because they will not follow the rule of the LTI)

> Given an LTI system
> $$
> h[n]=\cases{1,\quad n= 0,1\\0,\quad \text{otherwise}}
> $$
>
> $$
> x[n]=\delta [n]
> $$
>

*Solution:*
$$
\begin{aligned}
y[n]
=&\sum_{k=-\infty}^{+\infty}x[k]h[n-k]\\
=&\sum_{k=-\infty}^{+\infty}x[k]h[n-k]\\
=&x[n-1]+x[n]
\end{aligned}
$$
Then you can see that 
$$
y[n]=\cases{1,\quad n= 0,1\\0,\quad \text{otherwise}}
$$

> Given a nonlinear system
> $$
> y[n]=(x[n]+x[n-1])^2
> $$
>
> $$
> x[n]=\delta[n]
> $$

*Solution:*

You can find the answer of this question just by inserting value of $x$.
$$
y[n]=\cases{1,\quad n= 0,1\\0,\quad \text{otherwise}}
$$
There are other examples.

##### Property of Conclusion

> **Commutative**
> $$
> y[n]=x[n]*h[n]=h[n]*x[n]
> $$

*Proof:*
$$
\begin{aligned}
y[n]
&=x[n]*h[n]\\
&=\sum_{k=-\infty}^{+\infty}x[k]\cdot h[n-k]\\
&=\sum_{k=-\infty}^{+\infty}h[k]\cdot x[n-k]\\
&=h[n]*x[n]
\end{aligned}
$$

> **Distributive**
> $$
> x[n]*\{h_1[n]+h_2[n]\}=x[n]*h_1[n]+x[n]*h_2[n]
> $$

*Proof:*
$$
\begin{aligned}
&x[n]*\{h_1[n]+h_2[n]\}\\
=&\sum_{k=-\infty}^{+\infty}x[k]\cdot \{h_1[n-k]+h_2[n-k]\}\\
=&\sum_{k=-\infty}^{+\infty}x[k]\cdot h_1[n-k]+\sum_{k=-\infty}^{+\infty}x[k]\cdot h_2[n-k]\\
=&x[n]*h_1[n]+x[n]*h_2[n]
\end{aligned}
$$

> [!NOTE]
>
> Other calculation rules can all be derived from those two rules.

##### Some Useful Property of LTI Systems

- Causality
  $$
  h[n]=0\text{  for all }n<0
  $$

- Stability
  $$
  \sum_{k=-\infty}^{+\infty}|h[k]|<\infty
  $$
