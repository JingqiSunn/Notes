## CS104/CS108 

## Introduction to Mathematical Logic Final Review

### JingqiSUN

#### Logic 

> The basic question studied in logic

What conclusion(s) can be drawn with absolute certainty from a particular set of premises.

> Math term

1. Premise = Axiom
2. Conclusion = Theorem/Lemma
3. Reasoning = Proof

> Reductio ad Absurdum

A method of proving the falsity of a statement by assuming its truth and then deriving a contradiction.

> Traditional Logic

- Originate: Ancient Greek
- Where explicit analyses of principles developed: China, India, and Greece
- Modern treatment descend from: Greek tradition, particularly Aristotelian Logic, core of which is the syllogism

> Syllogism

1. Major premise: A broad statement or generalization
2. Minor premise: A specific statement related to or within the scope of the major premise
3. Conclusion:  A statement that logically follows from the combination of the major and minor premises

*Example One*

1. Major premise: All humans are mortal
2. Minor premise: Socrates is a human
3. Conclusion: Socrates is mortal

*Example Two*

1. Major premise: Metal conducts electricity.
2. Minor premise: Copper is a metal.
3. Conclusion: Copper conducts electricity.

> [!NOTE]
>
> Truth: Statements
>
> Validity: Arguments/Reasoning
>
> - Valid reasoning does not guarantee a true conclusion.
> - Invalid reasoning does not guarantee a false conclusion.
> - A false conclusion does not guarantee a invalidity.
> - True premises and a true conclusion together do not guarantee a validity.

> Ambiguity of Natural Language

- The similarity in natural language forms does not guarantee that the logical forms are identical
- Different natural language forms may have the same logical form

*Example One*

1. A student from Class A is the captain of the soccer team 
2. x knows a student from Class A .
3. x knows the captain of the soccer team.

> Early Phase of Modern Mathematical Logic

- Constructing a ”universal language”
- Constructing ”calculus of reasoning”

> [!NOTE]
>
> The origins of modern mathematical logic are often attributed to Leibniz.
>
> George Boole and A. De Morgan presented systematic mathematical treatments of propositional logic.
>
> Gottlob Frege and B. Russel developed logic with quantifiers.
>
> Great Logicians: Bertrand Russell, David Hilbert, Gerhard Gentzen, Kurt Gödel, and Alfred Tarski.

> Terms in Reasoning

- A reasoning consists of a finite number of declarative sentences, where some sentences infer another sentence. We will always use "Therefore" to represent this kind of relationship
- Declarative sentences: Used for declarations or statements, characterized by being true or false 

> [!NOTE]
>
> Reasoning concerns the abstract meanings of sentences, referred to as propositions.

> What is Reasoning

Reasoning is a set of propositions. conclusion is deduced/derived from premises. We use rules for deduction/derivation.

> Rule for Reasoning

1.  All $X$ is $Y$. $a$ is $X$. Therefore, $a$ is $Y$.
2.  If $P$ then $Q$; $P$; Therefore $Q$​.
3. If $P$ then $Q$; Not $Q$; Therefore not $P$.

> Formal Languages

1. Digital sequence understood by computer
2. Programme Language
3. Propositional Logic
4. First-Order Logic
5. Modal Logic

#### Prerequisite Knowledge 

##### Set

> Definition

A collection of objects

> Element of the Set

An object of the set

> Intension

Its description or defining properties

> Extension

Its members or contents

> Axiom of Extension

The two sets A and B are equal if and only if A and B have the same members.

> [!NOTE]
>
> So the intension are not such important when you are dealing with the equality of two sets.

*Examples*

- $$
  \{a\}=\{a,a\}
  $$

- $$
  \{a,b\}=\{b,a\}=\{a,b,b\}
  $$

##### Subset

> Definition

A set $A$ is a subset of a set $B$ if all elements of $A$ are also elements of $B$​.

> Notation

$A\subseteq B$

##### Proper Subset

> Definition

$A\subseteq B$ and $A\neq B$

> Notation

$A\subset B$

##### Power Set

> Definition

- $$
  p(\{a,b,c\})=\{\{a,b,c\},\{a,b\},\{a,c\},\{b,c\},\{a\},\{b\},\{c\},\emptyset\}
  $$

- $$
  p(\emptyset)=\{\emptyset\}
  $$

- $$
  p(\{\emptyset\})=\{\{\emptyset\},\emptyset\}
  $$

##### Set Operations

###### Union

> Definition

$$
A\cup B:\{x|x\in A \text{ or }x\in B\}
$$

###### Intersection

> Definition

$$
A\cap B:\{x|x\in A \text{ and }x\in B\}
$$

###### Difference

> Definition

$$
A-B:\{x|x\in A \text{ and }x\notin B\}
$$

##### Set Property

1. $$
   A\subseteq B \leftrightarrow A\cap B=A
   $$

2. $$
   A\subseteq B \leftrightarrow A\cup B=B
   $$

##### n-tuples

> Definition

An n-tuple is a tuple of n elements, where n is a non-negative integer.

###### Identity of two n − tuples

$$
<x_1,x_2,...,x_m>=<y_1,y_2,...,y_n>\leftrightarrow m=n,x_1=y_1,x_2=y_2,...,x_m=y_n
$$

##### Cartesian Product

> Definition

$$
A_1\times A_2\times ...\times A_n: \{<x_1,x_2,...,x_n>|x_1\in A_1,x_2\in A_2,...x_n\in A_n\}
$$

> [!NOTE]
>
> The results are ordered pairs.
>
> Denote as $A^n$ if $A_1=A_2=...=A_n=A$.

##### Binary Relationship

> Definition

A binary relation $R$ over sets $X$ and $Y$ is a subset of Cartesian product $A$ $\times$ $B$

> Denotation

$$
R\subseteq A\times B
$$

##### n_ary Relationship

> Definition

If $R\subseteq A^n$, $R$ is denoted as an n-ary relation over $A$.

##### Equivalence Relationship

- Reflexive: $\forall x\in A,xRx$
- Symmetric: $\forall x,y\in A,xRy\rightarrow yRx$
- Transitive: $\forall x,y,z\in A,xRy,yRz\rightarrow xRz$

> Definition

R is an equivalence relation on $A$ if $A$ is nonempty and $R$ is reflexive, symmetric and transitive.

*Examples*

- ”$=$” is an equivalence relation on $\N$​
- $\{<x,y>|\text{ x and y are contemporaries}\}$ is an equivalence relationship on $\{x|x \text{ is human}\}$
- $\{<x,y>|x \text{ is parallel to } y\}$ is an equivalence relation on the set of lines in a plane.

###### Equivalence Class

> Definition

$$
[x]_R=\{y\in A|xRy\}
$$

> Theorem

1. If R is an equivalence relation over $A$, then every $a \in A$​ belongs to exactly one equivalence class.
2. Given an equivalence relation on set A, the collection of equivalence classes forms a partition of set A.

##### Partial Order Relationship

A binary relation $R$ on a set $A$ is antisymmetric if for all $x, y \in A$，if $xRy$ and $yRx$, then $x=y$​.

> Definition

A binary relation R on a set A is a partial order if R is reflexive, antisymmetric, and transitive

> Other Conceptions

- For $x \in A$, if there doesn’t exist another $y \in A$ such that $yRx$, then $x$​ is the minimal element of this partial order.
- For $x \in A$, if there doesn’t exist another $y \in A$ such that $xRy$, then $x$ is the maximal element of this partial order.

##### Total Order Relationship(Linear)

> Definition

Formally, a partial order relation $R$ on a set $A$ is a total order (linear order), if for any $x, y \in A$, either $xRy$ or $yRx$.

> [!NOTE]
>
> Intuitively, a total order or linear order is a partial order in which any two elements are comparable.

##### Function

> [!NOTE]
>
> Relationship is not enough because it always performs one to many relationship, however in actual world, one to one relationship is very common.

> Definition

A function from a set $X$ to a set $Y$ is a binary relation $R$ between $X$ and $Y$ that satisfies the two following conditions:

- For any $x \in X$, there exists $y \in Y$ such that $xRy$
- If $y, z \in Y$ such that $xRy$ and $xRz$​, then y = z.

> Notation

$$
f:A\rightarrow B
$$

- Domain: $A$
- Codomain: $B$
- Range: A subset of $B$
- Always use $f(x)=y$ to denote $<x,y>=f$

##### n-ary Function

> Definition

