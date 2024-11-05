**Semantic Entailment**

**Definition of Entail**

$((\forall~v)\rightarrow((\Sigma^v=1)\rightarrow(A^v\rightarrow1)))\rightarrow(\Sigma$ &#8872;$A)$

**Definition of Not Entail**

$((\exist~v)\rightarrow((\Sigma^v\rightarrow1)\and(A^v\rightarrow 0)))\rightarrow(\Sigma$&#8877;$A)$

> Example 
>
> Prove that $\neg p$ &#8872; $((p\and (\neg q))\rightarrow (p\and q))$

I will use three ways to prove it.

*Proof 1:*

Here is the truth table.

| Truth Value of p | Truth Value of $\neg p$ | Truth Value of $((p\and (\neg q))\rightarrow (p\and q))$ |
| :--------------: | :---------------------: | :------------------------------------------------------: |
|        1         |            0            |                        Don't Care                        |
|        0         |            1            |                            1                             |

So according to the definition of the entail relationship we can prove that $\neg p$ &#8872; $((p\and (\neg q))\rightarrow (p\and q))$.

*Proof 2:*

Here is the degeneration of the right part of the statement.
$$
\begin{aligned}
&((p\and (\neg q))\rightarrow (p\and q))\\
=&(\neg((p\and (\neg q)))\or(p\and q)\\
=&((\neg p)\or q)\or(p\and q)\\
=&(((\neg p)\or q)\or p)\and(((\neg p)\or q)\or q)\\
=&((\neg p)\or q)\or q\\
=&(\neg p)\or q
\end{aligned}
$$
So we can have the truth table.

| Truth Value of $p$ | Truth Value of $\neg p$ | Truth Value of $(\neg p)\or q$ |
| :----------------: | :---------------------: | :----------------------------: |
|         1          |            0            |               q                |
|         0          |            1            |               1                |

*Proof 3:*

This time we will prove by contradiction.

If I want to prove that $((p\and (\neg q))\rightarrow (p\and q)) $ is true whenever that $\neg p $ is true, then we just need to prove that when $\neg p$, and $((p\and (\neg q))\rightarrow (p\and q))$ is wrong!

Which can be expressed by the following formula $\neg p\and \neg(((p\and (\neg q))\rightarrow (p\and q)))$ is always false.

Here we will have the calculation.
$$
\begin{aligned}
&\neg p\and \neg(((p\and (\neg q))\rightarrow (p\and q)))\\
=&\neg p\and \neg(((\neg(p\and (\neg q)))\or (p\and q)))\\
=&\neg p\and (\neg((\neg p) \or q)\or (p\and q))\\
=&\neg p\and (p\and(\neg q))\and ((\neg p)\or (\neg q))\\
=&\neg p\and p\and(\neg q)\and ((\neg p)\or (\neg q))\\
=&0
\end{aligned}
$$
  So we proved that when the premises are all right we will have the conclusion definitely to be correct.

>  [!TIP]
>
> You can also prove everything by contradiction.

> Example
>
> Prove that $A\rightarrow B,B\rightarrow C$ &#8872; $A\rightarrow C$

I want to prove it by contradiction this time.

*Proof 1:*

Then we will have to find that if this entail failed then we can find that there is possibility that when the left hand side are all true and the right hand side is false.

So there should be possibility that $(A\rightarrow B)\and (B\rightarrow C)\and(\neg(A\rightarrow C))$ to be true.

So let us just degenerate the formula.
$$
\begin{aligned}
&(A\rightarrow B)\and (B\rightarrow C)\and(\neg(A\rightarrow C))\\
=&((\neg A)\or B)\and((\neg B)\or C)\and(\neg((\neg A)\or C))\\
=&((\neg A)\or B)\and(\neg B))\or((\neg A)\or B)\and C)\and(\neg((\neg A)\or C))\\
=&((\neg A)\and(\neg B))\or(B\and(\neg B))\or((\neg A)\or B)\and C)\and(\neg((\neg A)\or C))\\
=&\neg(A\or B)\or((\neg A)\or B)\and C)\and(\neg((\neg A)\or C))\\
=&\neg(A\or B)\or((\neg A)\and C)\or(B \and C)\and(A\and(\neg C))\\
=&((\neg A)\and(\neg B))\or((\neg A)\and C)\or(B \and C)\and(A\and(\neg C))\\
=&(((\neg A)\and(\neg B))\or (\neg A))\and(((\neg A)\and(\neg B))\or C)\or(B \and C)\and(A\and(\neg C))\\
=&((\neg A) \or(\neg A))\and ((\neg A)\or (\neg B)) \and(((\neg A)\and(\neg B))\or C)\or(B \and C)\and(A\and(\neg C))\\
=&(\neg A)\and ((\neg A)\or (\neg B)) \and(((\neg A)\and(\neg B))\or C)\or(B \and C)\and(A\and(\neg C))\\
=&((\neg A)\and(\neg A))\or((\neg A)\and(\neg B))\and(((\neg A)\and(\neg B))\or C)\or(B \and C)\and(A\and(\neg C))\\
=&
\end{aligned}
$$
I think that struggling with this kind of calculation can be killing, so there is another way t of  finish this question by contradiction.

