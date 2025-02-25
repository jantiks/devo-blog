+++
title = 'The binomial coefficient'
author = "Tigran Arsenyan"
description = 'Intuition behind binomial coefficient'
tags = ["Math", "Combinatorics"]
date = 2024-08-25T18:18:04+01:00
draft = false
+++

The binomial coefficient denoted by $n \choose k$ is the number of ways to choose k objects from n objects. Its formula is the following: $n \choose k$ = $\frac{n!}{k!(n-k)!}$, why is this even the case? How did people come up with this? Let us find out together.

So we want to find the number of ways we can pick $k$ objects our of $n$ objects, let's say we have the set $\\{1,2,3, ..., n\\}$, and we are trying to pick $k$ of them and if $k = 2$ it doesn't matter we pick 1,2 or 2,1 those are the same, which basically means we don't care about the ordering of choice.

So now let us derive the formula together.

Suppose we are picking the $k$ objects by rounds, and in each round we pick only one element, so overall we have $k$ rounds, at round 1 we have $n$ objects to take, so we have n ways to take 1 object, at round 2 there are only left $n-1$ objects, so we have $n-1$ ways to pick an object, so at the end of round 2 we have $n*(n-1)$ ways to pick 2 objects out $n$, and with this way can continue this until $k+1$, hence the number of ways to pick $k$ objects out of $n$ would be $n(n-1)(n-2)* ... *(n-k+1)$, which equals to $\frac{n!}{(n-k)!}$, the $(n-k)!$ fraction is just a nice way to cancel out all factors of $n!$ which come after $(n-k+1)$.

The equation $\frac{n!}{(n-k)!}$ counts all the sequences of the $k$ objects we can choose, but we don't care about the different orderings of the same set of objects, so we have to count them out. And with similar reasoning, we have $k!$ possible sequences for each set of $k$ objects, hence we have to divide the forumla by $k!$, hence we get $\frac{n!}{k!(n-k)!}$
