#### One Example of Complex Poles

Suppose I give you a complex system with the formula of 
$$
Y = X + RY-R^2Y
$$
To simplify this expression to the combination of the blocks, we have to solve for the value of poles.
$$
(R^2-R+1)Y = X
$$

$$
H(R)=\frac{Y}{X}=\frac{1}{R^2-R+1}
$$

$$
H(z)=\frac{z^2}{z^2-z+1}
$$

So that we can find the solution to be 
$$
z_1 = \frac{1+\sqrt3j}{2},z_2 = \frac{1-\sqrt3j}{2}
$$

$$
z_1 = e^{\frac{\pi j}{3}},z_2 = e^{\frac{-\pi j}{3}}
$$

So now what we have is 
$$
\begin{aligned}
\frac{Y}{X}
&=\frac{1}{1-e^{\frac{\pi j}{3}} R}\cdot \frac{1}{1-e^{\frac{-\pi j}{3}} R}\\
&=\frac{1}{\sqrt 3 j}(\frac{e^{\frac{\pi j}{3}}}{1-e^{\frac{\pi j}{3}}}-\frac{e^{\frac{-\pi j}{3}}}{1-e^{\frac{-\pi j}{3}}})
\end{aligned}
$$

> [!NOTE]
>
> And we have to make one assumption here which is the outcome of a system in the real world should have real value.