If the domain of f is the Cartesian product $A_1 \times A_2 \times ... \times A_n(n ≥ 1)$, then $f$ is called an n-ary function.

> Other Conceptions

- An n-ary function maps ordered n-tuples from its domain to elements in its codomain.
- $f : A_n \rightarrow A$ is called an n-ary function in A.

##### Injective Function

> Definition

If each element of the codomain is mapped to by at most one element of the domain

##### Surjective Function

> Definition

If each element of the codomain is mapped to by at least one element of the domain

##### Bijective Function

> Definition

If each element of the codomain is mapped to by exactly one element of the domain. That is, the function is both injective and surjective.

##### Proof by Induction

> Template for Proof by Induction

- Base Case
- Induction Hypothesis
- Inductive Step

#### General Introduction of Propositional Logic

##### Proposition

> Definition

A proposition is a declarative sentence that can be judged as either true or false

##### Atomic Proposition

> Definition

A proposition that does not contain any smaller part that is still a proposition is called an atomic proposition

##### Compound Proposition

A proposition that involves the assembly of multiple propositions is called a compound proposition

##### Logical Connectives

> Definition

Words that connect multiple propositions to form a compound proposition are called logical connectives.

- and
- not
- or
- if...then...
- if and only if

##### Symbols

- Atomic Proposition
  $$
  p,q,r,...
  $$

- Compound Proposition
  $$
  A,B,C,...
  $$

- Connectives

  |    Connectives    |    Name     |
  | :---------------: | :---------: |
  |      $\neg$       |  Negation   |
  |      $\and$       | Conjunction |
  |       $\or$       | Disjunction |
  |   $\rightarrow$   | Implication |
  | $\leftrightarrow$ | Equivalence |

##### Language in General

- Syntax
- Semantics

##### Propositional Logic

###### Alphabet

- Atomic Proposition

  $p,q,r,...$

- Logical connectives

  $\and,\or,\neg,\rightarrow,\leftrightarrow$

- Punctuations

  $(,)$

###### Expression

> Definition

Finite strings of symbols

> Length of the Expression

The number of occurrences of symbols in it

> Empty Expression

An expression of length 0, denoted by $\lambda$

> Equality of Expression

Two expressions $u$ and $v$ are equal if they are of the same length and have the same symbols in the same order

###### Formula

The well-formed formulas of propositional logic are expressions which we obtain by using the construction rules, and only those, finitely many times.

- Atom:  Every propositional atom $p, q, r, ...$ is a well-formed formula.
- $\neg$: If $\phi$ is a well-formed formula, then so is $(\neg \phi)$. 
- $\and$: If $\phi$ and $\psi$ are well-formed formulas, then so is $(\phi \and \psi)$. 
- $\or$: If $\phi$ and $\psi$ are well-formed formulas, then so is $(\phi \or \psi)$. 
- $\rightarrow$: If $\phi$ and $\psi$ are well-formed formulas, then so is $(\phi \rightarrow \psi)$.  
- $\leftrightarrow$: If $\phi$ and $\psi$ are well-formed formulas, then so is $(\phi \leftrightarrow \psi)$.  

###### Parse Tree

> Complete Example

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619170302442.png" alt="image-20240619170302442" style="zoom:33%;" />

> Simplified Example

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619170330951.png" alt="image-20240619170330951" style="zoom:33%;" />

> Theorem

1. An expression of $L^P$ is a well-formed formula if and only if there is a parse tree of it.
2. Each well-formed formula of $L^P$​ has a unique parsing tree.
3. Well-formed formulas of $L^P$ are non-empty expressions.
4. Every well-formed formula of $L^P$​ has an equal number of opening and closing brackets.
5. Every proper prefix of a well-formed formula in $L^P$​ has more opening brackets than closing brackets.
6. Similarly, every proper suffix of a well-formed formula in $L^P$​ has more closing brackets than opening brackets.
7. Hence, proper prefix and proper suffix are not formulas in $L^P$.

###### Subformula

> Definition

A formula $G$ is a subformula of formula $F$ if $G$ occurs within $F$. $G$ is a proper subformula of $F$ if $G \neq F$. 

The nodes of the parse tree of $F$ form the set of subformulas of $F$.

###### Structures of Formula

1. $$
   \lambda u= u\lambda =u
   $$

2. $v$ is a segment of $u$ if $u=w_1vw_2$ 

3. $v$ is a proper segment of $u$ is $v$ is non-empty and $v \neq u$, $u=w_1vw_2$​ 

4. If $u = vw$, where $u$, $v$, $w$ are expressions, then $v$ is an initial segment (prefix) of $u$, $w$ is a terminal segment (suffix) of $u$.

5. If $u = vw$, where $u$, $v$, $w$ are expressions, and $v$, $w$ are non-empty, then $v$ is an proper prefix of $u$, $w$ is a proper suffix of $u$.

###### Precedence

- Each connective on the left has priority over those on the right $\neg,\and,\or,\rightarrow,\leftrightarrow$
- Parentheses take the highest precedence
- Connectives are assumed to associate to the right (right associative), i.e., first group the rightmost occurrence. For example, $p\rightarrow q \rightarrow r$ means $p \rightarrow (q \rightarrow r)$

###### Truth Table

| $p$  | $\neg p$ |
| :--: | :------: |
|  1   |    0     |
|  0   |    1     |

| $p$  | $q$  | $p\and q$ |
| :--: | :--: | :-------: |
|  0   |  0   |     0     |
|  0   |  1   |     0     |
|  1   |  0   |     0     |
|  1   |  1   |     1     |

| $p$  | $q$  | $p\or q$ |
| :--: | :--: | :------: |
|  0   |  0   |    0     |
|  0   |  1   |    1     |
|  1   |  0   |    1     |
|  1   |  1   |    1     |

| $p$  | $q$  | $p\rightarrow q$ |
| :--: | :--: | :--------------: |
|  0   |  0   |        1         |
|  0   |  1   |        1         |
|  1   |  0   |        0         |
|  1   |  1   |        1         |

###### Truth Valuation

$$
Atom(L^P)\rightarrow \{0,1\}
$$

$$
p^v\in\{0,1\}
$$

###### Truth Value for a Formula

1. $$
   p^v=\{0,1\}
   $$

2. $$
   (\neg A)^v=\cases{1\quad\quad if\quad A^v=0\\0\quad\quad else}
   $$

3. $$
   (A\and B)^v=\cases{1\quad\quad if\quad A^v=B^v=1\\0\quad\quad else}
   $$

4. $$
   (A\or B)^v=\cases{1\quad\quad if\quad A^v=1\quad or\quad B^v=1\\0\quad\quad else}
   $$

5. $$
   (A\or B)^v=\cases{1\quad\quad if\quad A^v=0\quad or\quad B^v=1\\0\quad\quad else}
   $$

6. $$
   (A\or B)^v=\cases{1\quad\quad if\quad A^v=B^v\\0\quad\quad else}
   $$

###### Tautology

> Definition

$$
A^v\equiv1
$$

###### Contradiction

$$
A^v\equiv0
$$

###### Satisfiable

$$
\exist A^v=1
$$

###### Valuation Tree

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619185950502.png" alt="image-20240619185950502" style="zoom:33%;" />

###### Satisfiability of Sets of Formulas

> Definition

$\Sigma$ is satisfiable if and only if there is some valuation $v$ such that $\Sigma ^v=1$; we say $v$ satisfies $\Sigma$

###### Logical Equivalence

> Definition

- $A ^v = B ^v $for every truth valuation $v$
- $A$ and $B$​ must have the same final column in their truth tables.
-  $A \leftrightarrow B$ is a tautology.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619190740967.png" alt="image-20240619190740967" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619190808043.png" alt="image-20240619190808043" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240619190911097.png" alt="image-20240619190911097" style="zoom:33%;" />

###### Substitution

> Definition

$B$ is a substitution instance of $A$ if and only if $B$ may be obtained from $A$ by substituting formulas for propositional variables in $A$, replacing each occurrence of the same variable by an occurrence of the same formula.

> Theorem

1. $A, B ∈ Form(L^P )$. If $A$ is a tautology, and $B$ is a substitution instance of $A$, then $B$​ is again a tautology.
2. $A \in Form(L^P )$. A contain a subformula $C$. If $C \equiv D$, then replacing some occurrences of the subformula $C$ in $A$ with $D$ to obtain the formula $B$, then $A \equiv B$.

###### Semantic Entailment

> Definition of Entail

