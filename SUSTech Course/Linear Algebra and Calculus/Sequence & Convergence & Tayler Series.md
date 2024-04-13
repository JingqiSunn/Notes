#### Sequence & Convergence & Tayler Series

##### Sequence

> *Definition:*
>
> Sequence is a function whose domain is a set of positive integers.

##### Convergence of Sequence

> *Definition:*
>
> $\forall \epsilon$, $\exist N$, that when $n > N$, we have $|a_n-L|<\epsilon$​.
>
> *Notation:*
> $$
> \lim_{n\rightarrow \infty}a_n=L,a_n\rightarrow L
> $$

##### Divergence of Sequence

> *Definition:*
>
> $\forall \epsilon>0$, $\exist N$, that when $n > N$, we have $|a_n-L|<\epsilon$, can not satisfy.

##### Diverge to Infinity

> *Definition:*
>
> $\forall M>0$, $\exist N$, that when $n>N$, we have $a_n>M$.
>
> *Notation:*
> $$
> \lim_{n\rightarrow \infty} a_n=\infty, a_n\rightarrow \infty
> $$

##### Diverge to Negative Infinity

> *Definition:*
>
> $\forall m<0$, $\exist N$, that when $n>N$, we have $a_n<m$​.
>
> *Notation:*
> $$
> \lim_{n\rightarrow \infty}a_n=-\infty, a_n\rightarrow -\infty
> $$

##### Calculating Limits of Series

