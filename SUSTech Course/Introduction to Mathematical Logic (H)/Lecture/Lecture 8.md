#### Lecture 8

|     Type      |                         Introduction                         |                    Elimination                    |
| :-----------: | :----------------------------------------------------------: | :-----------------------------------------------: |
|    $\and$     |                   $\frac{A,B}{(A\and B)}$                    |    $\frac{(A\and B)}{A}$,$\frac{(A\and B)}{B}$    |
|     $\or$     |            $\frac{A}{A\or B}$,$\frac{A}{B\or A}$             | $\frac{A\rightarrow C,B\rightarrow C, A\or B}{C}$ |
| $\rightarrow$ | $\frac{Box~\left\{\begin{aligned}A\\...\\B\end{aligned}\right.}{A\rightarrow B}$ |           $\frac{A\rightarrow B,A}{B}$            |
|    $\neg$     | $\frac{Box~\left\{\begin{aligned}A\\...\\\bot\end{aligned}\right.}{\neg A}$ |                       Null                        |
|    $\bot$     |                  $\frac{A,(\neg A)}{\bot}$                   |                       Null                        |
|  $\neg\neg$   |                             Null                             |              $\frac{\neg\neg A}{A}$               |

> [!NOTE]
>
> Actually we don't need to put the sign of $vdash$

**Example**

> *Definition:*
> $$
> 
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\vdash p \or q~~~~~~~~~~~~~~~~~~~~&premise\\
> Box.1.Begin\\
> &\vdash p~~~~~~~~~~~~~~~~~~~~&premise\\
> 
> \end{aligned}
> $$
>
> $$
> \left\{
> \begin{aligned}
> A\\
> ...\\
> B
> \end{aligned}
> \right.
> $$
>
> 

**Law of Excluded Middle**

> *Definition:*
> $$
> 
> $$
> *Proof:*
> $$
> \begin{aligned}
> &\neg (\alpha\or(\neg \alpha))~~~~~~~~~~~~~~~~~~~~&Assumption\\
> Box.1.Begin\\
> &\alpha~~~~~~~~~~~~~~~~~~~~&Assumption\\
> 
> \end{aligned}
> $$
> 