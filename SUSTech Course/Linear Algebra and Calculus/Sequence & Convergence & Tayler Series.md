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

##### Monotone Convergence Theorem

> *Definition:*
> $$
> (a_n>0)\and(\lim_{n\rightarrow \infty}(\sum_{i=1}^{n}a_i)\leq L)\vdash\sum_{i=1}^{n}a_i\text{convergence}\\
> (a_n<0)\and(\lim_{n\rightarrow \infty}(\sum_{i=1}^{n}a_i)\geq L)\vdash\sum_{i=1}^{n}a_i\text{convergence}
> $$
> *Proof:*
>
> > [!NOTE]
> >
> > I will not give the proof of this conclusion here.
>
> 

##### The Integrational Test

> *Definition:*
>
> $a_n > 0$, $a_n$is decreasing, the series $\sum_{n=N}^{\infty}a_n$ and the integral $\int_N^{\infty}f(x)dx$​ both converge or diverge.
>
> *Proof:*
>
> We will use the convergence or divergence of the partial sum to represent which of the infinite series.
>
> Set $f(x)$ satisfies: positive, decreasing, $f(n)=a_n$
> $$
> \begin{aligned}
> \sum_{i=N}^{n}a_i=&a_N+a_{N+1}+a_{N+2}+...+a_n\\
> =&\int_{N}^{N+1}a_Ndx+\int_{N+1}^{N+2}a_{N+1}dx+...+\int_{n}^{n+1}a_ndx\\
> \geq&\int_{N}^{N+1}f(x)dx+\int_{N+1}^{N+2}f(x)dx+...+\int_{n}^{n+1}f(x)dx\\
> =&\int_{N}^{n+1}f(x)dx
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
> \sum_{i=N}^{n}a_i=&a_N+a_{N+1}+a_{N+2}+...+a_n\\
> =&\int_{N-1}^{N}a_Ndx+\int_{N}^{N+1}a_{N+1}dx+...+\int_{n-1}^{n}a_ndx\\
> \leq&\int_{N-1}^{N}f(x)dx+\int_{N}^{N+1}f(x)dx+...+\int_{n-1}^{n}f(x)dx\\
> =&\int_{N-1}^{n}f(x)dx
> \end{aligned}
> $$
>
> Now we have
> $$
> \int_{N}^{n+1}f(x)dx\leq \sum_{i=N}^{n}a_i\leq \int_{N-1}^{n}f(x)dx
> $$
> If we find $\int_N^{\infty}f(x)dx$ converges, this means that $\sum_{i=N}^{n}a_n$ is increasing and has a specific upper bound, according to the monotone convergence theorem we find that $\sum_{i=N}^{n}a_n$  converges here.
>
> If we find $\int_N^{\infty}f(x)dx$ diverges, this means that $\sum_{i=N}^{n}a_n$ is bigger than $\infty$​, than it obviously diverges.
>
> So we proved
> $$
> (a_n>0)\and(\lim_{n\rightarrow \infty}(\sum_{i=1}^{n}a_i)\leq L)\vdash\sum_{i=1}^{n}a_i\text{convergence}\\
> (a_n<0)\and(\lim_{n\rightarrow \infty}(\sum_{i=1}^{n}a_i)\geq L)\vdash\sum_{i=1}^{n}a_i\text{convergence}
> $$
> **Error Estimation:**
>
> > [!IMPORTANT]
> >
> > I think it is very important for us to know that why we need this error estimation.
> >
> > For example I give you an convergent infinite series $\sum_{n=1}^{\infty}\frac{1}{n^2}$, we can not give the precise number that where it converges, but we can use the integrational test to give a rounded value for the series.
> >
> > But this will obviously cause some error, so we need to know how much error will it create.
>
> From the proof of the integrational test we can find a very important inequality.
> $$
> \int_{N}^{n+1}f(x)dx\leq \sum_{i=N}^{n}a_i\leq \int_{N-1}^{n}f(x)dx\\
> \int_{N}^{\infty}f(x)dx\leq \sum_{i=N}^{\infty}a_i\leq \int_{N-1}^{\infty}f(x)dx
> $$
> *Definition:*
>
> We use the partial sum to estimate the total sum.
> $$
> R_n=S-s_n
> $$
>
> $$
> \int_{n+1}^{\infty}f(x)dx\leq R_n \leq \int_{n}^{\infty}f(x)dx
> $$
>
> *Proof:*
> $$
> \begin{aligned}
> R_n=&S-s_n\\
> =&a_{n+1}+a_{n+2}+...\\
> \geq& \int_{n+1}^\infty f(x)dx
> \end{aligned}
> $$
>
> $$
> \begin{aligned}
> R_n=&S-s_n\\
> =&a_{n+1}+a_{n+2}+...\\
> \leq& \int_{n}^\infty f(x)dx
> \end{aligned}
> $$
>
> 

