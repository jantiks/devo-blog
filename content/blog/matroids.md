+++
title = 'Matroids'
date = 2024-05-15T21:24:35+02:00
draft = false
math = true
tags = ["Math", "Combinatorial Optimization"]
+++

Matroid is a structure $(E, F)$ where $E$ and $F$are sets and elements of $E$ are 'building' the set $F$, which has the following properties:

- **(A1):** $\empty \in F$
- **(A2):** If $X \sub Y$ and $Y \in F$ then $X \in F$
- **(A3):** Let $X, Y \in F$ and $|X| < |Y|$ then $\exists y \in Y \ X$ such that $X \cup \ {y} \in F$ 

If $M$ is a matroid, then $E$ is called the `ground set`, elements of $F$ `independent sets`

### Example
 - **Ground set $E$**: Finite set of n elements
 - **Independent sets $F$** All subsets of $E$ that contain no more than k ($k <= n$) elements.

 So let $E :=  \\{1, 2, 3, 4, 5, 6, 7\\}$, let $k = 3$, then $F = {\\{\empty\\}, \\{1\\}, \\{2\\}, \\{3\\}, \\{1, 2\\}, \\{1, 3\\}, \\{2, 3\\}, \\{1, 2, 3\\}}$

If you have $(E, F)$ such that only **(A1)** and **(A2)** hold, then $(E, F)$ is called Independent system.

Now, you may rightfully ask, what is an example of Independent system which is not a Matriod?

**Answer:** Let graph $G = (V, E)$ where $V$ is the set of vertices and $E$ is the set of edges, Let's take $(E, F)$ where $E$ is the edges of some graph G  

