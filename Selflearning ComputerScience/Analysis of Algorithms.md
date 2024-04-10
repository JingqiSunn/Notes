#### Analysis of Algorithms

**The Relationship Between Value Size and The Computation Time**

According to the test we will have that 
$$
\log_2(T(N))=b\log_2(N)+c
$$
Then we will have 
$$
\log_2(T(N))=\log_2(N^b)+\log_2 2^c
$$

$$
\log_2(T(N))=\log_2 (N^b\times2^c)
$$

$$
T(N)=2^c\times N^b
$$

If we set $2^c$ to be a variable a, then we will have 
$$
T(N)=aN^b
$$
**A Quick Way to Estimate b in a Power-Law Relationship**

We know that $T(N)=aN^b$

Then we will have 
$$
\begin{aligned}
\frac{T(2N)}{T(N)}=&\frac{a(2N)^b}{aN^b}\\
=&2^b
\end{aligned}
$$
Then we can quickly find the estimation of the value of b by experiment.

So we can find that 
$$
b=\log_2\frac{T(2N)}{T(N)}
$$
**A Quick Way to Estimate a in a Power-Law Relationship**

We can quickly estimate the value of b by the former steps, then we can just input a certain number of N to make an experiment, then according to the equation $T(N)=aN^b$

We have that
$$
a=\frac{T(N)}{N^b}
$$
**Most Primitive Operations Take Constant Time** 

|                          Operation                           | Time(nanoseconds) |
| :----------------------------------------------------------: | :---------------: |
|                     Variable Declaration                     |       c~1~        |
|                     Assignment Statement                     |       c~2~        |
|                       Integer Compare                        |       c~3~        |
|                     Array Element Access                     |       c~4~        |
|                         Array Length                         |       c~5~        |
| n Dimensional Array Allocation(with N element in each layer) |     c~6~N^n^      |

*Example*

> Here we have a algorithm, let us find the computation time of it.
>
> ```java
> int count = 0;
> for (int i = 0; i < N; i++)
> 	if (a[i] == 0)
> 	count++
> ```
>
> Notation: the array here has N elements in each layer.
>
> Solution:
>
> Here we will have a lot of operations.
>
> For the variable declaration, we did it twice, the first time is "int count = 0;" in the very beginning of the algorithm, the second time is "int i = 0;" in the initialization of the loop.
>
> For Assignment Statement, there is only 2, the first time is "int count = 0;", the second time is "int i = 0".
>
> For the less than compare, we did it for N+1 times, from i equals to 0 to i equals to N, although it failed the last time.
>
> For equal to compare, we did it for N times, from i equals to 0 to i equals to (N-1).
>
> For array access, we did it for N times, from i equals to 0 to i equals to (N-1).
>
> For the increment, we did it for (N to 2N) times, because we have i++ for N times and also we can not make sure that every loop will lead to count++, but we are sure that the maximum is N and the minimum is 0.

> Here we have a algorithm, let us find the computation time of it.
>
> ```java
> int count = 0;
> for (int i = 0; i < N; i++)
> 	for (int j = i+1; j < N; j++)
> 		if (a[i] + a[j] == 0)
> 		count++;
> ```
>
> |      Operation       |           Frequency            |
> | :------------------: | :----------------------------: |
> | Variable Declaration |             $2+N$              |
> | Assignment Statement |             $2+N$              |
> |  Less than Compare   |     $\frac{(N+1)(N+2)}{2}$     |
> |   Equal to Compare   |       $\frac{N(N-1)}{2}$       |
> |     Array Access     |            $N(N-1)$            |
> |      Increment       | $\frac{N(N-1)}{2}$ to $N(N-1)$ |

**Simplification: Cost Model**

*Definition: Use some basic operation as a proxy for running time.*

It is just looking like 

|      Operation       |           Frequency            |
| :------------------: | :----------------------------: |
| Variable Declaration |             $2+N$              |
| Assignment Statement |             $2+N$              |
|  Less than Compare   |     $\frac{(N+1)(N+2)}{2}$     |
|   Equal to Compare   |       $\frac{N(N-1)}{2}$       |
|     Array Access     |            $N(N-1)$            |
|      Increment       | $\frac{N(N-1)}{2}$ to $N(N-1)$ |

**Simplification: Tilde Notation**

*Definition: Estimate running time(or memory) as a function of input size N.*

Tricks that we will always use:

1. When N is large, terms are negligible.
2. When N is small, we don't care.

Here is an example:

> $\frac{1}{6}N^3+20N+16=\frac{1}{6}N^3$

So it can be recorded as $O(N^3)$.

> [!NOTE]
>
> The approximate model can be very complicated, but in this course we will just assume that $T(N)$~$cN^3$

**Common Order-of-growth Classifications**

> *Definition:*
>
> If $f(N)$~$cg(N)$ for some constant $c> 0$, then the order of growth of $f(N)$ is $g(N)$.
>
> > [!NOTE]
> >
> > This is just the application of the Tilde Notation.

**Binary Search**

1. Compare key against middle entry.
2. Too small, go left.
3. Too big, go right.
4. Equal, found.

> And here is the source code of the Binary Search in Java.
>
> I will use the example of 
>
> ```java
> Arrays.binarySearch(long[],long)
> ```
>
> Here is the Source Code.
>
> ```java
> public static int binarySearch(long[] a, long key) {
>         return binarySearch0(a, 0, a.length, key);
>     }
> ```
>
> ```java
> // Like public version, but without range checks.
> private static int binarySearch0(long[] a, int fromIndex, int toIndex,long key) {
> 	int low = fromIndex;
>  	int high = toIndex - 1;
> 	while (low <= high) {
>     	int mid = (low + high) >>> 1;
>         long midVal = a[mid];
> 			if (midVal < key)
>             	low = mid + 1;
>             else if (midVal > key)
>                 high = mid - 1;
>             else
>                 return mid; // key found
>         }
>         return -(low + 1);  // key not found.
>     }
> ```
>
> I am going to calculate the time complexity of this algorithm.
>
> 1. **Initialization**: At the beginning of the algorithm, we have the entire sorted array to search through. This requires no comparisons and can be considered constant time, typically denoted as $O(1)$.
> 2. **Iterations**: In each iteration of binary search, the search interval is halved. This means that the size of the search interval is divided by 2 with each iteration. As a result, the number of iterations required to reduce the search interval to a single element is $\log_2{(n)}$, where $n$​ is the size of the input array.
> 3. **Comparison**: In each iteration, binary search compares the target element with the middle element of the current search interval. Therefore, the total number of comparisons made during the algorithm is also$O(\log_2{(n)})$.

**Three Types of Notations**

| Notation |     Meaning     |
| :------: | :-------------: |
| $\theta$ |  The Asymptote  |
|   $O$    | The Upper Bound |
| $\Omega$ | The Lower Bound |

**Other Resources**

https://algs4.cs.princeton.edu/lectures/keynote/14AnalysisOfAlgorithms.pdf

https://www.youtube.com/watch?v=9TlHvipP5yA&amp;ab_channel=AbdulBari

https://www.youtube.com/watch?v=vRAMUDcwXy4&amp;ab_channel=BYTSINDIA