##### Comparison Test

> *Definition:*
> $$
> (a_n,c_n,d_n\geq 0)\and(d_n\leq a_n\leq c_n,n>N)\vdash (\sum d_n\text{divergence}\rightarrow \sum a_n\text{devergence})\\
> (a_n,c_n,d_n\geq 0)\and(d_n\leq a_n\leq c_n,n>N)\vdash (\sum c_n\text{convergence}\rightarrow \sum  a_n\text{convergence})
> $$
> *Proof:*
>
> When $\sum d_n$ diverges, we will find that $\sum d_n\rightarrow \infty$, so we find that $\sum a_n>\infty$, so we find that the series $\sum a_n$ obviously diverges.
>
> When $\sum c_n$ converges, then we will find that $\sum c_n\rightarrow L$, then we will find that $\sum a_n$ is increasing and also it is bounded, so according to the monotone convergence theorem, we will have the series $\sum a_n$ converges.
>
> > [!NOTE]
> >
> > You will find that you can only know that whether the series $\sum a_n$ converges, but if it converges you will have little knowledge about the exact limit of it.
>
> 

##### Limit Comparison Test

> **Theorem 11.1**
>
> *Definition:*
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=c>0)\vdash(\sum a_n,\sum b_n\text{both converge or diverge})
> $$
> *Proof:*
>
> > [!NOTE]
> >
> > This is just another version of the normal comparison test.
>
> We have $\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=c>0$, 
>
> Then according to the definition of limitation, we will have 
>
> For $\epsilon = \frac{c}{2}>0$, we have a corresponding $N$, when $n>N$, we have $|\frac{a_n}{b_n}-c|<\epsilon=\frac{c}{2}$.
>
> So we have when $n>N$, $|\frac{a_n}{b_n}-c|<\frac{c}{2}$.
> $$
> \frac{c}{2}<\frac{a_n}{b_n}<\frac{3c}{2}\\
> \frac{c\cdot b_n}{2}<a_n<\frac{3c\cdot b_n}{2}\\
> $$
> This is just in the form of formal comparison test.
>
> So we will find that 
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=c>0)\vdash(\sum a_n,\sum b_n\text{both converge or diverge})
> $$
> **Theorem 11.2**
>
> *Definition:*
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=0)\vdash(\sum b_n\text{Convergence}\rightarrow \sum a_n\text{Convergence})
> $$
>
> > [!NOTE]
> >
> > You can use a similar way to prove it.
>
> We have $\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=0$, according to the definition of limitation, we have 
>
> For $\epsilon = 1$, we have a corresponding $N$, when $n>N$, we have $|\frac{a_n}{b_n}|<\epsilon=1$.
>
> So we have when $n>N$, $|\frac{a_n}{b_n}|<1$​.
> $$
> 0<a_n<b_n
> $$
> Which is just in the form of comparison test.
>
> So we proved that 
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=0)\vdash(\sum b_n\text{Convergence}\rightarrow \sum a_n\text{Convergence})
> $$
> **Theorem 11.3**
>
> *Definition:*
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=\infty)\vdash(\sum b_n\text{Divergence}\rightarrow \sum a_n\text{Divergence})
> $$
>
> > [!NOTE]
> >
> > This proof is very similar to the former one, the only difference is that you have to use the infinite limitation definition.
>
> We have $\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=\infty$, according to the definition of limitation, we have 
>
> For $\epsilon = 1$, we have a corresponding $N$, when $n>N$, we have $|\frac{a_n}{b_n}|>\epsilon=1$.
>
> So we have when $n>N$, $|\frac{a_n}{b_n}|>1$​.
> $$
> b_n<a_n
> $$
> Which is just in the form of comparison test.
>
> So we proved that 
> $$
> (a_n,b_n>0,n>N)\and(\lim_{n\rightarrow \infty}\frac{a_n}{b_n}=\infty)\vdash(\sum b_n\text{Divergence}\rightarrow \sum a_n\text{Divergence})
> $$
> 

