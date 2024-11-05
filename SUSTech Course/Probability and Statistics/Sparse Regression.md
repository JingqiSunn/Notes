#### Sparse Regression

> [!NOTE]
>
> **LASSO**: Least Absolute Shrinkage And Selection Operator

##### Target Problem

$$
A\cdot x=b\\
\text{arg}_x\min{L(x)}
$$

where $A$ is a matrix.

> [!TIP]
>
> Very similar to the least square problem in linear algebra while this time we will do it in the way of statistics.
>
> So that it is very common to take the Least Square Function $||A\cdot x-b||^2$ to be the Loss Function $L(x)$​.
>
> But if we just directly use the Least Square Function to be the Loss Function, according to the principle of Least Square, there will be no zero among the entries of $x$. That means the method insists that every column of the matrix $A$ are important. But that kills the sparse of $x$ vector, because we know that not every factor of the matrix is actually important. If we don't care about these stuffs, it will lead our model to over fitting or ill condition.

##### Ridge Regression(Tikhonov Regularization)

$$
L=||A\cdot x -b||^2+\alpha ||x||^2
$$

##### LASSO

$$
L=||A\cdot x-b||^2+\lambda||x||
$$

##### Elastic Net

$$
L=||A\cdot x-b||^2+\lambda||x||+\alpha||x||^2
$$

##### Analyzing LASSO

When $\lambda$ is very big, we will find that there will be more and more terms in $x$ to die, and  once a term dies, it will never come back.