> $$
> \lim_{n\rightarrow \infty}a_n=A, \lim_{n\rightarrow \infty} b_n=B
> $$
>
> **Theorem 1.1**
>
> *Definition:*
> $$
> \lim_{n\rightarrow\infty}(a_n+b_n)=A+B
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty}a_n=A, \lim_{n\rightarrow \infty} b_n=B$,
>
> Then according to the definition of convergence of sequence,
>
> $\forall \frac{\epsilon}{2}$, $\exist N_1$, that when $n > N_1$, we have $|a_n-A|<\frac{\epsilon}{2}$.
>
> $\forall \frac{\epsilon}{2}$, $\exist N_2$, that when $n > N_2$, we have $|b_n-B|<\frac{\epsilon}{2}$.
>
> Set $N=N_1+N_2$,
>
> $\forall \epsilon$, $\exist N$, that when $n > N>N_1,n>N>N_2$, we have $|a_n-A|<\frac{\epsilon}{2},|b_n-B|<\frac{\epsilon}{2}$​.
>
> Then we have $|a_n+b_n-A-B|\leq |a_n-A|+|b_n-B|<\frac{\epsilon}{2}+\frac{\epsilon}{2}=\epsilon$.
>
> So we have $\forall \epsilon$, $\exist N$, that when $n > N$, we have $|a_n+b_n-A-B|<\epsilon$​.
>
> Which means $\lim_{n\rightarrow \infty}a_n+b_n=A+B$.
>
> **Theorem 1.2**
>
> *Definition:*
> $$
> \lim_{n\rightarrow\infty}(a_n-b_n)=A-B
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty}a_n=A, \lim_{n\rightarrow \infty} b_n=B$,
>
> Then according to the definition of convergence of sequence,
>
> $\forall \frac{\epsilon}{2}$, $\exist N_1$, that when $n > N_1$, we have $|a_n-A|<\frac{\epsilon}{2}$.
>
> $\forall \frac{\epsilon}{2}$, $\exist N_2$, that when $n > N_2$, we have $|b_n-B|<\frac{\epsilon}{2}$.
>
> Set $N=N_1+N_2$,
>
> $\forall \epsilon$, $\exist N$, that when $n > N>N_1,n>N>N_2$, we have $|a_n-A|<\frac{\epsilon}{2},|b_n-B|<\frac{\epsilon}{2}$​.
>
> Then we have $|a_n-b_n-A+B|\leq |a_n-A|+|b_n-B|<\frac{\epsilon}{2}+\frac{\epsilon}{2}=\epsilon$.
>
> So we have $\forall \epsilon$, $\exist N$, that when $n > N$, we have $|(a_n-b_n)-(A-B)|<\epsilon$​.
>
> Which means $\lim_{n\rightarrow \infty}a_n-b_n=A-B$​.
>
> **Theorem 1.3**
>
> *Definition:*
> $$
> \lim_{n\rightarrow \infty}(k\cdot b_n)=k\cdot B
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty} b_n=B$, and $k$ is a constant.
>
> Then according to the definition of convergence of sequence,
>
> $\forall\frac{\epsilon}{k}$, $\exist N$, that when $n > N$, we have $|b_n-B|<\frac{\epsilon}{k}$.
>
> Then we have 
>
> $\forall\epsilon$, $\exist N$, that when $n > N$, we have $|k\cdot b_n-k\cdot B|=k|b_n-B|<\frac{\epsilon}{k}\cdot k=\epsilon$​.
>
> Which means $\lim_{n\rightarrow \infty}(k\cdot b_n)=k\cdot B$​.
>
> **Theorem 1.4**
>
> *Definition:*
> $$
> \lim_{n\rightarrow \infty}(a_n\cdot b_n)=A\cdot B
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty}a_n=A, \lim_{n\rightarrow \infty} b_n=B$, I will just focus on the situation when A and B are both positive numbers, otherwise you can use the theorem 1.2 to change them into positive type.
>
> Then according to the definition of convergence of sequence, 
>
> So set $\forall \epsilon> 0$, $\exist N_1, N_2,N_3, N_4$,
> $$
> \begin{aligned}
> &n>N_1, |a_n-A|\leq \sqrt{\frac{\epsilon}{3}}\\
> &n>N_2, |b_n-B|\leq \sqrt{\frac{\epsilon}{3}}\\
> &n>N_3, |a_n-A|\leq \frac{\epsilon}{3(1+A)}\\
> &n>N_4, |b_n-B|\leq \frac{\epsilon}{3(1+B)}\\
> \end{aligned}
> $$
> Set $N=\max\{{N_1,N_2,N_3,N_4}\}$, then we when $n> N$
> $$
> a_n=(a_n-A)+A,b_n=(b_n-B)+B
> $$
>
> $$
> \begin{aligned}
> a_nb_n - AB =& ((a_n-A)+A)\cdot ((b_n-B)+B)-AB\\
> =&(a_n-A)\cdot (b_n-B)+A\cdot(b_n-B)+B\cdot (a_n-A)\\
> \leq&(a_n-A)\cdot (b_n-B)+(A+1)\cdot(b_n-B)+(B+1)\cdot (a_n-A)\\
> <&\frac{\epsilon}{3}\cdot 3\\
> =&\epsilon
> \end{aligned}
> $$
>
> So we will have that 
> $$
> \lim_{n\rightarrow \infty}a_nb_n = AB
> $$
> **Theorem 1.5**
>
> *Definition:*
> $$
> \lim_{n\rightarrow \infty }\frac{a_n}{b_n}=\frac{A}{B}
> $$
> *Proof:*
>
> To prove this theorem we have to prove that $\lim_{n\rightarrow \infty }\frac{1}{b_n}=\frac{1}{B}$.
>
> And we will set a number $B'$ that $0<B'<B$.
>
> According to the definition of convergence we have 
>
> $\forall \epsilon>0$, $\exist N$, that when $n>N$, we will have $|b_n-B|<\epsilon\cdot B(B-B')$
>
> Then when $n>N$, we have
> $$
> \begin{aligned}
> |\frac{1}{b_n}-\frac{1}{B}|=&|\frac{B-b_n}{B\cdot b_n}|\\
> <&|\frac{B-b_n}{B\cdot (B-\epsilon)}|\\
> <&|\frac{B-b_n}{B\cdot (B-B')}|\\
> <&\epsilon
> \end{aligned}
> $$
> So according to the definition of convergence we have $\lim_{n\rightarrow \infty }\frac{1}{b_n}=\frac{1}{B}$, now using the theorem 1.3, we can just prove $\lim_{n\rightarrow \infty }\frac{a_n}{b_n}=\frac{A}{B}$.

##### Theorem 2: The Sandwich Theorem for Sequence

> *Definition:*
>
> $a_n,b_n,c_n$ are sequence, when $n>N$, if we have $a_n\leq b_n\leq c_n$, also $\lim_{n\rightarrow \infty}a_n= \lim_{n\rightarrow \infty}c_n=L$.
>
> Then we will have $\lim_{n\rightarrow \infty}b_n=L$.
>
> *Proof:*
>
> We have the definition of the convergence of the sequence, 
> $$
> \forall \epsilon>0,\exist N_1,(n>N_1)\vdash(n>N_1)\rightarrow(|a_n-L|<\epsilon)\\
> \forall \epsilon>0,\exist N_2,(n>N_2)\vdash(n>N_2)\rightarrow(|c_n-L|<\epsilon)\\
> $$
> Set $N'=\max{\{N,N_1,N_2\}}$,
>
> When $n>N'$, we have $a_n\leq b_n\leq c_n$.
> $$
> |b_n-L|<\max{\{|a_n-L|,|c_n-L|\}}<\epsilon
> $$
> According to the definition of convergence of the sequence we have $\lim_{n\rightarrow \infty}b_n=L$

##### Infinite Series

> *Definition:*
>
> An infinite series is the sum of an infinite sequence of numbers.
>
> *General Form:*
> $$
> a_1+a_2+a_3+...+a_n+...
> $$
> 

##### Partial Sum

> *Definition:*
>
> > [!WARNING]
> >
> > Please remember that partial sum is a sequence.
>
> If the infinite series is $a_1+a_2+a_3+...+a_n+...$
>
> Then partial sum is a sequence $\{s_n\}$,
> $$
> s_n=\sum_{i=1}^{n}a_i
> $$
> 

##### Convergence of the Series

> *Definition:*
>
> When the partial sum sequence converges, then we will say that the series converges.
> $$
> (\lim_{n\rightarrow \infty}s_n=L)\vdash (\sum_{n=1}^{\infty}a_n=L)
> $$
> 

##### Geometric Series

> *Definition:*
> $$
> \sum_{n=1}^{\infty}ar^{n-1}
> $$
> *Property:*
> $$
> (|n|<1)\vdash\sum_{n=1}^{\infty}ar^{n-1}=\frac{a}{1-r}\\
> (|n|\geq 1)\vdash \text{divergence}
> $$
> 

##### Theorem 7

> *Definition:*
> $$
> ((\sum_{n=1}^{\infty}a_n)\text{convergence)}\vdash (\lim_{n\rightarrow \infty}a_n=0)
> $$
> *Proof:*
>
> We have the series converge is just the partial sum sequence converge.
>
> Suppose $\lim_{n\rightarrow \infty}\sum_{i=1}^{n} a_i=L$, also we will have that $\lim_{n\rightarrow \infty}\sum_{i=1}^{n-1} a_i=L$.
>
> So we will have 
> $$
> \lim_{n\rightarrow \infty}a_n=\lim_{n\rightarrow \infty}\sum_{i=1}^{n} a_i-\lim_{n\rightarrow \infty}\sum_{i=1}^{n-1} a_i=L-L=0
> $$
> 

##### The n^th^ Term Test For Divergence

> *Definition:*
> $$
> (\lim_{n\rightarrow \infty}a_n\ne 0)\vdash \sum_{n=1}^{\infty}a_n\text{divergence}
> $$
> *Proof:*
>
> You can use the *Reductio ad Absurdum* .

> [!IMPORTANT]
>
> We are going to find ways to examine whether the series diverge, but we are going to start with the case when $a_n>0$ always true.

##### The Integrational Test

> *Definition:*
>
> $a_n > 0$, $a_n$is decreasing, the series $\sum_{n=N}^{\infty}a_n$ and the integral $\int_N^{\infty}f(x)dx$​ both converge or diverge.
>
> *Proof:*
>
> We will use the convergence or divergence of the partial sum to represent which of the infinite series.
>
> And the *Sandwich Rule* will be very important in this proof.
>
> Set $f(x)$ satisfies: positive, decreasing, $f(n)=a_n$
> $$
> \begin{aligned}
> \sum_{i=N}^{n}a_n=&a_N+a_{N+1}+a_{N+2}+...+a_n\\
> =&\int_{N}^{N+1}a_Ndx+\int_{N+1}^{N+2}a_{N+1}dx+...+\int_{n}^{n+1}a_ndx\\
> \geq&\int_{N}^{N+1}f(x)dx+\int_{N+1}^{N+2}f(x)dx+...+\int_{n}^{n+1}f(x)dx\\
> =&\int_{N}^{n+1}f(x)dx
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
> \sum_{i=N}^{n}a_n=&a_N+a_{N+1}+a_{N+2}+...+a_n\\
> =&\int_{N-1}^{N}a_Ndx+\int_{N}^{N+1}a_{N+1}dx+...+\int_{n-1}^{n}a_ndx\\
> \leq&\int_{N-1}^{N}f(x)dx+\int_{N}^{N+1}f(x)dx+...+\int_{n-1}^{n}f(x)dx\\
> =&\int_{N-1}^{n}f(x)dx
> \end{aligned}
> $$
>
> Now we have
> $$
> \int_{N}^{n+1}f(x)dx\leq \sum_{i=N}^{n}a_n\leq \int_{N-1}^{n}f(x)dx
> $$
> when $n\rightarrow \infty$, we will have that $\int_{N}^{n+1}f(x)dx$ and $\int_{N-1}^{n}f(x)dx$​ both converge or diverge, then using the sandwich rule we will find that 
>
> $a_n > 0$, $a_n$is decreasing, the series $\sum_{n=N}^{\infty}a_n$ and the integral $\int_N^{\infty}f(x)dx$ both converge or diverge.
>
> *Error Estimation:*
>
>  