$((\forall~v)\rightarrow((\Sigma^v=1)\rightarrow(A^v\rightarrow1)))\rightarrow(\Sigma$ &#8872;$A)$

> Definition of Not Entail

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

> [!NOTE]
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

###### Logical Connectives

There are five logic connections in our frequently daily use.

|      Symbol       |    Name     |
| :---------------: | :---------: |
|      $\neg$       |  Negation   |
|      $\and$       | Conjunction |
|       $\or$       | Disjunction |
|   $\rightarrow$   | Implication |
| $\leftrightarrow$ | Equivalence |

But there are lot more logical connection other than them, also there is no need to have such a lot of logic connections.

*The Total Number for N-Dimension Logic Connection*

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

###### Adequate Set

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

##### Hilbert-Style Proof System(Optional)

> [!NOTE]
>
> We know that every proof system has language part and the inference part, so this time we will develop everything in this structure.

**Language Part**

1. Alphabet

   $\Sigma = \{(,),\neg,\rightarrow,p,q,r,...\}$

2. Formula

   - Atoms p, q, r, ... are formulas.
   - If A and B are formulas, then($\neg A$), ($A\rightarrow B$) are also formulas.
   - Only expressions of $\Sigma$ that are generated by 1 and 2 are formulas.

**Inference Part**

1. Axioms

   - A~1~: $A\rightarrow (B \rightarrow A)$
   - A~2~: $(A\rightarrow (B\rightarrow C))\rightarrow((A\rightarrow B)\rightarrow(A\rightarrow C))$
   - A~3~: $(\neg A\rightarrow \neg B)\rightarrow (B \rightarrow A)$

2. Inference Rule

   - Modus Ponens

     > 1. $A\rightarrow B$
     > 2. $A$
     > 3. $B$ (According to the Modus Ponens)
     >
     > > [!NOTE]
     > >
     > > Notation Form:
     > >
     > > $r_{mp}=\frac{A,A\rightarrow B}{B}$

3. Another Definition

   - If $A$ $\in$ $\Sigma$, then $\Sigma \vdash A$.

**Formation of the Proof**

1. A formal proof is a logical chain from the assumptions to the conclusions.

2. The chain has to be finite.

3. Each link in the chain might be 

   - Axioms
   - Premises
   - Intermediate conclusion by the inference rules, for example, in the Hilbert system we will find that there is only one kind of the inference rule, called the Modus Ponens.

4. If we want to prove the statement A is correct in the Hilbert System, the appearance of the formula sequence should be like 

   - A~1~

   - A~2~

   - A~3~

   - ...

   - A

     Then we can just prove the statement A in a proper form.

5. Formation

   > If a formula A has a proof with premises $\Sigma$, then we say that "A can be proved from $\Sigma$".
   >
   > It will be denoted as $\Sigma \vdash_{H} A$, or you can just simplify it as $\Sigma\vdash A$, but here I prefer to write with the notation of H, because it tells that it is just a conclusion from the premises by the rule in the Hilbert System.
   >
   > **But I think the notation below is the most important!**
   >
   > > [!IMPORTANT]
   > >
   > > If $\Sigma = \varnothing$, then we can denote the former expression as $\vdash A$, which means that **A is now a theorem in the Hilbert System.**
   >
   > **And There is also another useful trick!**
   >
   > > [!IMPORTANT]
   > >
   > > If $A\in \Sigma$, then $\Sigma \vdash A$.

**Proof in the Hilbert System**

Example One:

> We need you to prove $\vdash A \rightarrow A$ in the Hilbert system.

Solution:

> $$
> \begin{aligned}
> &\vdash A\rightarrow ((A\rightarrow A)\rightarrow A)~~~~~~~~~~~~~~~~~~~~&A_1\\
> &\vdash (A\rightarrow ((A\rightarrow A)\rightarrow A))\rightarrow((A\rightarrow(A\rightarrow A))\rightarrow(A\rightarrow A))~~~~~~~~~~~~~~~~~~~~&A_2\\
> &\vdash (A\rightarrow(A\rightarrow A))\rightarrow(A\rightarrow A)~~~~~~~~~~~~~~~~~~~~&MP _{12}\\
> &\vdash A\rightarrow (A\rightarrow A)~~~~~~~~~~~~~~~~~~~~&A_1\\
> &\vdash A\rightarrow A~~~~~~~~~~~~~~~~~~~~&MP_{34}\\
> \end{aligned}
> $$

Now you can notice that we only have one kind of inference rule here in the Hilbert system, then we can tell that sometimes it is very hard to make a proof by these limited tools.

So Now we have to introduce more inference rule here.

**Rule #3**

> *Definition:*
> $$
> \vdash A \rightarrow A
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\vdash A\rightarrow ((A\rightarrow A)\rightarrow A)~~~~~~~~~~~~~~~~~~~~&A_1\\
> &\vdash (A\rightarrow ((A\rightarrow A)\rightarrow A))\rightarrow((A\rightarrow(A\rightarrow A))\rightarrow(A\rightarrow A))~~~~~~~~~~~~~~~~~~~~&A_2\\
> &\vdash (A\rightarrow(A\rightarrow A))\rightarrow(A\rightarrow A)~~~~~~~~~~~~~~~~~~~~&MP _{12}\\
> &\vdash A\rightarrow (A\rightarrow A)~~~~~~~~~~~~~~~~~~~~&A_1\\
> &\vdash A\rightarrow A~~~~~~~~~~~~~~~~~~~~&MP_{34}\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > We can see that it is a very trivial conclusion, but it is very hard to prove it, and I think we don't need any effort to memorize this rule, but when you use it, please mention that this is a rule.

**Rule #4: Contrapositive Rule**

> *Definition:*
> $$
> \frac{\Sigma \vdash (\neg B)\rightarrow(\neg A)}{\Sigma\vdash A\rightarrow B}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\Sigma\vdash (\neg B)\rightarrow(\neg A)~~~~~~~~~~~~~~~~~~~~&Premise\\
> &\Sigma\vdash ((\neg B)\rightarrow(\neg A))\rightarrow(A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&A_3\\
> &\Sigma\vdash A\rightarrow B~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > We can see that it is telling us the relationship between the original proposition and the converse negative proposition, which the former one can imply the later one.

**Rule #5: Deduction Rule**

> **Part One**
>
> *Definition:*
> $$
> \frac{\Gamma\cup\{A\}\vdash B}{\Gamma\vdash A\rightarrow B}
> $$
> *Proof:*
>
> This can be the hardest proof in the Hilbert System.
>
> I want to separate the proposition B into all single proposition $\sum_{k=1}^{i} B_k$, and I want to use the induction rule to prove everything.
>
> When $i = 1$, then will find that there are three kinds of possibilities.
>
> 1. $B_1$ is an axiom in the Hilbert proof system.
> 2. $B_1\in \Gamma$, this is according to the $Definition_2$ of the Hilbert Proof System.
> 3. $B_1 = A$, this is also according to the $Difinition_2$ of the Hilbert Proof System.
>
> > Case One: $B_1$​ is an axiom in the Hilbert proof system.
> > $$
> > \begin{aligned}
> > &\Gamma\vdash B~~~~~~~~~~~~~~~~~~~~&Premise\\
> > &\Gamma\vdash B\rightarrow(A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&A_1\\
> > &\Gamma\vdash A\rightarrow B~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> > \end{aligned}
> > $$
>
> > Case Two: $B_1\in \Gamma$
> > $$
> > \begin{aligned}
> > &\Gamma\vdash B~~~~~~~~~~~~~~~~~~~~&Premise,~Definition_2\\
> > &\Gamma\vdash B\rightarrow(A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&A_1\\
> > &\Gamma\vdash A\rightarrow B~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> > \end{aligned}
> > $$
>
> > Case Three: $B_1 = A$​
> >
> > This time, it is just the same as proving $\Gamma \vdash A\rightarrow A$, and it is just the Rule #3.
>
> Then we have prove that when $i=1$, we can have $\frac{\Gamma\cup\{A\}\vdash B_i}{\Gamma\vdash A\rightarrow B_i}$
>
> But now, let us think about the situation when the value of $i$ is bigger than 1.
>
> what we want to prove now is that if we have $k<i$ that we can prove $\frac{\Gamma\cup\{A\}\vdash B_k}{\Gamma\vdash A\rightarrow B_k}$, then we can prove $\frac{\Gamma\cup\{A\}\vdash B_i}{\Gamma\vdash A\rightarrow B_i}$.
>
> I will just take $i$ to be $k+1$, when $B_i$ is $B_k\cup B_{k+1}$.
>
> Now, we will only have four possibilities.
>
> 1. $B_{k+1}$ is an axiom in the Hilbert proof system.
> 2. $B_{k+1}\in \Gamma$, this is according to the $Definition_2$ of the Hilbert Proof System.
> 3. $B_{k+1} = A$, this is also according to the $Difinition_2$​ of the Hilbert Proof System.
> 4. $B_{k+1}$ is the intermediate conclusion of the former $B_k$​ propositions.
>
> But for $B_i$, the former three conditions are very similar, so I will just take them together.
>
> > [!WARNING]
> >
> > I made some mistake here, I don't know how to prove the combination of the situations, maybe you can help me, contact me by <a href="mailto:Jingqi.SUN@outlook.com">email</a>
>
> > Case One: $B_i$​​ is an axiom in the Hilbert proof system, or $B_i\subset (\Gamma\cup A)$
> > $$
> > \begin{aligned}
> > &\Gamma\vdash B_i~~~~~~~~~~~~~~~~~~~~&Premise~or~Definition_2\\
> > &\Gamma\vdash B_i\rightarrow(A\rightarrow B_i)~~~~~~~~~~~~~~~~~~~~&A_1\\
> > &\Gamma\vdash A\rightarrow B_i~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> > \end{aligned}
> > $$
>
> > Case Two: $Bi\subset A$.
> >
> > This time, it is just the same as proving $\Gamma \vdash A\rightarrow A$, and it is just the Rule #3.
>
> > Case Three: $B_{k+1}$ is the intermediate conclusion of the former $B_k$ propositions, and I suppose those two to form the modus ponens is the $m^{th}$ and the $j^{th}$, and then we can write $B_m = B_j\rightarrow B_i$
> > $$
> > \begin{aligned}
> > &\Gamma \vdash A \rightarrow B_m~~~~~~~~~~~~~~~~~~~~&Premise\\
> > &\Gamma \vdash A \rightarrow B_j~~~~~~~~~~~~~~~~~~~~&Premise\\
> > &\Gamma \vdash A \rightarrow (B_j\rightarrow B_i)~~~~~~~~~~~~~~~~~~~~&Replacement\\
> > &\Gamma \vdash (A \rightarrow (B_j\rightarrow B_i))\rightarrow((A\rightarrow B_j)\rightarrow(A\rightarrow B_i))~~~~~~~~~~~~~~~~~~~~&A_2\\
> > &\Gamma \vdash (A\rightarrow B_j)\rightarrow(A\rightarrow B_i)~~~~~~~~~~~~~~~~~~~~&MP_{34}\\
> > &\Gamma \vdash A\rightarrow B_i~~~~~~~~~~~~~~~~~~~~&MP_{25}\\
> > \end{aligned}
> > $$
>
> So now by the definition of  the induction rule, I proved the deduction rule part one successfully.
>
> **Part Two**
>
> *Definition:*
> $$
> \frac{\Gamma\vdash A\rightarrow B}{\Gamma\cup\{A\}\vdash B}
> $$
> *Proof:*
>
> The proving method of part two is very similar to the one of part one, so that I will not show the proving progress here.

**Rule #6**

> *Definition:*
>
> $\vdash (A\rightarrow B)\rightarrow((B\rightarrow C)\rightarrow(A\rightarrow C))$
>
> *Proof:*
> $$
> \begin{aligned}
> \{(A\rightarrow B),(B\rightarrow C),A\}&\vdash A~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{(A\rightarrow B),(B\rightarrow C),A\}&\vdash (A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{(A\rightarrow B),(B\rightarrow C),A\}&\vdash B~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \{(A\rightarrow B),(B\rightarrow C),A\}&\vdash (B\rightarrow C)~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{(A\rightarrow B),(B\rightarrow C),A\}&\vdash C~~~~~~~~~~~~~~~~~~~~&MP_{23}\\
> \{(A\rightarrow B),(B\rightarrow C)\}&\vdash (A\rightarrow C)~~~~~~~~~~~~~~~~~~~~&Deduction_5\\
> \{(A\rightarrow B)\}&\vdash ((B\rightarrow C)\rightarrow(A\rightarrow C))~~~~~~~~~~~~~~~~~~~~&Deduction_5\\
> &\vdash (A\rightarrow B)\rightarrow((B\rightarrow C)\rightarrow(A\rightarrow C))~~~~~~~~~~~~~~~~~~~~&Deduction_5\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > I don't think that is a very powerful rule at least now, because we can find that the things it can do can not simplify a problem, but anyway it is still a very powerful rule.

**Rule #7: Transitivity Rule**

> *Definition:*
> $$
> \frac{\Sigma\vdash A\rightarrow B~~~~~\Sigma\vdash B\rightarrow C}{\Sigma\vdash A\rightarrow C}
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{A\}\cup\Sigma&\vdash A~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{A\}\cup\Sigma&\vdash (A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&Premise\\
> \{A\}\cup\Sigma&\vdash B~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \{A\}\cup\Sigma&\vdash (B\rightarrow C)~~~~~~~~~~~~~~~~~~~~&Premise\\
> \{A\}\cup\Sigma&\vdash C~~~~~~~~~~~~~~~~~~~~&MP_{34}\\
> \Sigma&\vdash A\rightarrow C~~~~~~~~~~~~~~~~~~~~&Deduction_5\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This rule is very trivial but when you want to use it, you need to give the name of it, because it doesn't appeared in the original definition of the Hilbert proof system.

**Rule #8**

> *Definition:*
> $$
> \vdash(A\rightarrow(B \rightarrow C))\rightarrow(B\rightarrow(A \rightarrow C))
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{A\rightarrow(B \rightarrow C)\}&\vdash (A\rightarrow(B \rightarrow C))~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{A\rightarrow(B \rightarrow C),A\}&\vdash (B \rightarrow C)~~~~~~~~~~~~~~~~~~~~&Deduction_1\\
> \{A\rightarrow(B \rightarrow C),A,B\}&\vdash C~~~~~~~~~~~~~~~~~~~~&Deduction_2\\
> \{A\rightarrow(B \rightarrow C),B\}&\vdash (A \rightarrow C)~~~~~~~~~~~~~~~~~~~~&Deduction_3\\
> \{A\rightarrow(B \rightarrow C)\}&\vdash (B\rightarrow(A \rightarrow C))~~~~~~~~~~~~~~~~~~~~&Deduction_4\\
> &\vdash(A\rightarrow(B \rightarrow C))\rightarrow (B\rightarrow(A \rightarrow C))~~~~~~~~~~~~~~~~~~~~&Deduction_5\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This is a pre-version of a very powerful rule, it can change the form of the proposition.

**Rule #9: Exchange of Antecedent Rule**

> *Definition:*
> $$
> \frac{\Sigma A\rightarrow(B \rightarrow C)}{\Sigma B\rightarrow(A\rightarrow C)}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\vdash A\rightarrow(B \rightarrow C)~~~~~~~~~~~~~~~~~~~~&Premise\\
> &\vdash(A\rightarrow(B \rightarrow C))\rightarrow (B\rightarrow(A \rightarrow C))~~~~~~~~~~~~~~~~~~~~&Rule\#8\\
> &\vdash B\rightarrow(A \rightarrow C)~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This is a very important rule in the Hilbert System, because it can actually help you to change the antecedent of the proposition.

**Rule #10**

> **Part One**
>
> *Definition:*
> $$
> \vdash\neg A\rightarrow(A\rightarrow B)
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{\neg A\}&\vdash (\neg A)~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{\neg A\}&\vdash((\neg A)\rightarrow ((\neg B)\rightarrow(\neg A)))~~~~~~~~~~~~~~~~~~~~&A_1\\
> \{\neg A\}&\vdash ((\neg B)\rightarrow(\neg A))~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \{\neg A\}&\vdash (A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&Contrapositive_3\\
> &\vdash\neg A\rightarrow(A\rightarrow B)~~~~~~~~~~~~~~~~~~~~&Deduction_4\\
> \end{aligned}
> $$
> **Part Two**
>
> *Definition:*
> $$
> \vdash A\rightarrow(\neg A\rightarrow B)
> $$
> *Proof:*
>
> The way of proof in the part two is very similar to which of part one, so I will not do it again.
>
> > [!NOTE]
> >
> > The meaning of it is that both sides of one thing can be used to imply anything in the world, which is very easy to understand, and I think this rule is also kind of important.

**Rule #11**

> **Part One**
>
> *Definition:*
> $$
> \vdash \neg\neg A\rightarrow A
> $$
>
> > [!NOTE]
> >
> > I gain the idea from a webpage designed by Stanford.
>
> *Proof:*
> $$
> \begin{aligned}
> \{\neg\neg A\}&\vdash (\neg\neg A)~~~~~~~~~~~~~~~~~~~~&Assumption\\
> &\vdash (\neg\neg A)\rightarrow ((\neg\neg\neg\neg A)\rightarrow (\neg \neg A))~~~~~~~~~~~~~~~~~~~~&A_2\\
> \{\neg\neg A\}&\vdash (\neg\neg\neg\neg A)\rightarrow (\neg \neg A)~~~~~~~~~~~~~~~~~~~~&Deduction_2\\
> \{\neg\neg A\}&\vdash (\neg A)\rightarrow (\neg\neg \neg A)~~~~~~~~~~~~~~~~~~~~&Contrapositive_3\\
> \{\neg\neg A\}&\vdash (\neg\neg A)\rightarrow A~~~~~~~~~~~~~~~~~~~~&Contrapositive_4\\
> \{\neg\neg A\}&\vdash  A~~~~~~~~~~~~~~~~~~~~&MP_{15}\\
> &\vdash (\neg\neg A)\rightarrow A~~~~~~~~~~~~~~~~~~~~&Deduction_6\\
> \end{aligned}
> $$

> **Part Two**
>
> *Definition:*
> $$
> \vdash A\rightarrow \neg\neg A
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{A\}&\vdash  A~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{A\}&\vdash  (\neg \neg \neg A)\rightarrow (\neg A)~~~~~~~~~~~~~~~~~~~~&Rule\#11PartOne\\
> \{A\}&\vdash  A\rightarrow (\neg\neg A)~~~~~~~~~~~~~~~~~~~~&Contrapositive_2\\
> &\vdash  A\rightarrow(A\rightarrow (\neg\neg A))~~~~~~~~~~~~~~~~~~~~&Deduction_3\\
> &\vdash  (A\rightarrow(A\rightarrow (\neg\neg A)))\rightarrow((A\rightarrow A)\rightarrow(A\rightarrow (\neg \neg A)))~~~~~~~~~~~~~~~~~~~~&Deduction_3\\
> &\vdash (A\rightarrow A)\rightarrow(A\rightarrow (\neg \neg A))~~~~~~~~~~~~~~~~~~~~&MP_{45}\\
> &\vdash A\rightarrow A~~~~~~~~~~~~~~~~~~~~&Rule\#3\\
> &\vdash A\rightarrow \neg \neg A~~~~~~~~~~~~~~~~~~~~&MP_{67}\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This conclusion is very trivial, but the proving part is very difficult.

**Rule #12**

> **Part One**
>
> *Definition:*
> $$
> \frac{\Sigma\vdash\neg\neg A}{\Sigma\vdash A}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\vdash  \neg \neg A~~~~~~~~~~~~~~~~~~~~&Premise\\
> &\vdash  \neg \neg A\rightarrow A~~~~~~~~~~~~~~~~~~~~&Rule\#11\\
> &\vdash  A~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \end{aligned}
> $$
> **Part Two**
>
> *Definition:*
> $$
> \frac{\Sigma\vdash A}{\Sigma\vdash \neg\neg A}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\vdash  A~~~~~~~~~~~~~~~~~~~~&Premise\\
> &\vdash  A\rightarrow \neg \neg  A~~~~~~~~~~~~~~~~~~~~&Rule\#11\\
> &\vdash  \neg \neg  A~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \end{aligned}
> $$

**Rule #13**

> **Part One**
>
> *Definition:*
> $$
> \vdash true
> $$
> **Part Two**
>
> *Definition:*
> $$
> \vdash false
> $$

> [!NOTE]
>
> Because we have proved the theorem 3, then we just find another expression that, so there is no need to prove it.

**Rule #14-1**

> *Definition:*
> $$
> \vdash (\neg A\rightarrow false)\rightarrow A
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{\neg A \rightarrow false\}&\vdash (\neg A \rightarrow false)~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{\neg A \rightarrow false\}&\vdash (\neg false \rightarrow A)~~~~~~~~~~~~~~~~~~~~&Contrapositive_{1}\\
> \{\neg A \rightarrow false\}&\vdash \neg false ~~~~~~~~~~~~~~~~~~~~&Rule \#13\\
> \{\neg A \rightarrow false\}&\vdash A ~~~~~~~~~~~~~~~~~~~~&MP_{23}\\
> &\vdash (\neg A\rightarrow false)\rightarrow A ~~~~~~~~~~~~~~~~~~~~&MP_{23}\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > To understand this rule, if we know something that can imply the false, then we will have the opposite of this event to be true. If you think it more carefully, it is just proving by contradiction.

**Rule #14-2: Reductio ad Absurdum**

> *Definition:*
> $$
> \frac{\Sigma \vdash \neg A \rightarrow false}{\Sigma \vdash A}
> $$
> *Proof:*
> $$
> \begin{aligned}
> \Sigma &\vdash (\neg A\rightarrow false)\rightarrow A~~~~~~~~~~~~~~~~~~~~&Rule \#14-1\\
> \Sigma &\vdash \neg A \rightarrow false~~~~~~~~~~~~~~~~~~~~&Premise\\
> \Sigma &\vdash A~~~~~~~~~~~~~~~~~~~~&MP_{12}\\
> \end{aligned}\\
> $$
>
> > [!NOTE]
> >
> > This is just another form of the rule #14, you can think that if you want to form something and then some absurd contradiction forms, then you can prove the original form is true.

> [!CAUTION]
>
> **In summary, there can be statements that are provable in a Hilbert-style proof system but false in a semantic interpretation, and vice versa.** 

**Rule #15: Implication Reduction**

> *Definition:*
> $$
> \vdash (A\rightarrow \neg A)\rightarrow \neg A
> $$
> *Proof:*
> $$
> \begin{aligned}
> \{A\rightarrow \neg A,  \neg\neg A\}&\vdash \neg\neg A~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{A\rightarrow \neg A,  \neg\neg A\}&\vdash A~~~~~~~~~~~~~~~~~~~~&DoubleNegation_1\\
> \{A\rightarrow \neg A,  \neg\neg A\}&\vdash A\rightarrow \neg A~~~~~~~~~~~~~~~~~~~~&Assumption\\
> \{A\rightarrow \neg A,  \neg\neg A\}&\vdash \neg A~~~~~~~~~~~~~~~~~~~~&MP_{23}\\
> 
> \end{aligned}
> $$
>
> 

**The List Of Rule in the Hilbert Proof System**

| Sequence |          Name          |                           Content                            |
| :------: | :--------------------: | :----------------------------------------------------------: |
|    1     |       Definition       |                     Not To Mention Again                     |
|    2     |       Definition       |                     Not to Mention Again                     |
|    3     |          Null          |                   $\vdash A\rightarrow A$                    |
|    4     |     Contrapositive     | $\frac{\Sigma \vdash (\neg B)\rightarrow(\neg A)}{\Sigma\vdash A\rightarrow B}$ |
|    5     |       Deduction        | Part One: $\frac{\Gamma\cup\{A\}\vdash B}{\Gamma\vdash A\rightarrow B}$, Part Two:$\frac{\Gamma\vdash A\rightarrow B}{\Gamma\cup\{A\}\vdash B}$ |
|    6     |          Null          | $\vdash (A\rightarrow B)\rightarrow((B\rightarrow C)\rightarrow(A\rightarrow C))$ |
|    7     |      Transitivity      | $\frac{\Sigma\vdash A\rightarrow B~~~~~\Sigma\vdash B\rightarrow C}{\Sigma\vdash A\rightarrow C}$ |
|    8     |          Null          | $\vdash(A\rightarrow(B \rightarrow C))\rightarrow(B\rightarrow(A \rightarrow C))$ |
|    9     | Exchange of Antecedent | $\frac{\Sigma A\rightarrow(B \rightarrow C)}{\Sigma B\rightarrow(A\rightarrow C)}$ |
|    10    |          Null          | Part One: $\vdash\neg A\rightarrow(A\rightarrow B)$, Part Two: $\vdash A\rightarrow(\neg A\rightarrow B)$ |
|    11    |          Null          | Part One: $\vdash \neg\neg A\rightarrow A$, Part Two: $A\rightarrow \neg\neg A$ |
|    12    |    Double Negation     | Part One: $\frac{\Sigma\vdash\neg\neg A}{\Sigma\vdash A}$, Part Two: $\frac{\Sigma\vdash A}{\Sigma\vdash \neg\neg A}$ |
|    13    |          Null          |    Part One: $\vdash true$, Part Two: $\vdash \neg false$    |
|   14-1   |          Null          |       $\vdash (\neg A\rightarrow false)\rightarrow A$        |
|   14-2   |  Reductio ad Absurdum  | $\frac{\Sigma \vdash \neg A \rightarrow false}{\Sigma \vdash A}$ |
|    15    | Implication Reduction  |       $\vdash (A\rightarrow \neg A)\rightarrow \neg A$       |

##### Natural Deduction System

##### Language Part

1. Alphabet 
   $$
   \Sigma = \{(,),\neg,\and,\or,\rightarrow,\leftrightarrow,p,q,r,...\}
   $$

2. Formula

   - Atoms $p, q, r, ...$​ are formulas.
   - If $A, B$ are formulas, then$(\neg A),(A\and B),(A\or B),(A\rightarrow B),(A\leftrightarrow B)$​ are also formulas.

**Inference Part**

1. Axioms

   |     Type      |                         Introduction                         |                    Elimination                    |
   | :-----------: | :----------------------------------------------------------: | :-----------------------------------------------: |
   |    $\and$     |                   $\frac{A,B}{(A\and B)}$                    |     $\frac{(A\and B)}{A},\frac{(A\and B)}{B}$     |
   |     $\or$     |             $\frac{A}{A\or B},\frac{A}{B\or A}$              | $\frac{A\rightarrow C,B\rightarrow C, A\or B}{C}$ |
   | $\rightarrow$ | $\frac{Box~\left\{\begin{aligned}A\\...\\B\end{aligned}\right.}{A\rightarrow B}$ |           $\frac{A\rightarrow B,A}{B}$            |
   |    $\neg$     | $\frac{Box~\left\{\begin{aligned}A\\...\\\bot\end{aligned}\right.}{\neg A}$ |                       Null                        |
   |    $\bot$     |                  $\frac{A,(\neg A)}{\bot}$                   | Null, Actually you can use $\frac{\bot}{\alpha}$  |
   |  $\neg\neg$   | Null, Actually you can use $\frac{\alpha}{\neg(\neg \alpha)}$ |              $\frac{\neg\neg A}{A}$               |

2. Inference Rule

   - Reflexivity

     > [!NOTE]
     >
     > If you want to write down a previous formula in the proof again, you can do it by reflexivity

     $$
     \Sigma \cup \{\alpha\}\vdash \alpha
     $$

> [!CAUTION]
>
> Because in the natural deduction system we don't need to change the left hand side of the $\vdash$, so that what we need to show is the right side of the formula.

**Example #1**

> *Definition:*
> $$
> \{p,q\}\vdash_{ND}p
> $$
> *Proof 1:*
> $$
> \begin{aligned}
> 1.~~~~~&p~~~~~~~~~~~~~~~~~~~~&Premise\\
> 2.~~~~~&q~~~~~~~~~~~~~~~~~~~~&Premise\\
> 3.~~~~~&p~~~~~~~~~~~~~~~~~~~~&Reflexivity_1\\
> \end{aligned}
> $$
> *Proof 2:*
> $$
> \begin{aligned}
> 1.~~~~~&p~~~~~~~~~~~~~~~~~~~~&Premise\\
> \end{aligned}
> $$

**Example #2**

> *Definition:*
> $$
> \{(p\and q)\}\vdash_{ND}(q\and p)
> $$
> *Proof:*
> $$
> \begin{aligned}
> 1.~~~~~&p\and q~~~~~~~~~~~~~~~~~~~~&Premise\\
> 2.~~~~~&p~~~~~~~~~~~~~~~~~~~~&\and e:1\\
> 3.~~~~~&q~~~~~~~~~~~~~~~~~~~~&\and e:1\\
> 4.~~~~~&q\and p~~~~~~~~~~~~~~~~~~~~&\and i:2,3\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This shows that in the natural deduction proof system we will have that the conjunction is commutative law.

**Example #3**

> *Definition:*
> $$
> \{(p\or q)\}\vdash _{ND}((p\rightarrow q)\or (q\rightarrow p))
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~p\or q~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~p~~~~~~~~~~~~~~~~~~~~Assumption\\
> &\boxed{
> \begin{aligned}
> &3.~~~~~q~~~~~~~~~~~~~~~~~~~~Assumption\\
> &4.~~~~~p~~~~~~~~~~~~~~~~~~~~Reflexivity_2\\
> \end{aligned}
> }
> \\
> &5.~~~~~q\rightarrow p~~~~~~~~~~~~~~~~~~~~\rightarrow i:3-4\\
> &6.~~~~~((p\rightarrow q)\or (q\rightarrow p))~~~~~~~~~~~~~~~~~~~~\or i:5\\
> \end{aligned}
> }
> \\
> &7.~~~~~p\rightarrow((p\rightarrow q)\or (q\rightarrow p))~~~~~~~~~~~~~~~~~~~~\rightarrow i:2-6\\
> &\boxed{
> \begin{aligned}
> &8.~~~~~q~~~~~~~~~~~~~~~~~~~~Assumption\\
> &\boxed{
> \begin{aligned}
> &9.~~~~~p~~~~~~~~~~~~~~~~~~~~Assumption\\
> &10.~~~~~q~~~~~~~~~~~~~~~~~~~~Reflexivity_2\\
> \end{aligned}
> }
> \\
> &11.~~~~~p\rightarrow q~~~~~~~~~~~~~~~~~~~~\rightarrow i:9-10\\
> &12.~~~~~((p\rightarrow q)\or (q\rightarrow p))~~~~~~~~~~~~~~~~~~~~\or i:11\\
> \end{aligned}
> }
> \\
> &13.~~~~~q\rightarrow((p\rightarrow q)\or (q\rightarrow p))~~~~~~~~~~~~~~~~~~~~\rightarrow i:8-12\\
> &14.~~~~~((p\rightarrow q)\or (q\rightarrow p))~~~~~~~~~~~~~~~~~~~~\or e:7,13\\
> \end{aligned}
> $$

**Example #4**

> *Definition:*
> $$
> \{p\rightarrow q\}\vdash  (r\or p) \rightarrow (r\or q)
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~p\rightarrow q~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~r\or p~~~~~~~~~~~~~~~~~~~~Assumption\\
> &\boxed{
> \begin{aligned}
> &3.~~~~~r~~~~~~~~~~~~~~~~~~~~Assumption\\
> &4.~~~~~r\or q~~~~~~~~~~~~~~~~~~~~\or i:3\\
> \end{aligned}
> }
> \\
> &\boxed{
> \begin{aligned}
> &5.~~~~~p~~~~~~~~~~~~~~~~~~~~Assumption\\
> &6.~~~~~p\rightarrow q~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> &7.~~~~~q~~~~~~~~~~~~~~~~~~~~\rightarrow e:5,6\\
> &8.~~~~~r\or q~~~~~~~~~~~~~~~~~~~~\or i:7\\
> \end{aligned}
> }
> \\
> \end{aligned}
> }
> \\
> &9.~~~~~(r\or p) \rightarrow (r\or q)~~~~~~~~~~~~~~~~~~~~\or e:2,3-4,5-8\\
> \end{aligned}
> $$

**Example #5**

> *Definition:*
> $$
> \{\alpha \rightarrow (\neg \alpha )\}\vdash _{ND} (\neg \alpha)
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~\alpha \rightarrow (\neg \alpha )~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~Assumption\\
> &3.~~~~~\neg\alpha~~~~~~~~~~~~~~~~~~~~\rightarrow e:1,2\\
> &4.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\bot i:2,3\\
> \end{aligned}
> }
> \\
> &5.~~~~~\neg \alpha~~~~~~~~~~~~~~~~~~~~\bot e:2-4\\
> \end{aligned}
> $$

> [!NOTE]
>
> Now we are going to prove that the elimination rule of $\bot$ is redundant, and now I will show you why.

**Example #6**

> *Definition:*
> $$
> \{\bot\}\vdash \alpha
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~\bot~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~\neg \alpha~~~~~~~~~~~~~~~~~~~~Assumption\\
> &3.~~~~~\bot~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> \end{aligned}
> }
> \\
> &4.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~\bot e:2-3\\
> \end{aligned}
> $$

**Important Derived Rules**

|              Name               |                           Formula                            |
| :-----------------------------: | :----------------------------------------------------------: |
|          Modus Tollens          | $\{p\rightarrow q,(\neg q)\}\vdash _{ND}(\neg p)$, or you can express it as $\frac{\alpha\rightarrow \beta,(\neg \beta)}{\neg \alpha}$ |
| Introduction of Double Negation |              $\frac{\alpha}{\neg(\neg \alpha)}$              |
|  Elimination of Contradiction   |                   $\{\bot\}\vdash \alpha$                    |
|      Reductio ad Absurdum       | $\frac{\boxed{\begin{aligned}&\neg\alpha\\&...\\&\bot\end{aligned}}}{\alpha}$ |
|     Law of Excluded Middle      |              $\frac{}{(\alpha\or(\neg\alpha))}$              |

> [!IMPORTANT]
>
> The proof of the elimination of the contradiction has been showed in the example #6.

**Modus Tollens**

> *Definition:*
> $$
> \{p\rightarrow q,(\neg q)\}\vdash _{ND}(\neg p)~~~~~or~~~~~\frac{\alpha\rightarrow \beta,(\neg \beta)}{\neg \alpha}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~p\rightarrow q~~~~~~~~~~~~~~~~~~~~Premise\\
> &2.~~~~~\neg q~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &3.~~~~~p~~~~~~~~~~~~~~~~~~~~Assumption\\
> &4.~~~~~p\rightarrow q~~~~~~~~~~~~~~~~~~~~Reflexivity: 1\\
> &5.~~~~~q~~~~~~~~~~~~~~~~~~~~\rightarrow e: 3,4\\
> &6.~~~~~\neg q~~~~~~~~~~~~~~~~~~~~Reflexivity:2\\
> &7.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\bot i: 5,6\\
> \end{aligned}
> }
> \\
> &1.~~~~~\neg p~~~~~~~~~~~~~~~~~~~~\bot e:3-7\\
> \end{aligned}
> $$
>
> > [!NOTE]
> >
> > This tell you that if the conclusion is wrong, then you must have been using the invalid premises.

***

**Introduction of Double Negation**

> *Definition:*
> $$
> \frac{\alpha}{\neg(\neg \alpha)}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~\neg \alpha~~~~~~~~~~~~~~~~~~~~Assumption\\
> &3.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> &4.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\bot i:2,3\\
> \end{aligned}
> }
> \\
> &5.~~~~~\neg(\neg \alpha)~~~~~~~~~~~~~~~~~~~~\neg i:2-4\\
> \end{aligned}
> $$

**Reductio ad Absurdum**

> *Definition:*
> $$
> \frac{\boxed{\begin{aligned}&\neg\alpha\\&...\\&\bot\end{aligned}}}{\alpha}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &1.~~~~~\neg\alpha\rightarrow \bot~~~~~~~~~~~~~~~~~~~~\rightarrow i: Premise\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~\neg\alpha~~~~~~~~~~~~~~~~~~~~Assumption\\
> &3.~~~~~\neg\alpha\rightarrow \bot~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> &4.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\rightarrow e: 2,3\\
> \end{aligned}
> }
> \\
> &5.~~~~~\neg(\neg\alpha)~~~~~~~~~~~~~~~~~~~~\neg i: 2-4\\
> &6.~~~~~\neg(\neg\alpha)\rightarrow\alpha~~~~~~~~~~~~~~~~~~~~\neg\neg e\\
> &7.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~\rightarrow e: 5,6\\
> \end{aligned}
> $$

**Law of Excluded Middle**

> *Definition:*
> $$
> \frac{}{(\alpha\or(\neg\alpha))}
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\boxed{
> \begin{aligned}
> &1.~~~~~\neg(\alpha\or(\neg\alpha))~~~~~~~~~~~~~~~~~~~~Assumption\\
> &\boxed{
> \begin{aligned}
> &2.~~~~~\alpha~~~~~~~~~~~~~~~~~~~~Assumption\\
> &3.~~~~~\alpha\or (\neg \alpha )~~~~~~~~~~~~~~~~~~~~\or i:2\\
> &4.~~~~~\neg(\alpha\or(\neg\alpha))~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> &5.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\bot i:3,4\\
> \end{aligned}
> }
> \\
> &6.~~~~~\neg\alpha~~~~~~~~~~~~~~~~~~~~\neg i:2-5\\
> &7.~~~~~\alpha\or (\neg \alpha )~~~~~~~~~~~~~~~~~~~~\or i:7\\
> &8.~~~~~\neg(\alpha\or(\neg\alpha))~~~~~~~~~~~~~~~~~~~~Reflexivity:1\\
> &9.~~~~~\bot~~~~~~~~~~~~~~~~~~~~\bot i:7,8\\
> \end{aligned}
> }
> \\
> &10.~~~~~\neg(\neg(\alpha\or(\neg\alpha)))~~~~~~~~~~~~~~~~~~~~\neg i:1-9\\
> &11.~~~~~\neg(\neg(\alpha\or(\neg\alpha)))\rightarrow(\alpha\or(\neg\alpha))~~~~~~~~~~~~~~~~~~~~\neg\neg e\\
> &12.~~~~~(\alpha\or(\neg\alpha))~~~~~~~~~~~~~~~~~~~~\rightarrow e:10,11\\
> \end{aligned}
> $$

#### First Order Logic 

##### Syntax

###### Domain

> Definition

A domain is a non-empty set of objects. It is a world that our statement is situated within

###### Constants

> Definition

Concrete objects in the language

###### Variables

> Definition

Variables: “place holders” for concrete values

> Classification

- Free Variables

  an occurrence of a variable $x$ in a formula is free if and only if $x$ is not within the scope of a quantified variable $x$

- Bound Variables

  otherwise, the occurrence of this variable is bound

###### Predicates

> Definition

- A property of an individual object in the domain
- A relationship among multiple individuals

> Examples

1. S(andy): Andy is a student
2. Y(andy, y): Andy is younger than y

###### Quantifiers

> Definition

The quantity of objects

> Examples

Universal quantifier: $\forall$

Existential quantifier: $\exist$​

> Universal Proposition

$\forall xP(x)$

> Existential Proposition

$\exist xP(x)$​

> Scope

- In a formula $\forall x\alpha$ or $\exist x\alpha$, $x$ is the quantified variable and its scope is the formula $\alpha$.
- The formula $\alpha$ is the scope of the quantifier $\forall x(\exist x)$, if $\forall x(\exist x)$is adjacent to $\alpha$, or, $\alpha$ immediately follows $\forall x(\exist x)$, and any proper prefix of $\alpha$ is not a formula.

###### Function

> Definition

Take some arguments and return some arguments.

> Example 

$m(y)$: $y$​'s mother

> [!NOTE]
>
> a function has arity n and sometimes denoted as $f^{(n)}$

##### Alphabet

###### Non-logical Symbols

- Constant Symbols: Usually $c_1,c_2,c_3,...$
- Predicates(Denote by uppercase letters): $P,Q,P_1,P_2,...,Q_1^1,Q_1^2,...$
- Function Symbols(Denote by lowercase letters): $f,g,h,f_1,f_2^1,...,g_1^2,...$

###### Logical Symbols

- Quantifier: $\exist,\forall$​
- Variables: $x,y,z,x_1,x_2,...,y_1,y_2,...$
- Connectives: $\neg,\and,\or,\rightarrow,\leftrightarrow$
- Punctuation: $(,),and,$
- Equality(A special binary relation):$=$

##### Important Classification in Syntax

1. terms

2. atomic formulas

3. formulas

   > Classification

   - Closed Formula/sentence

     A formula with no free variables

     - Universal Closure 

       $\forall x\forall yP(x,y)$

     - Existential Closure
       $$
       \exist x\exist yP(x,y)
       $$

   > [!NOTE]
   >
   > The presence of free variables distinguishes formulas from sentences.
   >
   > We can ask whether a closed formula is true or not.

###### Term

> Definition

- Constant and variables are (atomic) terms
- If $f^{(n)}$ is a function symbol of arity $n$, and $t_1,t_2,...,t_n$ are terms, then $f^n(t_1,t_2,...,t_n)$ is a term
- Nothing else is a term

> Example

- $c_1$
- $x$
- $f^2(x,c_1)$

###### Atomic Formula

> Definition

- $P(t_1,...,t_n)$, where $P$ is an n-ary predicate symbol, and $t_1,...,t_n\in Term(L)$
- $=(t_1,t_2)$ which is also denoted as $t_1=t_2$, where $t_1,t_2\in Term(L)$

###### Formula

> Definition

- $Atom(L)\subseteq Form(L)$
- $\alpha\in Form(L)\rightarrow (\neg \alpha )\in Form(L)$
- $\alpha,\beta\in Form(L)\rightarrow (\alpha\star \beta )\in Form(L)$, where $\star$ is any one of $\and,\or,\rightarrow,\leftrightarrow$
- $\{\alpha\in Form(L),x\text{ is a variable }\}\rightarrow \{(\exist x \alpha)\in Form(L),(\forall x \alpha)\in Form(L)\}$

##### Precedence

- Each connective on the left has priority over those on the right $\neg,\and,\or,\rightarrow,\leftrightarrow$
- $\forall x$ and $\exist x$ have the same precedence level as $\neg$
- Parentheses take the highest precedence
- Connectives are assumed to associate to the right (right associative), i.e., first group the rightmost occurrence. For example, $p\rightarrow q \rightarrow r$ means $p \rightarrow (q \rightarrow r)$

###### Parse Tree

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240620105300985.png" alt="image-20240620105300985" style="zoom:33%;" />

##### Semantic of Formula

###### Needs to Assign

- Domain $D$
- An Interpretation of non-logical symbols
  - Mapping Constants
  - Predicates
  - Function Symbols
- An interpretation of logical symbols
  - Logical connectives, punctuations (same as $P^L$​)
  - Quantifiers, variable symbols

###### Interpretation $I$

> Consist of

- Domain $D$ of $I$
- For each constant symbol $c$, a member $c^I$ of $D$
- For each function symbol $f^{(i)}$, an i-ary function $f^I$ 
- For each predicate symbol $P^{(i)}$ , an i-ary predicate (relation) $P^I$ 

###### Environment $E$

> Definition

An environment is a function (or, a look-up table) that assigns a value in the domain to every variable symbol in the language

> Example

$$
E(x)=a
$$

###### Value of Well-formed Formulas

1. $$
   P(t_1,...,t_n)^{(I,E)}=\cases{1\quad \quad if\quad P^T(t_1^{(I,E)},...,t_n^{(I,E)})=1\\0\quad \quad else}
   $$

   $$
   (t_1=t_2)^{(I,E)}=\cases{1\quad \quad if\quad t_1^{(I,E)}=t_1^{(I,E)}\\
   0\quad \quad else}
   $$

2. $$
   (\neg \alpha)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E)}=0\\0\quad \quad else}
   $$

