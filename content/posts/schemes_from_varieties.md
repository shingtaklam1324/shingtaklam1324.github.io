+++
title="Schemes from varieties"
date="27 Jan 2025"
math=true
+++

In scheme-theoretic algebraic geometry, we can define a variety as an reduced[^1] separated scheme which is finite type over a field $k$. In this post, we'll start off with the notions of affine and projective varieties from classical algebraic geometry, and then generalise these incrementally, to end up at the definition of a scheme.

First of all, recall that we have a bijection between affine varieties and finitely generated reduced $k$ algebras, given by sending an affine variety $X$ to it's ring of regular functions $k[X]$. If $X$ is given by the ideal $I \trianglelefteq k[x_1, \dots, x_n]$, then $k[X] = k[x_1, \dots, x_n]/\sqrt{I}$. The fact that we take the radical of $I$ means that the coordinate ring is reduced, i.e. it has no non-zero nilpotents. However, we lose geometric information from doing this.

Consider Bezout's theorem: If $C_1, C_2$ are (irreducible projective) plane curves of degree $d_1, d_2$ and $k$ is algebraically closed, then $C_1 \cap C_2$ is at most $d_1d_2$ points. Why "at most"? Consider
$$\\{y = x^2\\} \cap \\{y = t\\}.$$
If $t \ne 0$, then we have two points. However, when $t = 0$, we only have point point, which is $(0, 0)$. Geometrically however, this looks "different" to just a point, there is the additional information which the intersection has "degree 2". As $\sqrt{\langle x^2 \rangle} = \langle x \rangle$, this information is lost in the classical world.

Thus, what we would like to do is consider $k[x_1, \dots, x_n]/I$ instead, without taking the radical. What we have done here, is dropped the condition that the scheme is reduced. In fact, this can be helpful. In the ring $A = k[x]/\langle x^2\rangle$, we can think of $x$ as an "infinitesimal" coordinate, and so we can work with infinitesimals in a rigorous manner. For example, we can define the tangent space as the space of all morphisms from $A$, which gives the analogue of the definition in differential geometry via curves agreeing to first order.

Next, in differential geometry, a manifold is defined to be something which "locally looks like Euclidean space". We would like to do the same thing with schemes. As in differential geometry, gluing spaces together is formally a quotient space. In topology, if we do not glue things carefully, we can end up with non-Hausdorffness. Separated is the scheme theoretic analogue of Hausdorff.

Finally, we would like to drop the finite type over $k$ condition. Suppose we have a polynomial $f \in \mathbb Z[x, y]$. Then it would make sense to ask for solutions to $f = 0$ over $\mathbb Z, \mathbb Q, \mathbb R$ or $\mathbb C$. However, we needed to choose a field when defining varieties. If $X$ is a variety over $K$, and $Y$ is a variety over $L$, in general, there is no way of relating the two. If we forget the fact that our ring was a $k$-algebra, then we can end up with a more "intrinsic" object: a geometric space whose $K$-points correspond to solutions over $K$.

With this, we have dropped all of the assumptions, and we have ended up with just a scheme. On the other hand, defining schemes take a bit more effort than just forgetting properties of varietie. Hopefully this is good motivation for why scheme theory can be considered as a natural generalisation of the notions in classical algebraic geometry.

[^1]: Irreducibility in classical and scheme-theoretic algebraic geometry mean basically the same thing, so we won't assume irreducibility in the definition of a variety - recall that integral is equivalent to irreducible and reduced.
