#### Lecture 5

#### Gaussian Discriminant Analysis(GDA) and Naive Bayes

##### Discriminative  Learning Algorithm

###### Goal 

Learn $P(Y^{(i)}\Big|X^{(i)})$ or learn $h_\Theta(X^{(i)})=\begin{cases}0\\1\end{cases}$ directly.

> [!NOTE]
>
> In contrast, in the **generative learning algorithm**. we will learn $P(X^{(i)}\Big|Y^{(i)})$
>
> But if we can do calculate it, then according to the Bayes Rule, we have that 
> $$
> P(Y^{(i)}=1\Big|X^{(i)})=\frac{P(X^{(i)}\Big|Y^{(i)}=1)\cdot P(Y^{(i)}=1)}{P(X^{(i)}\Big|Y^{(i)}=1)\cdot P(Y^{(i)}=1)\cdot P(X^{(i)}\Big|Y^{(i)}=0)\cdot P(Y^{(i)}=0)}
> $$

##### Gaussian Discriminant Analysis

###### Background

Suppose $X^{(i)}\in R^{n\times 1}$(drop $X^{(i)}_0=1$ convention), and assume that $P(X^{(i)}\Big|Y^{(i)})$ is obey a multi-variable Gaussian Distribution.

> [!NOTE]
>
> **Multi-variable Gaussian Distribution**
> $$
> z\sim N(\mu,\epsilon),z\in R^n,\mu\in R^n,\epsilon\in R^{n\times n}
> $$
>
> $$
> E(z)=\mu
> $$
>
> $$
> Cov(z)=E[(z-\mu)(z-\mu)^T]=E(zz^T)-E(z)\cdot (E(z))^T
> $$
>
> $$
> P(z)=\frac{1}{(2\pi)^{\frac{n}{2}}|\epsilon|^{\frac{1}{2}}}\exp(-\frac{1}{2}(z-\mu)^T\epsilon^{-1}(z-\mu))
> $$

###### GDA Model

$$
P(X^{(i)}\Big| Y^{(i)}=0)=\frac{1}{(2\pi)^{\frac{n}{2}}|\epsilon|^{\frac{1}{2}}}\exp(-\frac{1}{2}(X^{(i)}-\mu_0)^T\epsilon^{-1}(X^{(i)}-\mu_0))
$$

$$
P(X^{(i)}\Big| Y^{(i)}=1)=\frac{1}{(2\pi)^{\frac{n}{2}}|\epsilon|^{\frac{1}{2}}}\exp(-\frac{1}{2}(X^{(i)}-\mu_1)^T\epsilon^{-1}(X^{(i)}-\mu_1))
$$

$$
P(Y^{(i)}=1)=\phi
$$

$$
P(Y^{(i)})=\phi^{Y^{(i)}}(1-\phi)^{1-Y^{(i)}}
$$

There are totally four variables $\mu_1$, $\mu_2$, $\phi$ and $\epsilon$. We usually use the same covariance matrix, the above formulas supports you to use the Bayes Transformation.

###### The Training of Gaussian Discriminant Analysis Model

- Training Set
  $$
  \{X^{(i)},Y^{(i)}\}_{i=1}^m
  $$

- Joint Likelihood
  $$
  \begin{aligned}
  L(\phi,\mu_0,\mu_1,\epsilon)
  &=\prod_{i=1}^{m}P(X^{(i)},Y^{(i)};\phi,\mu_0,\mu_1,\epsilon)\\
  &=\prod_{i=1}^{m}\Big(P(X^{(i)}\Big|Y^{(i)};\phi,\mu_0,\mu_1,\epsilon)\cdot P(Y^{(i)};\phi,\mu_0,\mu_1,\epsilon)\Big)\\
  \end{aligned}
  $$

  > [!IMPORTANT]
  >
  > The main difference is that in the former models, the likelihood function will always use the conditional probability like $P(Y^{(i)}\Big|X^{(i)})$

  Here you have to choose the variables to maximize the log likelihood, which is to
  $$
  \text{Find the value of }\phi,\mu_0,\mu_1,\epsilon\text{ to maximize the value of }l(\phi,\mu_0,\mu_1,\epsilon)= \log(L(\phi,\mu_0,\mu_1,\epsilon))
  $$

We have 
$$
\phi=\frac{\sum_{i=1}^mY^{(i)}}{m}=\frac{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}{m}
$$

$$
\mu_0=\frac{\sum_{i=1}^m\iota\{Y^{(i)}=0\}X^{(i)}}{\sum_{i=1}^m\iota\{Y^{(i)}=0\}}
$$

$$
\mu_1=\frac{\sum_{i=1}^m\iota\{Y^{(i)}=1\}X^{(i)}}{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}
$$

$$
\epsilon = \frac{1}{m}(X^{(i)}-\mu_{Y^{(i)}})(X^{(i)}-\mu_{Y^{(i)}})^T
$$

###### Prediction

