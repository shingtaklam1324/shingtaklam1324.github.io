+++
title="Canonical metrics in complex geometry"
date="02 Feb 2025"
math=true
+++

In this post, I'll attempt to provide an intorduction to the study of canonical (or extremal) metrics in complex geometry. The emphasis of this post is on the differential geometry side of the picture, and not the algebro-geometric side. In particular, there are interesting links to moduli theory which I won't cover. Finally, this is supposed to be an overview post, and so I won't cover the geometric analysis aspects on the subject.

Recall that if $S$ is a Riemann surface, then its universal cover is one of

* $\mathbb{CP}^1$
* $\mathbb C$
* $\mathbb D$, the unit disc in $\mathbb C$.

In particular, we have natural choices of metrics for each of these. The usual metric on $\mathbb{CP}^1$ has constant (Gaussian) curvature $1$, the metric on $\mathbb C$ has curvature $0$, and the hyperbolic metric on $\mathbb D$ has curvature $-1$. Another way to think about this is that every compact Riemann surface has a metric with constant curvature, and we get a trichotomy:

* Positive: genus $0$
* Flat: genus $1$
* Negative: genus $\ge 2$.

One interesting question is then: can we find constant scalar curvature metrics on higher dimensional complex manifolds? To do this, we'll first put this question into a more general framework.

## Preliminaries

### Geometric Invariant Theory

Geometric Invariant Theory (GIT) is one answer to the question: how do we take quotients of algebraic varieties? More concretely, let $X$ be a projective variety, $G$ a reductive Lie group (which we will understand as $\mathrm{Lie}(G) = \mathrm{Lie}(K) \otimes \mathbb C$ for a maximal compact subgroup $K$). How do we define a variety $X/G$?

The answer, as developed by Mumford, is to ask for a "stability" condition. That is, we define what it means for an orbit to be stable, semistable and polystable, the subsets of $X$ are denoted by $X^s, X^{ss}, X^{ps}$ respectively. These satisfy
$$X^s \subseteq X^{ps} \subseteq X^{ss} \subseteq X.$$
Once we have this, we can then define the quotient as $X^{ps}/G$, or as $X^{ss}/\\!\\!/G$. The first is a genuine quotient of sets, and the second is a "categorical quotient".

### Moment maps

In classical dynamics, we have Hamilton's equations
$$\frac{\mathrm d q}{\mathrm d t} = \frac{\partial H}{\partial p} \quad\text{ and }\quad \frac{\mathrm d p}{\mathrm d t} = -\frac{\partial H}{\partial q}.$$
If we interpret this as the flow of a vector field $X_H$, and we define $\omega = \mathrm d p \wedge \mathrm d q$, then the above can be written as
$$\iota_{X_H}\omega = -\mathrm d H.$$

More generally, if $X$ is a manifold, $\omega$ a non-degenerate closed $2$-form on $X$, then $(X, \omega)$ is called a symplectic manifold. One way to think about them is as the generalisation of phase space from classical dynamics - for any manifold $Q$, the cotangent bundle $T^*Q$ is canonically a symplectic manifold. Another class of examples come from algebraic geometry: $\mathbb C^n$ and $\mathbb {CP}^n$ have canonical symplectic structures, and this makes any smooth affine or projective variety into a symplectic manifold.

Recall Noether's principle, which states (very roughly) "every symmetry has a conserved quantity". We can interpret a symmetry as an action by a compact Lie group $K$, and the corresponding conserved quantity is then called a moment map, denoted by $\mu : X \to \mathrm{Lie}(K)^*$.

One important theorem in this area is the Marsden-Weinstein reduction theorem, which says that under certain conditions, $\mu^{-1}(0)/K$ is again a symplectic manifold. In terms of classical dynamics, one can think of this as a reduced phase space, where we fix $\mu = 0$.

### Kempf-Ness

From the above, we now have two ways to take a quotient. One coming from algebraic geometry, and one from symplectic geometry. The Kempf-Ness theorem states that these two give the same result. That is,

$$X^{ps}/G \cong \mu^{-1}(0)/K$$

