---
title: Rigid Objects
date: 2025-04-20
author: Isky Mathews
math: true
---

This is the first actual blog post on this group blog and I thought I'd start us off with something fairly fun & relaxed. This is a topic I like to think about every now and then when I encounter a new type of object in my studies:

> We say that an object $X$ in a category is **rigid** if the only isomorphism $X \to X$ is the identity morphism.

For example, the only rigid sets are the empty set or the singleton. The question is: what are the rigid objects in various categories we care about? The answer to this question can vary between being completely easy to inconceivably intractable (such that it doesn't really seem realistic there will be a nice characterisation of such objects).

 In this post, we'll go through some examples I've worked out or thought about and maybe interested audience members can contribute in the comments rigid objects in the areas they study.

## Vector Spaces

This is probably the next simplest example beyond sets. First notice, that if you're a rigid vector space $V$ over a field $k$ then if $\{e_i\}_{i \in I}$ is a basis, we get a nonidentity linear isomorphism simply by permuting $e_1, e_2$ so there must be at most one basis element.

Then we must split into cases:

- If $k = \mathbb{Z} / 2 \mathbb{Z}$, then the zero vector space and $k$ are both rigid.
- If $k$ doesn't have characteristic 2, then scaling by any nonzero $\lambda \neq 1$ is a nonidentity isomorphism $k \to k$ so $k$ fails to be rigid. Thus the only rigid vector space is the zero space in this case.

## Groups

Again, we start by assuming $G$ is rigid and see what constraints this gives us. Well a big supply of automorphisms is the inner ones: conjugation by some element $g\in G$ sending $h \mapsto ghg^{-1}$. Rigidity tells us that $h = ghg^{-1}$ for every $g,h \in G$ or in other words that $G$ is abelian!

This is exciting as for abelian groups, inverting elements is actually a group homomorphism: $$(gh)^{-1} = h^{-1}g^{-1} = g^{-1}h^{-1}$$ and since it's an involution which fixes the identity it must be an isomorphism. Thus rigidity tells us that $g^{-1} = g \iff g^2 = 1$ or, in additive notation, we can think of it as $2g = 0$. Thus $G$ is none other than vector space over $\mathbb{Z} / 2 \mathbb{Z}$!

Reducing to our previous case above, we see that the rigid groups are precisely the trivial group and $\mathbb{Z} / 2\mathbb{Z}$.

These are actually the only two categories I'm going to mention where I have a simple & complete characterisation of the rigid objects. Already, for example, for monoids it seems a lot more tough than the groups case as the above proof catastrophically fails without the ability to invert elements (e.g. $\mathbb{N}$ is a rigid monoid!). Perhaps Francesco could tell us the rigid inverse semigroups?

## Spaces

To give an idea, about why some categories might fail to have any kind of simple characterisation think about the categories of graphs or metric spaces (or really anything metric-y enough). The rigid metric spaces are kind of anything which are sufficiently asymmetric that there's no rotational or other kind of symmetry to them (most of the characters written in the font of this page would work!). Similarly, the rigid graphs are mainly just those which are horribly messy.

Something else which might count as a notion of space is manifolds. Note that if a manifold $M$ is of dimension $n>0$, then any point is contained in a chart and then it's possible to pullback a nonidentity smooth diffeomorphism of a ball containing the image of that point in $R^n$ to get a nonidentity diffeomorphism $M\to M$. Thus $M$ has dimension zero and thus must be a single point to be rigid. So here the classification was very simple!

If we decide to expand our search to look at all topological spaces, it suddenly becomes very complicated again. Clearly a point works but is that everything? After some thought, I came up with the following infinite class of examples. For $n \in \mathbb{N}$, construct a space from the ordered set $1 < 2 < \ldots < n$ by having the open sets $\{\}, \{1\}, \{1,2\}, \{1,2,3\}, \ldots, \{1,\ldots, n \}$; any homeomorphism from itself to itself can be proven to be the identity by induction.

This seems to be far from all of the rigid spaces & in fact this appears to be somewhat of an active research topic. For an interesting or exotic example of another rigid topological space, consider the *Golomb space* as discussed on my own blog [here](n-simplex.github.io/).

## Rings

What are the rigid rings? Again I am far from a complete classification but I have a couple of fun examples:

1. $\mathbb{Z}, \mathbb{Q}, \mathbb{Z} / n\mathbb{Z}$ for all $n \in \mathbb{N}$ all work for the simple reason that every ring isomorphism sends $1 \mapsto 1$ and in these cases that alone completely guarantees that the map is the identity!
2. $\mathbb{R}$ is also rigid! Why? The key idea is that *positivity is definable algebraically*, in particular we have that $x \geq 0 \iff x = y^2$ for some $y \in \mathbb{R}$. As a result, any ring isomorphism $\mathbb{R} \to \mathbb{R}$ preserves the property of *being positive* and thus preserves orderings $x \geq y \iff 0 \geq y-x$. Then since we already know that $\mathbb{Q}$ is fixed and it is dense in the reals, we know that $\mathbb{R}$ is fixed and the isomorphism is the identity. In fact, this proof shows that any subring of the reals closed under taking square-roots when possible is rigid (e.g. the real algebraic numbers).
3. Another supply of characteristic zero rigid fields are field extensions of $\mathbb{Q}$ with trivial Galois group. For example, $\mathbb{Q}(\sqrt[3]{2})$ works! I'm not sure if there's any nice characterisation of such field extensions: perhaps someone with better Galois theory knowledge could enlighten us?
4. If we turn our sights to finite fields, notice that the Frobenius automorphism of $\mathbb{F}_{p^n}$ precisely fixes the copy of $\mathbb{F}_p$ and nothing else so $n = 1$. Thus the finite rigid fields are precisely $\mathbb{Z} / p \mathbb{Z}$ for primes $p$.

There are a lot of questions I would love to answer here. Are there any other rigid finite rings people can find other than $\mathbb{Z} / n \mathbb{Z}$? I suspect, additionally, that the $p$-adic integers and also $\mathbb{Q}_p$ will be rigid (with a proof along the lines of $\mathbb{R}$ being rigid since the metric is kind of algebraically defined) but I haven't quite worked it through.

Also, the algebraic geometers among us reading about the last section on spaces and now this section on rings are probably wondering about what are the rigid schemes. We probably can't find a complete characterisation but can anyone offer in the comments an example of a **rigid scheme that isn't affine**? I'm not sure really where to start as most of the examples of non-affine schemes are far from rigid (think projective space or the plane-without-a-point).

## Categories

As a category theorist, I couldn't refrain from thinking about the rigid categories! Now, given most categories of categories are really 2-categories there is a little bit of choice about this definition: I'm going to state that a category $\mathcal{C}$ is *rigid* if every autoequivalence $\mathcal{C}\to \mathcal{C}$ is naturally isomorphic to the identity functor.

There are plenty of examples of rigid categories and plenty of non-rigid ones. It's not difficult to see that

- $\text{Mon}$, the category of monoids
- $\text{Pos}$, the category of partially ordered sets
- $\text{Ring}$, the category of non-commutative rings

are not rigid because in each case they have a kind of $(-)^\text{op}$ functor sending the monoid to the opposite monoid, the poset to the opposite poset etc. and these functors are automorphisms (since they are involutions) but are not isomorphic to the identity functor since this would require each object in these categories to be isomorphic to its opposite (which is almost never true).

On the other hand, the principle seems to be that in reasonable categories of objects where there is no obvious candidate for $(-)^{\text{op}}$ then it will be rigid. The simplest example is $\text{Set}$: any autoequivalence $F:\text{Set} \to \text{Set}$ must send the singleton $\{ * \}$ to a singleton set $F\{ * \}$ since it preserves terminal objects.

But every set $S$ is a canonical coproduct of copies of $\{ * \}$, so since equivalences preserve coproducts we see that $F(S)$ is a canonical coproduct of copies of the singleton $F\{ * \}$ and in fact $F$ is naturally isomorphic to $\text{Hom}(F * , -)$. But then $$F \cong \text{Hom}(F * , -) \cong \text{Hom}( * , -) \cong \text{Id}$$

Another example which is easy to show is the ($\text{Ab}$-enriched) category $R\text{-Mod}$ of $R$-modules for $R$ a PID. An ($\text{Ab}$-enriched) autoequivalence $F$ is a left adjoint & a right adjoint so by the Eilenberg-Watts Theorem (discussed in the homological algebra course!) we know that it is naturally isomorphic to a functor of the form $\text{Hom}(M, -)$ for some $R$-module $M$. But since it's an equivalence we know that it must preserve surjections so $M$ is projective. But if $R$ is a PID (or local or probably many other conditions) all projective modules are free, so $M \cong R^S$ for some set $S$. But then $$F \cong \text{Hom}(M,-) \cong (-)^S$$ is an equivalence so $S$ is a singleton and $F$ is naturally isomorphic to the identity functor!

Online you can find various other arguments showing that lots of other categories are rigid, such as the categories of schemes, rings or groups. In most of these cases, the main part of the argument is to prove that some special object (respectively $\text{Spec}\, \mathbb{Z}[x], \mathbb{Z}[x], \mathbb{Z}$) is preserved by the autoequivalence and then you show that's sufficient for the autoequivalence to be naturally isomorphic to the identity.

# Summary

That's it for now! There are many other possible categories where I haven't given it much thought (e.g. posets) and lots of questions which I'm sure can be answered by people with a lot more specialist knowledge than me! I'd love to hear any thoughts or other examples down in the comments.

Finally, it's been suggested that every post should have at least one photo (whether it's directly relevant to the post or not!), so I thought I'd include this image of a bunny:

![a picture of a bunny looking expectantly at the camera](../Bunny.jpg)
