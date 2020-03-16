---
title: "Rosenberg ML"
section: "Real Analysis"
author: "Chaichontat Sriworarat"
date: 2020-03-16
tags: ["real analysis"]
---

# Lecture 9

## Convex Optimization
A set $C$ is **convex** if $∀x_1,x_2 ∈ C$ and $0 ≤ θ≤ 1$,
$$
\begin{align}
  θx_1+(1-θ)x_2∈C.
\end{align}
$$

A function $f$ is convex if $∀x,y ∈\on{dom}(f)$,
$$
\begin{align}
  f(θx+(1-θ)y)≤θf(x) + (1-θ)f(y).
\end{align}
$$

* Convex $⟹$ local minima are global minima.
* Strictly convex $⟹$ local minimum is unique.

### Standard Optimization Form
$$
\begin{align}
  \min \quad &f_0(x) \\
  \mathrm{s.t.} \quad &f_i(x) ≤ 0 \\
  &h_i(x) = 0.
\end{align}
$$

* A point $x$ satisfying all constraints is called a **feasible point**.
* A **Feasible set** is the set of feasible points.
* $x$ is feasible and $f_i(x) = 0 ⟹ f_i(x)≤0$ is **active** at $x$.
* An **optimal value** $p^∗ = \inf\set{f_0(x): x \text{ satisfies all constraints.}}$.
* $x^∗$ is an **optimal point** if $x^∗$ is feasible and $f(x^∗)=p^∗$.


## Lagrangian Duality

The **Lagrangian** for a standard optimization problem is
$$
\begin{align}
  L(x,λ) = f_0(x) + \sum_{i=1}^m λ_if_i(x).
\end{align}
$$

$λ$ is called the **Lagrange multipliers**.

Taking the supremum over the Lagrangian gives back encoding of objective and constraints,
$$
\begin{align}
  \sup_{λ⪰0} L(x,λ) &= \sup_{λ⪰0}\pp{f_0(x) + \sum_{i=1}^m λ_i f_i(x)} \\
  &= \cases{
    f_0(x) & $f_i(x)≤0$ all $i$ \\
    ∞ & otherwise
  }.
\end{align}
$$

Equivalently, in **primal form**,
$$
\begin{align}
  p^∗ &= \inf_x \, \sup_{λ⪰0} L(x,λ)
\end{align}
$$
The Lagrangian dual problem is
$$
\begin{align}
  d^∗ &= \sup_{λ⪰0} \, \inf_x  L(x,λ) \\
  &= \sup_{λ⪰0} g(λ)
\end{align}
$$
where $g$ is the **dual function**.

Have **weak duality** if $p^∗≥d^∗$.

* $p^∗-d^∗$ is called the **duality gap**.
* Duality gap is 0 when the optimization is convex.
* Dual function is always concave.
* Lagrange dual gives the lower bound of $p^∗$.

Dual problem (often easier to solve) is
$$
\begin{align}
  \max \quad &g(λ) \\
  \mathrm{s.t.} \quad &λ ⪰ 0.
\end{align}
$$