3. $$
   (\alpha\and\beta)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E)}=\beta^{(I,E)}=1\\
   0\quad \quad else}
   $$

4. $$
   (\alpha\or\beta)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E)}=1\quad or\quad \beta^{(I,E)}=1\\
   0\quad \quad else}
   $$

5. $$
   (\alpha\rightarrow\beta)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E)}=0\quad or\quad \beta^{(I,E)}=1\\
   0\quad \quad else}
   $$

6. $$
   (\alpha\leftrightarrow\beta)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E)}=\beta^{(I,E)}\\
   0\quad \quad else}
   $$

> [!NOTE]
>
> But how can we evaluate $(\forall x\alpha)$ or $\exist x\alpha$

###### Environment Reassignment

> Definition

$$
E[x\mapsto d](y)\cases{d\quad\quad \text{ if y is x}\\
E(y)\quad\quad \text{ if y is not x}}
$$

###### Value of Well-formed Formulas with Quantifier

1. $$
   (\forall x\alpha)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E[x\mapsto d])}=1\text{ for every d in the domain of } I\\
   0\quad \quad else}
   $$

2. $$
   (\exist x\alpha)^{(I,E)}=\cases{1\quad \quad if\quad \alpha^{(I,E[x\mapsto d])}=1\text{ for some d in the domain of } I\\
   0\quad \quad else}
   $$

