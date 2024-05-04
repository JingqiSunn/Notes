#### Lecture 9

##### Resolution Inference Rule

$$
\frac{(\alpha \or p)~~~~~((\neg p)\or \beta)}{(\alpha\or \beta)}
$$

###### Unit Resolution

$$
\frac{(\alpha \or p)~~~~~(\neg p)}{\alpha}
$$

###### Contradiction

$$
\frac{p~~~~~(\neg p)}{\bot}
$$

##### Proof & Entailment

**Soundness**

*Definition:*

$(\Sigma\vdash A)\rightarrow (\Sigma $&#8872;$A)$

> [!NOTE]
>
> If a proof system is not sound, the it is pretty much useless.

**Completeness**

*Definition:*

$(\Sigma $&#8872;$A)\rightarrow (\Sigma\vdash A)$

**Soundness of Natural Deduction System**

We will use the induction proof.