+++
title = 'What is a Matroid?'
date = 2024-05-15T21:24:35+02:00
author = "Tigran Arsenyan"
draft = false
tags = ["Math", "Combinatorial Optimization"]
comments = true
+++

Matroid is a structure $(E, F)$ where $E$ and $F$ are sets and elements of $E$ are 'building' the set $F$, which has the following properties:

- **(A1):** $\empty \in F$
- **(A2):** If $X \subseteq Y$ and $Y \in F$ then $X \in F$
- **(A3):** Let $X, Y \in F$ and $|X| < |Y|$ then $\exists y \in Y \backslash X$ such that $X \cup \ \\{y\\} \in F$ 

If $M$ is a matroid, then $E$ is called the `ground set`, elements of $F$ `independent sets`

### Example
 - **Ground set $E$**: Finite set of n elements
 - **Independent sets $F$** All subsets of $E$ that contain no more than k ($k <= n$) elements.

 So let:
 - $E :=  \\{1, 2, 3, 4, 5, 6, 7\\}$.
 - $k = 3$
 - Then: $F = \\{\empty, \\{1\\}, \\{2\\}, \\{3\\}, \\{1, 2\\}, \\{1, 3\\}, \\{2, 3\\}, \\{1, 2, 3\\}\\}$


### Independent System
If you have $(E, F)$ such that only **(A1)** and **(A2)** hold, then $(E, F)$ is called Independent system.

Now, you may rightfully ask, what is an example of Independent system which is not a Matriod?
> {{< collapse summary="**Answer:**" >}}
Let graph $G = (V, E)$ where $V$ is the set of vertices and $E$ is the set of edges, Let's take $(E, F)$ where $E$(Ground set) is $E(G)$ and each element of $F$ is a matching in $G$.
$(E, F)$ is a Independent system but not Matroid, because:
- **(A1)** $\empty \in F$
- **(A2)** Take matching $Y \in F$, then $\forall X \sub Y: X \in F$, because all subsets of $Y$ are also matchings in G
- **(A3)** Doesn't hold: Take G := $C_4$ and perfect matching $M_1$, and any non empty other matching $M_2$ of $C_4$ such that $M_1 \cap M_2 \neq \empty$, then take any edge edge from $M_1$ and add to $M_2$ it won't be a matching. Hence (A3) doesn't hold, and $(E, F)$ is an Independent set (A1 and A2 holds), but not a matroid.
{{</ collapse >}}
---

### Some practice with matroids
**Problem:** Let $(E, F)$ be a matroid, $E^\prime \cup E$ and $F^\prime = \\{ I \cap E^\prime | I \in F \\}$, prove that $(E^\prime, F^\prime)$ is also a matroid.

Think of a soltuion for 5 minutes.

> {{< collapse summary="**Answer:**" >}}
To prove $(E^\prime, F^\prime)$ is a matroid, we should prove that it holds the 3 properties of the matroid: (A1, A2, A3):
- **A1:** Since $\empty \in F$, for $I := \empty$, $I \cap E^\prime = \empty$ hence  $\empty \in F^\prime$., so **A1** holds
- **A2:** We should show that $\forall X^\prime \in F^\prime$, all subsets of $X$ are also in $F^\prime$. Take $X^\prime \in F^\prime$, for some $I \in F$, $X^\prime = I \cap E^\prime$ and $I \cap E^\prime \in F$, hence $X^\prime \in F$ as well, this implies that all subsets of $X^\prime$ are also elements $F$(Because $(E, F)$ is a matroid), hence all subsets of $X^\prime$ are also elements of $F^\prime$
- **A3:** let's prove it by contradiction: Which means, for an $X,Y \in F^\prime$ s.t $|X| > |Y|$, $\forall x \in X \backslash Y | (Y \cap \\{x\\})\notin F^\prime$, from the proof of **A2** we know that for some $I_x \in F$ such that $X = I_x \cap E^\prime$, $(I_x \cap E^\prime) \in F$, similar for some $I_y$ and $Y$. This means that $|I_x \cap E^\prime| > |I_y \cap E^\prime|$, and property **A3** holds for them, but this is contradiction, because if there is $x \in ((I_x \cap E^\prime) \backslash (I_y \cap E^\prime))$ such that $((I_y \cap E^\prime) \cap \\{x\\} \in F)$, then $(I_y \cap E^\prime) \cap \\{x\\} \in F^\prime$ by definition of $F^\prime$. Hence proving **A3**
{{</ collapse >}}
---
### Why should you care?
Matroids give framework to prove the correctness of [greedy algorithms](https://en.wikipedia.org/wiki/Greedy_algorithm). If a structure you want to maximize/minimize is a matroid, then you can use a greedy algorithm on it. Conversely if you can solve a problem using greedy algorithm, then the underlying structure must be a matroid.

---
This was a quick intro to matroids, structures in combinatorial optimization which can be seen in our daily life (if you are wondering where, then you just should look deeper 😄)