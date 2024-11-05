#### A Study on Performance Evaluation Ability of a Modified Inverted Generational Distance Indicator

##### Inverted Generational Distance

###### How to Determine the Distance

> 1. Determine the Reference Set
>
>    Obtain a set of Pareto-optimal solutions, which serves as the reference set. This set represents the ideal distribution of solutions across the objective space.
>
> 2. Calculate the Distance for Each Solution
>
>    For each solution 𝑠*s* in the set of non-dominated solutions produced by the algorithm, calculate its distance to the reference set. The distance metric used is typically Euclidean distance or another appropriate distance measure in the objective space.
>
> 3. Aggregate the Distances
>
>    Aggregate the distances calculated in the previous step, typically by taking the average or sum of distances across all solutions.
>
> 4. Normalize the Result
>
>    Normalize the aggregated distance by dividing it by the number of solutions in the non-dominated set. This step ensures that the IGD value is independent of the number of solutions.
>
> 5. Invert the Result
>
>    Since the IGD measures closeness to the reference set, and smaller values indicate better convergence, the final IGD value is often inverted. 
>
> **Mathematical Expression**
>
> - Let $R$​ be the reference set of Pareto-optimal solutions.
> - Let $S$​ be the set of non-dominated solutions produced by the algorithm.
>
> $$
> IGD=\frac{1}{|S|}\sum_{s\in S}d(s,R)
> $$

###### The Application of Inverted Generational Distance

This algorithm quantifies how well the solutions produced by the algorithm approximate the true Pareto front, with lower IGD values indicating better convergence.

So why lower IGD implies better convergence?

> 1. Proximity to the True Pareto Front
>
>    The ultimate goal of a multi-objective optimization algorithm is to approximate the Pareto front, which represents the set of all Pareto-optimal solutions in the objective space. A lower IGD value indicates that the solutions produced by the algorithm are closer to this ideal front. Thus, lower IGD values signify a better approximation to the true Pareto front.
>
> 2. Improved Solution Quality
>
>    A lower IGD value implies that the algorithm has generated solutions that are not only non-dominated but also closer to the reference set of Pareto-optimal solutions. Closer proximity to the reference set suggests that the solutions are of higher quality in terms of meeting the objectives or preferences specified by the optimization problem.
>
> 3. Enhanced Diversity and Coverage
>
>    Lower IGD values often correspond to solutions that exhibit better diversity and coverage across the objective space. This means that the algorithm is able to explore a wider range of trade-offs between conflicting objectives, resulting in a more comprehensive set of solutions that better represents the problem's solution space.
>
> 4. Quantitative Measure of Convergence
>
>     By providing a numerical measure of how well the algorithm converges to the Pareto front, lower IGD values offer a quantitative assessment of algorithm performance. This enables comparisons between different algorithms or parameter settings, with lower IGD values indicating superior convergence and solution quality.

How to find $d(s,R)$?

> 1. Select a Distance Metric
>
>    Choose a distance metric suitable for your problem domain and the characteristics of the solutions. Common distance metrics include Euclidean distance, Manhattan distance, Chebyshev distance, and others.
>
>    > [!NOTE]
>    >
>    > Finding a standard to analyze the distance between the points can be the most difficult things in this method, which will be covered in my future notes.
>
> 2. Calculate Distance to Each Solution in $R$
>
> 3. Find the Minimum Distance
>
> 4. Use the Minimum Distance as $d(s,R)$

Why calculation of Inverted Generational Distance is more efficient than calculation of the Hypervolume?