*Proof 2:*

If the relationship between the premises and conclusions are not entail, which is semantically entailing, then we will find that for some truth value the evaluation of the conclusion is false when the premises are all true.

Here is the truth table.

|  A   |  B   |  C   | A$\rightarrow$B | B$\rightarrow$C | A$\rightarrow$C | Premise | Conclusion |
| :--: | :--: | :--: | :-------------: | :-------------: | :-------------: | :-----: | :--------: |
|  1   |  1   |  0   |        1        |        0        |        0        |    0    |     0      |
|  1   |  0   |  0   |        0        |        1        |        0        |    0    |     0      |

So now we find that when the conclusion is wrong there is no possibility that the premise is correct.

**How to prove $\Sigma$ &#8877;A**

We will just need to find the counter example.

> Example
>
> Prove that $\neg(A\leftrightarrow B)\or C,B\and(\neg C)$ &#8877; $(\neg A)\and(B\leftrightarrow C)$ is true.

 To do this I will find the counter example that the conclusion is wrong when the premises is correct.

We have to make the premises all correct that means that B has to be correct, and also C has to be false, also we have to let $A\leftrightarrow B$ to be false, that means that A is wrong, so now we will find that only when A=0, B=1, C=0 then the premises are all correct. Now we need to check the conclusions.

Now we have the conclusion is 
$$
\begin{aligned}
&(\neg A)\and(B\leftrightarrow C)\\
=&(\neg 0)\and(1\leftrightarrow 0)\\
=&1\and0\\
=&0
\end{aligned}
$$
So we find the counter example to be 

|  A   |  B   |  C   |
| :--: | :--: | :--: |
|  0   |  1   |  0   |

**Semantically Entailment**

> $A$ &#8872; $B$ if and only if $A\rightarrow B$ is tautology.

*Proof:*

I will separate the argument into two parts to proof.

The first part is

$A$ &#8872; $B$ if $A\rightarrow B$ is tautology.

We know that when $A\rightarrow B$ is tautology, then we will have whenever A is right we will all have B should be right, too.  Then the statement $A$ &#8872; $B$ will be correct by the definition.

The second part is 

$A$ &#8872; $B$ only if $A\rightarrow B$ is tautology.

We will have that when A &#8872; $B$, then we will know that when $A$ is 1, then $B$ will be 1.

So let us have the truth table, the only information we have is that when $A$ is 1 then $B$ will also be 1.

|  A   |  B   | A$\rightarrow$B |
| :--: | :--: | :-------------: |
|  1   |  1   |        1        |
|  0   |  1   |        1        |
|  0   |  0   |        1        |

So we will find that under any truth value, the output of $A\rightarrow B$ will always be true.

Then it will be tautology.

**Logical Equivalence**

> A $\equiv$ B if and only if both A &#8872; B and B &#8872; A.

We will prove that by separate it into two parts.

The first part is A $\equiv$ B if both A &#8872; B and B &#8872; A.

We have to make discussion about the truth value under every possibility.

When A is 1, according to the A &#8872; B, we will have that B have to be 1.

When A is 0, according to the B &#8872; A, we will have that B have to be 0.

So we proved that A is equivalence to B.

**Empty Set**

> $\varnothing$ &#8872; A, that means A is tautology.

This is absolutely true.

**Theorem**

> A~1~, ..., A~n~ &#8872; A if and only if $\varnothing$ &#8872; $A_1\and...\and A_n \rightarrow A$.

I will separate the question into two parts.

The first part is A~1~, ..., A~n~ &#8872; A if $\varnothing$ &#8872; $A_1\and...\and A_n \rightarrow A$.

We have that when $A_1\and...\and A_n \rightarrow A$, we will have when $A_1\and...\and A_n$ is true, then A is true, which is just the definition of the entailment.

Then the second part is A~1~, ..., A~n~ &#8872; A only if $\varnothing$ &#8872; $A_1\and...\and A_n \rightarrow A$.

When A~1~, ..., A~n~ &#8872; A we will have that when A~1~, ..., A~n~ is 1, then A will also be 1, which just satisfies everything in the statement $A_1\and...\and A_n \rightarrow A$.

