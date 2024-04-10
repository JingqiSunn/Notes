**Logical Connectives**

There are five logic connections in our frequently daily use.

|      Symbol       |    Name     |
| :---------------: | :---------: |
|      $\neg$       |  Negation   |
|      $\and$       | Conjunction |
|       $\or$       | Disjunction |
|   $\rightarrow$   | Implication |
| $\leftrightarrow$ | Equivalence |

But there are lot more logical connection other than them, also there is no need to have such a lot of logic connections.

**The Total Number for N-Dimension Logic Connection**

> For any n $\geq$ 1, there are $2^{2^n}$ different n-ary connective symbols.

*Proof:*

Logical connection actually represent a relationship between set of truth value and an output of 0 and 1 values.

Let us first think of why two logical connections are different, that is probably when the input are the same, however the output are different.

I will make an example in the binary situation.

We want the logic connection in $A\star B$, then we have to examine 4 kinds of input.

|  A   |  B   |
| :--: | :--: |
|  1   |  0   |
|  1   |  1   |
|  0   |  0   |
|  0   |  1   |

We will notice that as long as under one kind of the input, the output is different, then we can say that those two logic connections are different.

So we think that when it is a connection between n events, then there will be $2^n$ kinds of different output.

That means there is totally $2^{2^n}$ kinds of different output to all the sets of truth value input.

So there are $2^{2^n}$ kinds of different logic connection in n objects situation.

**Adequate Set**

> This time I will prove that we only need two connections then we will have all kind of connections, I will give my example by $\neg$ and $\and$.

*Proof:*

We have already have $\neg$ and $\and$, so we have the De Morgan Theorem, that $p\or q = \neg((\neg p )\and(\neg q))$

This means that we can express the binary connection $\or$ now.

And we still have implication and equivalence these two kinds of binary connections.

I will continue to find the implication.

According to the rule that we learnt before, we know that $p\rightarrow q = (\neg p)\or q$, which means that we can actually express the binary connection implication by the previous several binary and unary connections.

The last one is the equivalence.

According to the definition of the equivalence we know that $p \leftrightarrow q = (p\rightarrow q)\and(q\rightarrow p)$.

So that we now can express all the unary and binary connections by the two basic one we have.

Now I am going to prove that we can express all the logic relationship by these things.

I will use the induction rule.

Suppose we can express p and q, which are two complete formula, then we will find that there can only be several choice for creating new logical relationship, which are $\neg p$, $\neg q$ and $p\star q$.

And we have finished expressing all the binary and unary connections by the two basic connection negation and conjunction.

So we proved that we can express all the logic expressions with the help of negation and conjunction, that means negation and conjunction are an adequate set.