##### Absolute Convergence

> *Definition:*
> $$
> (\sum|a_n|\text{Convergence})\leftrightarrow(\sum a_n \text{is convergent absolutely})
> $$
>
> > [!NOTE]
> >
> > This will be more useful when it comes to the Tayler Series and the interval of the convergence.
>
> 

> [!WARNING]
>
> But there is one thing very important. From now on we are not going to purely study the non-negative series, we are going to analyze all the normal $a_n$.



##### The Ratio Test

> > [!NOTE]
> >
> > The central trick in the ratio test is how to compare the series you are working on with a geometric series.
>
> **Theorem 13.1**
>
> *Definition:*
> $$
> (\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho)\and(\rho<1)\vdash (\sum a_n\text{Convergence Absolutely})
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho$, so according to the definition of the limitation.
> $$
> \forall \epsilon, \exist N,\text{when } n>N,||\frac{a_{n+1}}{a_n}|-\rho|<\epsilon
> $$
>
> $$
> |\frac{a_{n+1}}{a_n}|-\rho\leq||\frac{a_{n+1}}{a_n}|-\rho|<\epsilon\\
> |\frac{a_{n+1}}{a_n}|-\rho<\epsilon\\
> |\frac{a_{n+1}}{a_n}|<\rho+\epsilon\\
> $$
>
> We choose relatively small $\epsilon$, for $n>N$, it can be proved that we can always find the corresponding $N$, and we have $\rho<1$.
>
> Then we will find there exist small $\epsilon$ that $r=\rho +\epsilon<1$
>
> That is when $n>N$, we have when $r<1$,
> $$
> |\frac{a_{n+1}}{a_n}|<r\\
> \frac{|a_{n+1}|}{|a_n|}<r\\
> |a_{n+1}|<r\cdot |a_{n}|
> $$
> Set $m\in \Z$, and $m\geq 1$.
> $$
> |a_{N+m}|<r^{m}\cdot |a_{N}|
> $$
>
> $$
> \begin{aligned}
> \sum_{n=1}^{\infty}|a_n|=&\sum_{n=1}^{N-1}|a_n|+\sum_{n=N}^{\infty}|a_n|\\
> <&\sum_{n=1}^{N-1}|a_n|+|a_N|(1+r+r^2+...+r^n+...)\\
> \end{aligned}
> $$
>
> And According to our knowledge on geometric series that when $r<1$, we will have $1+r+r^2+...+r^n+...$ to be convergent, then according to the calculating rule for convergence we will find that the series $\sum a_n$​  converges absolutely.
>
> So we got 
> $$
> (\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho)\and(\rho<1)\vdash (\sum a_n\text{Convergence Absolutely})
> $$
> **Theorem 13.2**
>
> *Definition:*
> $$
> (\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho)\and(\rho>1)\vdash (\sum a_n\text{Divergence})
> $$
> *Proof:*
>
> We have $\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho$, so according to the definition of the limitation.
> $$
> \forall \epsilon, \exist N,\text{when } n>N,||\frac{a_{n+1}}{a_n}|-\rho|<\epsilon
> $$
> We choose relatively small $\epsilon$, for $n>N$, it can be proved that we can always find the corresponding $N$, and we have $\rho>1$​.
> $$
> ||\frac{a_{n+1}}{a_n}|-\rho|<\epsilon\\
> \rho-\epsilon<|\frac{a_{n+1}}{a_n}|<\epsilon+\rho
> $$
> We have $\rho>1$, so there is a corresponding $\epsilon$ that when $n>N$, we have $r=\rho-\epsilon>1$
>
> So when $n>N$, we have $r<|\frac{a_{n+1}}{a_n}|$
>
> Then in the same way 
> $$
> \begin{aligned}
> &|a_{n+1}|>r\cdot|a_n|\\
> &|a_{N+m}|>r^{m}\cdot |a_{N}|\\
> \end{aligned}
> $$
> Then easily we will find a very trivial thing that 
> $$
> \lim_{n\rightarrow \infty}a_n\ne 0
> $$
> According to The n^th^ Term Test For Divergence, we will find that 
> $$
> (\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho)\and(\rho>1)\vdash (\sum a_n\text{Divergence})
> $$
> **Theorem 13.3**
>
> *Definition:*
> $$
> (\lim_{n\rightarrow \infty}|\frac{a_{n+1}}{a_n}|=\rho)\and(\rho=1)\vdash (\sum a_n\text{Inconclusive})
> $$
> *Proof:*
>
> I think there is no need to prove this.

