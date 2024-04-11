#### Natural Deduction System

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