> [!CAUTION]
>
> If you have a quantifier, it will redefine the environment on the variable in its scope

*Examples*

> Prove that $\emptyset \vDash (\forall x(\alpha\rightarrow \beta))\rightarrow ((\forall x\alpha)\rightarrow (\forall x\beta))$

Proof:

We use the method of Reductio ad Absurdum.

Suppose $\emptyset \nvDash (\forall x(\alpha\rightarrow \beta))\rightarrow ((\forall x\alpha)\rightarrow (\forall x\beta))$

Then we have to exist some Interpretation and Environment such that $I \vDash_E \forall x(\alpha\rightarrow \beta)$;$I \nvDash_E ((\forall x\alpha)\rightarrow (\forall x\beta))$;

Which is $I \vDash_E \forall x(\alpha\rightarrow \beta)$; $I \vDash_E\forall x\alpha$; $I \nvDash_E\forall x\beta$;

For any $a\in D(I)$, $I \vDash_  {E[x\mapsto a]}(\alpha\rightarrow \beta)$,$I \vDash_  {E[x\mapsto a]}\alpha$;

Then we will have $I \vDash_  {E[x\mapsto a]}\beta$, which is against $I \nvDash_E\forall x\beta$;

So Contradiction appears, the original statement is correct.

> Prove that $\forall x(\neg\gamma)\vDash \neg(\exist x\gamma)$