$$
\arg(\max_y P(Y^{(i)}\Big| X^{(i)}))=\arg(\max_y\frac{P(X^{(i)}\Big|Y^{(i)})P(Y^{(i)})}{P(X^{(i)})})=\arg(\max_yP(X^{(i)}\Big|Y^{(i)})P(Y^{(i)}))
$$

##### Compare Generalized Discriminant Analysis to Logic Regression

###### What Generalized Discriminant Analysis 

For fixed $\phi,\mu_0,\mu_1,\epsilon$, lets plot $P(Y^{(i)}=1\Big| X^{(i)};\phi,\mu_0,\mu_1,\epsilon)$ as a formula of $X^{(i)}$.
$$
P(Y^{(i)}=1\Big| X^{(i)};\phi,\mu_0,\mu_1,\epsilon)=\frac{P(X^{(i)}\Big| Y^{(i)}=1;\mu_1,\epsilon)P(Y^{(i)}=1;\phi)}{P(X^{(i)};\phi,\mu_0,\mu_1,\epsilon)}
$$

> [!NOTE]
>
> You can always find that the shape of the function of $P(Y^{(i)}=1\Big| X^{(i)};\phi,\mu_0,\mu_1,\epsilon)$​ is always sigmoid function, which is one great connection between the Generalized Discriminant Analysis and the Logic Regression.

###### Generalized Discriminant Analysis

Assume
$$
X^{(i)}\Big| Y^{(i)}=0\sim N(\mu_0,\epsilon)
$$

$$
X^{(i)}\Big| Y^{(i)}=1\sim N(\mu_1,\epsilon)
$$

$$
Y^{(i)}\sim \text{Bernoulli}(\phi)
$$

###### Logistic Regression

Assume
$$
P(Y^{(i)}=1\Big| X^{(i)})=\frac{1}{1+e^{-\Theta^TX^{(i)}}}
$$

> [!NOTE]
>
> Considering the fact which has been mentioned before that if a set of data obeys the assumption in the Generalized Discriminant Analysis, then the function of $P(Y^{(i)}=1\Big| X^{(i)};\phi,\mu_0,\mu_1,\epsilon)$​​ will always be the sigmoid function. That means the assumption proposed by the Generalized Discriminant Analysis is a **Stronger** assumption.
>
> **Conclusion:**
>
> So if the assumption of Generalized Discriminant Analysis is right for the data set, then the performance will be lot better than the logistic regression. However, if the assumption of Generalized Discriminant Analysis is incorrect there is still chance that the assumption of logistic regression is correct.
>
> For example if we have the fact below
> $$
> X^{(i)}\Big| Y^{(i)}=0\sim \text{Poisson}(\lambda_0)
> $$
>
> $$
> X^{(i)}\Big| Y^{(i)}=1\sim \text{Poisson}(\lambda_1)
> $$
>
> $$
> Y^{(i)}\sim \text{Bernoulli}(\phi)
> $$
>
> It turns out that this kind of assumption also implies that $P(Y^{(i)}=1\Big| X^{(i)};\phi,\mu_0,\mu_1,\epsilon)$ is logistic.

##### Naive Bayes

###### Background

The problem is to classify the emails based on the theme they have.

###### Difficulty

How to define the *feature vector* $X^{(i)}$?

###### The Step to Find the Feature Vector

1. Find a fixed number of words with top frequency in the email, for example about 10000 words concluding buy, computer...

2. If the word appeared in the specific email, then you use 1 to represent. So that 
   $$
   X\in\{0,1\}^n
   $$

   $$
   X_i = \iota\{\text{word $i$ appears in email}\}
   $$

   

###### Assumptions

We assume that $X_i$ are conditionally independent given $Y^{(i)}$
$$
\begin{aligned}
P(X_1,...,X_{10000}\Big| Y)
&=P(X_1\Big| Y)P(X_2\Big|X_1, Y)P(X_3\Big|X_1,X_2, Y)...P(X_{10000}\Big|..., Y)\\
&=^{assume} P(X_1\Big| Y)P(X_2\Big| Y)P(X_3\Big| Y)...P(X_{10000}\Big|Y)\\
\end{aligned}
$$

###### Parameter

$$
\phi_{j\Big| Y^{(i)}=1}=P(X^{(i)}_j=1\Big| Y^{(i)}=1)
$$

$$
\phi_{j\Big| Y^{(i)}=0}=P(X^{(i)}_j=1\Big| Y^{(i)}=0)
$$

$$
\phi_y = P(Y^{(i)}=1)
$$

###### Joint Likelihood

$$
L(\phi_y,\phi_{j\Big| Y^{(i)}})=\prod_{i=1}^m P(X^{(i)},Y^{(i)};\phi_y,\phi_{j\Big| Y^{(i)}})
$$

###### Result

$$
\phi_y=\frac{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}{m}
$$

$$
\phi_{j\Big|Y^{(i)}=1}=\frac{\sum_{i=1}^m\iota\{X_j^{(i)}=1,Y^{(i)}=1\}}{\sum_{i=1}^m\iota\{Y^{(i)}=1\}}
$$

