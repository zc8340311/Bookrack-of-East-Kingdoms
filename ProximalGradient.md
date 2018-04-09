# Proximal Gradient
#### Ref:
[Wiki: Proximal gradient method](https://en.wikipedia.org/wiki/Proximal_gradient_method)

### What is the proximal gradient method?
I heard the name of proxiaml gradient method long time ago when I started learning some works of my advisor.
It is used in Lasso, Robust PCA etc. I used this idea in my work too.

But lack of detailed understanding, I was confused by it for a long time.

This note combines ideas from wiki: priximal gradient method, several discussion with my advisor, and some of convex analysis class from Prof. Moscow.

*  **Proximal Gradient Methods** are a generalized form of projection used to solve *non-differentiable* convex optimization problems.

    \[ min_{x \in R} \sum f_{i}(x) ,
where $f_{i}, i = 1,...,n$ are convex function defined from $f: R^{N} -> R$ where some of the functions are non-differentiable.

This non-differentiable rules out our conventional smooth optimization techniques like steepest descent method. There is a specific class of algorithms which can solve this non-differentiable problem.
These methods are processed by splitting, in that the function $f_{1}$,...,$f_{n}$ are used individually so as to yield an easily implementable algorithm. They are called proximal because each non-smooth function among $f_{1}$...$f_{n}$ is involved via its **proximity operator**.

* Iterative shrinkage thresholding algorithm, projected landweber, projected gradient, alternating projections, alternating-direction method of multipliers, and alternating split Bregman are some examples.

* The idea of proximal gradient decent is to find a iteration step to update parameter values which is POCS, achieved by the following formula \:
\[x_{k+1} = P_{C_{1}}P_{C_{2}}...P_{C_{n}}x_{k}\]
where the $C_{i}$ are constrains, and $P_{C_{i}}$ is projection onto $C_i$ constraint.

* A proximity operator of a convex function $f$ at $x$ is defined as the unique solution to
\[argmin_y (f(y)+\frac{1}{2}\|x-y\|^2_2).\]
We want to project a point $x$ which is outside of $f$, onto $f$. The solution is to find a point on $f$ plus the euclidean distance between $y$ and $x$, This eclidean  turns out to be the orthogonal projection, which means to find a close point from a convex set, we need to orthogonally project the point onto the convex set. The operator name "proximity" means "the closest point".

* The distance from $x \in R^N$ to $C$ is definded as
\[ D_{C}(x) =  \min\limits_{y \in C} \|x-y\|_{2} \]
* if $C$ is closed and convex the projection of $x \in R^N$ onto $C$ is the unique point $P_{C}x \in C$ such that $D_C(x) = \|x - P_{C}x\|$, so the minimized distance is the Euclidean distance between the outside point and its projected point.

* Suppose $R^{N}$ represent N dimensional Euclidean space, $f: R^{N} -> (-\infty ,+\infty)$. Suppose C is a non-empty convex subset of $R^N$.
The proximal operator pr




.
