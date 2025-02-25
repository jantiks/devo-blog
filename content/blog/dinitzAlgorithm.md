+++
title = 'Dinitz Algorithm'
description = "Dinitz algorithm and it's applications for special graphs"
date = 2024-10-12T08:28:24+02:00
author = "Tigran Arsenyan"
tags = ["Graph Algorithms", "Algorithms"]
draft = true
comments = true
+++

Before we get into the Dinitz algorithm let's use a switched definition
for flows which lets an easier design of algorithms.

**Definition (Effective flow):** For a flow $f$ we define effective flow as: $f^{*} : E \rightarrow R$, where: 

$f^{*}(uv) := f(uv) - f(vu)$

Let's observe some properties of $f^{*}$

1. $$f^{*}(uv) = -f^{*}(vu)$$
2. $$f^{*}(uv) \leq c(uv)$$
    (2) holds because $f^{*}(uv)$ is bounded by $c(uv)$
3. By combining both (1) and (2): $$f^{*}(uv) \geq -c(vu)$$
4. $\forall v \in V(G)$ such that $v \neq s,t$,  $\sum_{(u,v) \in E} f^{*}(uv) = 0$

**Lemma:** For every effective flow $f^{*}$ satisfying (1), (2), (4), there exists a 
corresponding flow f

**Proof:**

For any pair of edges $uv$ let's define a flow $f$ on it. 

WLOG: $f^{*}(uv) \geq 0$

Now let's define a function $f$ such that:

- $f(uv) := f^{*}(uv) \leq c(uv)$
- $f(vu) := 0$

It can be easily verified that $f$ is a flow.


Let's give a modified defintion of residual capacity as well.

**Definition (Resiudal capacity):** $r(uv) = c(uv) - f^{*}(uv)$


**Definition (Residaul network)** For a network $N(G, c, s, t)$ and a flow $f$ in $N$.
Residual network is $R(N, f) := (G, r, s, t)$, where $r$ is the residual capacity. 

**Lemma**