##### The Root Test

> **Theorem 13.1**
>
> *Definition:*
> $$
> (\lim_{n\rightarrow\infty}\sqrt[n]{|a_n|}=\rho)\and(\rho<1)\vdash (\sum a_n\text{Convergence Absolutely})
> $$
> *Proof:*
>
> We have the definition of the limitation, so we have
> $$
> \forall \epsilon, \exist N,\text{when } n>N,|\sqrt[n]{|a_n|}-\rho|<\epsilon
> $$
>
> $$
> |\sqrt[n]{|a_n|}-\rho|<\epsilon\\
> \rho-\epsilon<\sqrt[n]{|a_n|}<\rho+\epsilon\\
> $$
>
> We have that $\rho<1$, so that we have for $n>N$, there will be 
> $$
> r=\rho+\epsilon<1
> $$
> So that 
> $$
> \sqrt[n]{|a_n|}<r\\
> |a_n|<r^n\\
> $$
> We know the characteristic of geometric series and also the comparison rule, 
>
> So that we have the series $\sum|a_n|$ converges, so that $\sum {a_n}$ converges absolutely.
>
> So we proved that 
> $$
> (\lim_{n\rightarrow\infty}\sqrt[n]{|a_n|}=\rho)\and(\rho<1)\vdash (\sum a_n\text{Convergence Absolutely})
> $$
> **Theorem 13.2**
>
> *Definition:*
> $$
> (\lim_{n\rightarrow\infty}\sqrt[n]{|a_n|}=\rho)\and(\rho>1)\vdash (\sum a_n\text{Divergence})
> $$
> *Proof:*
>
> We have the definition of the limitation, so we have
> $$
> \forall \epsilon, \exist N,\text{when } n>N,|\sqrt[n]{|a_n|}-\rho|<\epsilon
> $$
>
> $$
> |\sqrt[n]{|a_n|}-\rho|<\epsilon\\
> \rho-\epsilon<\sqrt[n]{|a_n|}<\rho+\epsilon\\
> $$
>
> We have that $\rho>1$, so that we have for $n>N$, there will be 
> $$
> r=\rho-\epsilon>1
> $$
> So that 
> $$
> \sqrt[n]{|a_n|}>r\\
> |a_n|>r^n\\
> $$
> We know the characteristic of geometric series,
>
> We can find that $\lim_{n\rightarrow \infty}a_n\ne0$. 
>
> So we proved that 
> $$
> (\lim_{n\rightarrow\infty}\sqrt[n]{|a_n|}=\rho)\and(\rho<1)\vdash (\sum a_n\text{Divergence})
> $$
> 

> [!NOTE]
>
> Although we have already mastered several test, but these are all too complexed, but for alternating series, we have an easier way to find whether it is convergent.

##### Alternating Series

> *Definition:*
> $$
> a_n=(-1)^{n+1}u_n\text{ or }a_n=(-1)^{n}u_n,\text{ when }u_n=|a_n|\text{ is a positive number.}
> $$
> 

##### The Alternating Series Test

> *Definition:*
> $$
> (u_n>0)\and(n>N,u_{n+1}\leq u_n)\and(u_n\rightarrow 0)\vdash (\sum_{n=0}^{\infty}u_n\text{Convergence})
> $$
> 