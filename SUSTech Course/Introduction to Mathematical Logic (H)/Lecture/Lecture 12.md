#### Lecture 12

##### First Order Logic

###### Alphabet

1. Logical Symbol

   > [!IMPORTANT]
   >
   > Equality is also a logical relationship here.
   >
   > It is used to be a predicate, but too often used.
   >
   > Also the punctuation is also a logical relationship here.

2. Non-logic Symbol

   - Predicate
   - Object
   - Function

###### Syntax

1. Terms
2. Atom
3. Formula

> **Terms**
>
> *Definition:*
>
> - Constant symbols and variables are (atomic) terms.
> - If $f ^{(n)}$ is a function symbol of arity $n$, and $t_1,t_2, ...,t_n$ are terms, then $f ^n (t_1,t_2, ...,t_n)$​ is a term.
> -  Nothing else is a term.
>
> **Atom**
>
> *Definition:*
>
> > [!IMPORTANT]
> >
> > Predicate(Object) is a atom.
>
> - $P(t_1, ...,t_n)$, where $P$ is an n-ary predicate symbol, and $t_1, ...,t_n ∈ Term(L )$
> - $= (t_1,t_2)$ (also denoted as $t_1 = t_2$), where $t_1,t_2 ∈ Term(L )$
>
> **Formula**
>
> *Definition:*
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240508104609771.png" alt="image-20240508104609771" style="zoom:33%;" />

> [!NOTE]
>
> My understanding is it just change the definition of atoms compared to the former proof system, it allow more non-logical atom, but your self defined functions.
>
> And formula must have logical symbol!
>
> Or what is the meaning of having a formula!
>
> $\forall x \alpha$, $\alpha$ has to be a formula, term can not be.
>
> When you are doing the breakdown job, you have to do it until the objects appears, rather than terms.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240508110208663.png" alt="image-20240508110208663" style="zoom:33%;" />