> 1. Simplicity of Calculation
>
>    The IGD requires calculating the distance between each solution produced by the algorithm and the reference set of Pareto-optimal solutions. This involves computing the distance using a chosen distance metric, such as Euclidean distance. While this can still require computation, it's typically simpler and faster than computing the hypervolume, which involves computing the volume of the dominated space in the objective space. The calculation of hypervolume can be complex, especially in higher-dimensional spaces.
>
> 2. Computational Complexity
>
>     The computational complexity of calculating the hypervolume increases significantly with the dimensionality of the objective space. As the number of objectives increases, the hypervolume calculation becomes more computationally expensive due to the need to compute the volume of the dominated space. In contrast, the IGD calculation involves computing distances in the objective space, which may not scale as dramatically with dimensionality.
>
> 3. Objective Space Coverage
>
>    The IGD focuses on measuring the convergence of the algorithm's solutions towards the Pareto front by considering their proximity to the reference set. This makes it particularly suitable for evaluating convergence performance. In contrast, the hypervolume indicator measures the volume of the dominated space, which indirectly reflects both convergence and diversity but may not provide as direct a measure of convergence as the IGD.
>
> 4. Ease of Interpretation
>
>    The IGD produces a single scalar value that quantifies the convergence performance of the algorithm, with lower values indicating better convergence. This makes it easy to interpret and compare across different runs of the same algorithm or different algorithms. The hypervolume, while also producing a scalar value, may be less intuitive to interpret, especially in higher-dimensional spaces.

###### The Shortage of Inverted Generational Distance

**Pareto Incompliant**

> - Type: Two-dimensional Objective Space
> - Solution Sets: $A=\{a_1,a_2,a_3\},B=\{b_1,b_2,b_3\}$
> - Reference Sets: $C=\{c_1,c_2,c_3\}$
> - Setting: Every solution in $B$ is dominated by at least one solution of $A$​.
> - Ideal Result: $A$ is a better solution set than $B$.
> - Actual Result: $A$ is not better than $B$​.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240427120003826.png" alt="image-20240427120003826" style="zoom:50%;" />

**Dependency on Reference Points Selection**

> **Case 1**
>
> - Type: Two-dimensional Objective Space
> - Solution Sets: $A=\{a_1,a_2,a_3\},B=\{b_1,b_2,b_3\}$
> - Reference Sets: $C=\{c_1,c_2,c_3\}$
> - Setting: Every solution in $B$ is dominated by at least one solution of $A$​.
> - Ideal Result: $A$ is a better solution set than $B$.
> - Actual Result: 
> - $A$ is a better solution set than $B$​​​.
> - Figure 2
>
> **Case 2**
>
> - Type: Two-dimensional Objective Space
> - Solution Sets: $A=\{a_1,a_2,a_3\},B=\{b_1,b_2,b_3\}$
> - Reference Sets: $C=\{c_1,c_2,c_3\}$
> - Setting: Every solution in $B$ is dominated by at least one solution of $A$​.
> - Ideal Result: $A$ is a better solution set than $B$.
> - Actual Result: $A$ is not better than $B$​​.
> - Figure 3
>
> > [!NOTE]
> >
> > The most important part is that the only difference between two cases is just the different selection of reference points.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240427121104831.png" alt="image-20240427121104831" style="zoom:50%;" />
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240427121140554.png" alt="image-20240427121140554" style="zoom:50%;" />

###### Solution to The Shortage of Inverted Generational Distance

Then it comes to the introduction of $IGD^+$.

And we know that in the situation of Figure 1, the traditional Inverted Generational Distance is not reliable any more, but we can introduce $IGD^+$.

> Algorithm:
>
> Calculate the distance from each reference point zi to the  dominated region by the solution set.

Now we can see its performance which will fail by traditional Inverted Generational Distance.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240504100522797.png" alt="image-20240504100522797" style="zoom:50%;" />

Now we can see that under this situation we can find set $A$ is a better set of solution than set $B$.

###### Problem of Inverted Generational Distance Plus

1. Not Complete Pareto Compliant
2. Practical Usefulness Unclear
3. 

##### Other Resources

https://blog.csdn.net/xyisv/article/details/86741887

https://blog.csdn.net/a1920993165/article/details/112136149