To prove $\forall x(\neg\gamma)\vDash \neg(\exist x\gamma)$, we need to prove that 
$$
\forall I,\forall E,(I\vDash_E\forall x(\neg\gamma))\rightarrow(I\vDash_E\neg(\exist x\gamma))
$$
$(I\vDash_E\forall x(\neg\gamma)$ means for all $a$ in $D(I)$, we have $I\vDash_{E[x\mapsto a]}\neg\gamma$, which means there doesn't exist $I\vDash_E\exist x\gamma$, so that the original statement is correct.

##### First Order Logic Entailment

###### Satisfaction of Formulas

> Definition

An interpretation $I$ and environment $E$ satisfy a formula $\alpha$, denoted $I\vDash_E\alpha$, if and only if $\alpha ^{(I,E)}=1$. They do not satisfy $\alpha$, denoted $I\nvDash_E\alpha$ if $\alpha^{(I,E)}=0$

If $I\vDash_E\alpha$ for every $E$, then $I$ satisfies $\alpha$, denotes $I\vDash \alpha$

> Classification

- Valid

  $I\vDash_E\alpha$ for every $E$ and $I$

- Satisfiable

  $I\vDash_E\alpha$ for some $E$ and $I$

- Unsatisfiable

  $I\nvDash_E\alpha$ for every $E$ and $I$​

> [!NOTE]
>
> We write $I\vDash_E\Sigma$ if and only if for every formula $\phi\in \Sigma$, we have $I\vDash_E\phi$, when $\Sigma$ is a set of formulas.

###### $\Sigma \vDash \alpha$

> Definition

$$
\forall E,\forall I\rightarrow((I\vDash_E \Sigma)\rightarrow(I\vDash_E \alpha))
$$

> [!NOTE]
>
> $\emptyset\vDash \alpha$ means that $\alpha$ is valid

##### Natural Deduction System in First Order Logic

###### Substitution

> Denotation and Definition

$$
\alpha[t/x]
$$

Replacing each free occurrence of $x$ in $\alpha$ with $t$

> [!CAUTION]
>
> In other words, substitution does NOT affect bound occurrences of the variable.
>
> *Special Situation*
>
> > If $\alpha$ is $\forall x(\exist y((x+y)=z))$, what is $\alpha[(y-1)/z]$
>
> You can see that in this kind of special case, we don't want our substitution elements to be bounded, so that we should avoid that, here are two solutions.
>
> 1. $\forall x(\exist y((x+y)=(w-1)))$
> 2. $\forall x(\exist w((x+w)=(y-1)))$

###### Addition in Deduction Rules

|   Type    |                         Introduction                         |                         Elimination                          |
| :-------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| $\forall$ | $\frac{\boxed{\begin{aligned}&y\quad fresh\\&...\\&\alpha[y/x]\end{aligned}}}{\forall x\alpha}$ |           $\frac{(\forall x\alpha)}{\alpha[t/x]}$            |
| $\exist$  |             $\frac{\alpha[t/x]}{\exist x\alpha}$             | $\frac{(\exist x\alpha)\quad\boxed{\begin{aligned}&\alpha[u/x],\quad u\quad fresh\\&...\\&\beta\end{aligned}}}{\beta}$ |

