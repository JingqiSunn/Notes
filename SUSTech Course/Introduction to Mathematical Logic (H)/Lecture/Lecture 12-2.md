#### Lecture 12-2

![image-20240511104050527](C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511104050527.png)

It means the situation lack of parenthesis.

#####  Free and Bound Variable

> - Free variables: an occurrence of a variable x in a formula is free if and only if x is not within the scope of a quantified variable x.
>
>   Like $P(x)$
>
> - Bound variables x: otherwise, the occurrence of this variable is bound, i.e., the occurrence of this variable lies in the scope of some quantifier of the same variable.
>
>   Like $\forall x P(x)$​
>
>   The first $x$ is neither free or bound, and the second x is a bound variable.

##### Open Formula and Close Formula

> Open Formula: with free variable
>
> Close Formula(Sentence in FOL): without free variable

##### Universal Closure and Existential Closure

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511105926478.png" alt="image-20240511105926478" style="zoom:33%;" />

##### Interpretation 

> 1. A non-empty set D, called the domain (or universe) of I.
> 2. For each constant symbol c, a member c I of D.
> 3. For each function symbol f (i) , an i-ary function f I .
> 4. For each predicate symbol P (i) , an i-ary predicate (relation) P I .

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511112515669.png" alt="image-20240511112515669" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511112530351.png" alt="image-20240511112530351" style="zoom:33%;" />

That means 1,3 has the property of P.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511113257276.png" alt="image-20240511113257276" style="zoom:33%;" />

The reason it looks like this is we don't have free variables.

We need environment for free variable.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511113659957.png" alt="image-20240511113659957" style="zoom:33%;" />

##### Environment

> *Definition:*
>
> An environment is a function (or, a look-up table) that assigns a value in the domain to every variable symbol in the language.
>
> > [!NOTE]
> >
> > This concept is similar to the truth valuation (e.g., $\alpha^v$ = 1) in propositional logic.

###### Value of Terms

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511113946418.png" alt="image-20240511113946418" style="zoom:33%;" />

##### Evaluate $\forall x\alpha$​

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511115309230.png" alt="image-20240511115309230" style="zoom:33%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511115709171.png" alt="image-20240511115709171" style="zoom:33%;" />

There are two step of assigning

1. <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511120036855.png" alt="image-20240511120036855" style="zoom:33%;" />
2. <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240511120102235.png" alt="image-20240511120102235" style="zoom:33%;" />

We can actually reassign the variable by the second step, which will always happen in $\forall x \alpha$