and the complex (resp. symplectic) structures on both sides are nicely compatible. Another way to view this is that we can determine stability (which is an algebro-geometric condition) using moment maps (which are symplectic objects).

### General principle

Collecting all of the above, we can now state the general guiding principle for the area. The space of metrics is an infinite dimensional space, and we would like to choose a canonical representative. One way to do this is to write down a PDE which this metric should satisfy. Ideally, this metric is then unique, up to the symmetry group $K$ of the situation. Next, we then interpret the PDE as a zero for a moment map for an appropriate $K$-action. Thus, the existence of a solution to the PDE looks like finding a point in $\mu^{-1}(0)/K$.

By analogy with Kempf-Ness, this should be the "same" as looking at $X^{ps}/G$. Note that even through $G$ may not exist (the complexification of an infinite dimensional Lie group may not exist), we can still make sense of the right hand side. This then gives us:

> A canonical metric exists if and only if a stability condition is satisfied.

This links differential geometry on the left hand side with algebraic geometry on the right hand side.

## Kähler-Einstein metrics

A Kähler-Einstein (KE) metric $\omega$ [^1] is one which satisfies[^2]
$$\mathrm{Ric}(\omega) = \lambda\omega.$$
By rescaling, we can assume that $\lambda \in \\{0, 1, -1\\}$. This value is determined topologically, as $\mathrm{Ric}(\omega) \in c_1(X)$.

When $\lambda = -1$, Aubin and Yau showed that there is always such a metric, and when $\lambda = 0$, Yau showed that such a metric always exist. The case $\mathrm{Ric}(\omega) = 0$ is now called a Calabi-Yau manifold.

In the case of Riemann surfaces/algebraic geometry, this corresponds to the "negatively curved" and the "flat" cases, but we are left with the "positively curved" case. Here, there are obstructions. The Yau-Tian-Donaldson conjecture is that

> A Kähler-Einstein metric with $\lambda = 1$ exists if and only if $X$ is $K$-polystable.

Here, $K$-(poly)stability is an algebro-geometric condition, which is motivated by the Hilbert-Mumford criterion in GIT. Roughly speaking, if an orbit is not (semi/poly)stable, then we can find a one-parameter subgroup $\mathbb C^* \hookrightarrow G$ which destabilises it.

This version of the Yau-Tian-Donaldson conjecture was proven by Chen-Donaldson-Sun, however one can make an analogous statement for constant scalar curvature metrics, which is still open.

## Hermite-Einstein metrics

One can also define a notion of a canonical metric for holomorphic vector bundles. On any fixed holomorphic vector bundle $E \to X$, with a hermitian metric $h$, there is a unique connection, called the Chern connection, which is compatible with the complex structure and the metric. The Hermite-Einstein equation is then

$$\Lambda_\omega(iF) = \lambda \mathrm{id}_E.$$

Here, $\Lambda_\omega : \Omega^2(\mathrm{End}(E)) \to \Omega^0(\mathrm{End}(E))$ is the contraction operator, taking the trace of the form part, and $F$ is the curvature of the Chern connection. The Hitchin-Kobayashi correspondence then states:

> A Hermite-Einstein metric exists if and only if the bundle is slope polystable.

Slope polystability is a notion introduced by Mumford in the study of the moduli of vector bundles on curves. For our purposes, one way to think about it is that any sub-bundle is "less-twisted". This correspondence was proven by Donaldson (when $X$ is projective) and by Uhlenbeck-Yau (for arbitrary Kähler $X$).

## Examples

One interesting question is then: We have a good understanding of the existence of these metrics. Can we write down any explicit examples?

So far, the answer is (mostly) no.

[^1]: Strictly speaking the metric is $g$, and $\omega$ is the symplectic form. But as we are fixing the complex structure, we can recover $g$ from $\omega$ and vice versa.

[^2]: In Riemannian geometry, the Ricci tensor is a symmetric $(0, 2)$-tensor. In Kähler geometry, we use the complex structure to make it into a $(1, 1)$-form. This definition then agrees with the definition of an Einstein metric in Riemannian geometry.