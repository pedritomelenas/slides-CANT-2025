---
layout: cover
lang: en-en
theme: default
coverAuthorUrl: [https://www.ugr.es/local/pedro]
title: "The isomorphism problem for ideal class monoids of numerical semigroups"
coverDate: ""
background: ""
aspectRatio: 16/10
download: true
fonts:
  # basically the text
  sans: Lato
  # use with `font-serif` css class from UnoCSS
  serif: Robot Slab
  # for code blocks, inline code, etc.
  mono: Fira Code
---

<style>
    h1,h2 {
        color: rgb(60, 122, 169);
    }
    h3,h4 {
        color: darkgrey;
    }
    .slidev-layout h1 + p {
        margin-top: 0rem;
        opacity: 1;
    }
    .katex { font-size: 1.1em; }
</style>

## Some problems related to the ideal class monoid of a numerical semigroup

<br>

**Pedro A. García Sánchez** <br> Departamento de Álgebra and IMAG, Universidad de Granada

<br><br>

### CANT 2025
### CUNY Graduate Center 
#### May 20 - 23, 2025

<br><br><br>

<p style="font-size:0.6em;  line-height: 1.5; text-align: left;">Supported by the grant number ProyExcel_00868 (Proyecto de Excelencia de la Junta de Andalucía) and by the Junta de Andalucía Grant Number FQM-343; grant PID2022-138906NB-C21 funded by MICIU/AEI/10.13039/501100011033 and by ERDF "A way of making Europe", and by the Spanish Ministry of Science and Innovation (MICINN), through the "Severo Ochoa and María de Maeztu Programme for Centres and Unities of Excellence" (CEX2020-001105-M). </p>


---

# Ideals of a numerical semigroup 

For $A,B\subseteq \mathbb{Z}$, we write $A+B=\{a+b : a\in A, b\in B\}$

Let $S$ be a numerical semigroup ($S\subseteq\mathbb{N}$, $0\in S$, $S+S\subseteq S$, $\mathbb{N}\setminus S$ finite)

An **ideal** of $S$ is a non-empty set $I$ of integers such that

- $I+S\subseteq I$
- $z+I\subseteq S$ for some integer $z$ (equivalently, $\min(I)$ exists)

There exists $X\subseteq \mathbb{Z}$ such that $I=X+S$, we can take $X$ to be a finite set of integers

The set $X$ is called a **set of generators** of $I$, and it is a **minimal set of generators** of $I$ if no proper subset of $X$ generates $I$ 

The minimal set of generators of $I$ is unique and equals $\operatorname{Minimals}_{\leq_S}(I)$, where

$$
a\leq_S b \text{ if } b-a\in S
$$

If $I,J$ are ideals of $S$, then $I+J$, $I\cap J$, $I\cup J$ are ideals of $S$ 

---

# The monoid of ideals of a numerical semigroup

Let $S$ be a numerical semigroup and $\mathcal{I}(S)$ the set of ideals of $S$

The set $\mathcal{I}(S)$ is a monoid with respect to the operation $+$, the sum of ideals

Denote by $\mathfrak{P}(S)$ the set of principal ideals of $S$ (that is, the set of ideals of the form $a+S$ for some $a\in S$)

1. $\mathfrak{P}(S)$ is a divisor-closed ($I+J\in \mathfrak{P}(S)$ implies $I,J\in \mathfrak{P}(S)$) submonoid of $\mathfrak{I}(S)$

1. Every (non-trivial) divisor-closed submonoid of $\mathfrak{I}(S)$ contains $\mathfrak{P}(S)$

1. Isomorphisms between monoids send divisor-closed submonoids to divisor-closed submonoids

1. If $S$ and $T$ are numerical semigroups, every isomorphism between $\mathfrak{I}(S)$ and $\mathfrak{I}(T)$ restricts to an isomorphism between $\mathfrak{P}(S)$ and $\mathfrak{P}(T)$

1. The monoid $\mathfrak{P}(S)$ is isomorphic to $S$ (under the map $a\mapsto a+S$)


**Conclusion**: If $\mathcal{I}(S)$ and $\mathcal{I}(T)$ are isomorphic as monoids, then $S=T$

---

# The ideal class monoid 

Let $\mathcal{I}(S)$ be the set of ideals of $S$

We write $I\sim J$ if there exists $z\in\mathbb{Z}$ such that $I=z+J$

The **ideal class monoid** of $S$ is 

$$
 \mathcal{C}\ell(S) = \mathcal{I}(S)/{\sim}  
$$

Addition is defined as $[I]+[J]=[I+J]$

---

# The set of normalized ideals 

Let $\mathcal{I}_0(S) = \{ I\in \mathcal{I}(S) : \min(I)=0 \}$, the set of normalized ideals of $S$

It follows easily that

$$
\mathcal{C}\ell(S)\cong \mathcal{I}_0(S) 
$$

$$
[I]\mapsto -\min(I)+I
$$

For $I\in \mathcal{I}_0(S)$, there exists $g_1,\dots,g_k\in\operatorname{G}(S)=\mathbb{N}\setminus S$ such that 

$$
I=\{0,g_1,\dots,g_k\}+S
$$

Moreover, $\{g_1,\ldots,g_k\}$ can be taken to be an anti-chain with respect to $\le_S$

Thus, $0,g_1,\ldots,g_k$ are the minimal generators of $I$

Thus, the cardinality of $\mathcal{C}\ell(S)$ equals the number of antichains in $(\operatorname{G}(S),\le_S)$

---

# Hasse diagram of normalized ideals wrt inclusion

Let $S$ be a numerical semigroup with multiplicity $m$, that is, $m=\min(S\setminus\{0\})$

<Transform :scale="0.9">

<div class="grid grid-cols-[50%_50%] gap-4">

<div>

- $\min_\subseteq(\mathcal{I}_0(S))=S$
- $\max_\subseteq(\mathcal{I}_0(S))=\mathbb{N}$

- Maximal non-trivial ideals:  
    
    $\{0,1,\dots,i-1,i+m,i+1,\dots,m-1\}+S$

    $|\operatorname{Maximals}_\subseteq(\mathcal{I}_0(S)\setminus\{\mathbb{N}\})|= m-1$

- Minimal non-tivial ideals: 
    
    $\{0,f\}+S$ with $f\in\operatorname{Maximals}_{\le_S}(\mathbb{Z}\setminus S)$
    
    $|\operatorname{Minimals}_\subseteq(\mathcal{I}_0(S)\setminus\{S\})| = \operatorname{t}(S)$, the type of $S$
- Height equals $|\operatorname{G}(S)|+1$, the genus of $S$ plus one

</div>

<div>

<figure>

<img src="/NSGraph4.svg" alt="469-ideal-min-gen" width="95%">

<figcaption align="center">

Hasse diagram of $\footnotesize{(\mathcal{I}_0(\langle 4,6,9\rangle),\subseteq)}$, nodes labelled by sets of minimal generators

</figcaption>
</figure>


</div>

</div>

</Transform>

---

# Can we fully recover $S$ from $(\mathcal{I}_0(S),\subseteq)$?

**Idea**: $\{0,g\}+S\subseteq \{0,g'\}+S$ if and only if $g'\le_S g$

Thus, if we can tell apart the ideals of the form $\{0,g\}+S$, with $g\in \operatorname{G}(S)$, then we recover $(\operatorname{G}(S),\le_S)$

**Result**: The number of non-zero minimal generators of $I$ is precisely the number of elements in the poset $(\mathcal{I}_0(S),\subseteq)$ covered by $I$ 


<div class="absolute left-25% top-44%">

<img src="/469-blind-inclusion.svg" alt="469-ideal" width="40%">

$(\mathcal{I}_0(S),\subseteq)$ 

</div>


<div class="absolute left-55% top-60%">

<img src="/469-gaps-blind.svg" alt="469-gap" class="right" width="40%">

$(\operatorname{G}(S),\le_S)$

</div>


---

# How to fully reconstruct $S$ from $(\operatorname{G}(S),\le_S)$?

**Idea**: counting "divisors"

For $h\in \operatorname{G}(S)$, set $\operatorname{nd}(h)=|\{ h'\in \operatorname{G}(S) : h'\le_S h\}|$

**Result:** For every $h,h'\in \operatorname{G}(S)$, $h\le h'$, 
$$|S\cap [h,h']| = \operatorname{nd}(h')-\operatorname{nd}(h)$$

In a run of gaps, the number of divisors remains constant

In a run of elements of $S$, the number of divisors increases by the length of the run


**Conclusion:** If $S$ and $T$ are numerical semigroups such that the poset $(\mathcal{I}_0(S),\subseteq)$ is isomorphic to $(\mathcal{I}_0(T),\subseteq)$,<br> then $S=T$

---

# Monoid isomorphism problem

If $S$ and $T$ are numerical semigroups such that the monoid $(\mathcal{I}_0(S),+)$ is isomorphic to $(\mathcal{I}_0(T),+)$,<br> can we ensure that  $S=T$?

For $I,J\in \mathcal{I}_0(S)$, write $I\preceq J$ if there exists $K\in \mathcal{I}_0(S)$ such that $I+K=J$


Recall that $S$ is *irreducible* if it is not the intersection of two semigroups properly containing it

### Some observations

1. Oversemigroups of $S$ are precisely the ideals $I$ of $\mathcal{I}_0(S)$ such that $I+I=I$ (idempotent)

1. Unitary extensions of $S$ are minimal idempotents with respect to $\preceq$ (idempotent quarks)

1. The genus of $S$ (the cardinality of $\operatorname{G}(S)$) is the maximum $k$ such that there exists a chain $I_0\prec I_1 \prec \dots \prec I_k$ in $\mathcal{I}_0(S)$

1. For $E\in \mathcal{I}_0(S)$, with $E+E=E$, the set $C_E=\{I\in \mathcal{I}_0(S) : I+E=I\}=\mathcal{I}_0(E)$ 

---

# Monoid isomorphism problem (solution)

If $S$ and $T$ are numerical semigroups such that the monoid $(\mathcal{I}_0(S),+)$ is isomorphic to $(\mathcal{I}_0(T),+)$,<br> then  $S=T$?

1. Apply induction on the genus: $S$ and $T$ have the same genus and the same unitary extensions

1. The intersection of all the unitary extensions of $S\neq \mathbb{N}$ equals $S$ or  $S\cup \{\operatorname{F}(S)\}$ (if $S$ is irreducible) with $\operatorname{F}(S)=\max(\mathbb{Z}\setminus S)$ the Frobenius number of $S$ 


1. $S$ is irreducible if and only if $\mathcal{I}_0(S)$ has at most two quarks; if $S\neq \mathbb{N}$,
    
   - one quark means symmetric ($x\in \mathbb{Z}\setminus S$ if and only if $\operatorname{F}(S)-x\in S$)
    
   - two quarks translates pseudo-symmetry ($\operatorname{F}(S)$ even, $\operatorname{F}(S)/2\neq x\in \mathbb{Z}\setminus S$ if and only if $\operatorname{F}(S)-x\in S$)

1. In the irreducible case, we recover $\operatorname{F}(S)$ from the genus of $S$


---

# The other (unsolved) poset isomorphism

If $S$ and $T$ are numerical semigroups such that the poset $(\mathcal{I}_0(S),\preceq)$ is isomorphic to $(\mathcal{I}_0(T),\preceq)$,<br> can we ensure that  $S=T$?


<div class="absolute left-35% top-25%">

<figure>


<img src="/469-dotm.svg" alt="469-dotm" width="50%">


<figcaption>

<p style="font-size:0.8em">

Hasse diagram of $\mathcal{I}_0(\langle 4,6,9\rangle)$; nodes labelled <br> 
with sets of minimal generators<br> gray nodes are idempotents (oversemigroups)

</p>

</figcaption>

</figure>

</div>
---

# The multiplicity three case

The multiplicity of $S$ is the smallest positive integer in $S$, denoted by $\operatorname{m}(S)$

For $I\in \mathcal{I}_0(S)$, the Apéry set of $I$ is 

$$
\operatorname{Ap}(I) = \{ i \in I : i-\operatorname{m}(S)\notin I \} = \{ 0, i_1,\dots, i_{\operatorname{m}(S)-1} \}
$$
Every $i_j= k_j\operatorname{m}(S)+j$ for some $k_j\in\mathbb{N}$: $(k_1,\dots,k_{\operatorname{m}(S)-1})$ are the Kunz coordinates of $I$

If $\operatorname{m}(S)=3$, then the Kunz coordinates of $I$ are $(k_1,k_2)$ (fulfilling a known set of inequalities depending on the Kunz coordinates of $S$)

The depth of $I$ is the largest $k$ such that there exists a chain $I=I_0\prec I_1\prec \dots \prec I_k=\mathbb{N}$ in $\mathcal{I}_0(S)$

For multiplicity $3$, the depth of $I$ is the sum of its Kunz coordinates

Also, $(\mathcal{I}_0(S),\preceq)$ is a lattice and has at most three quarks

With all this information we can recover the Kunz coordinates of $S$ and thus $S$ itself

In particular, for multiplicity three the isomorphism problem for the poset $(\mathcal{I}_0(S),\preceq)$ is solved

---

# When is the poset $(\mathcal{I}_0(S),\preceq)$ a lattice?

We know when $\preceq$ coincides with $\subseteq$ in $\mathcal{I}_0(S)$ (and thus in this cases the poset is a lattice):

$$
S \in  \{⟨3,4⟩,⟨3,4,5⟩,⟨3,5⟩,⟨3,5,7⟩\} \cup \{⟨2,2k+ 1⟩ : k ∈ N\}.
$$

We also know that if the multiplicity of $S$ is three, then $(\mathcal{I}_0(S),\preceq)$ a lattice

By studying how the posets $(\mathcal{I}_0(S),\preceq)$ and $(\mathcal{I}_0(S\setminus\{a\}),\preceq)$ with $a$ a minimal generator larger than the Frobenius number of $S$ are related, we can show that for multiplicity four the poset $(\mathcal{I}_0(S),\preceq)$ is a lattice 

If $S$ has multiplicity larger than five, then the poset $(\mathcal{I}_0(S),\preceq)$ is not a lattice

**Conclusion**: The poset $(\mathcal{I}_0(S),\preceq)$ is a lattice if and only if $S$ has multiplicity at most four

---

# Related problems

## Irreducible elements

Detect irreducibles with respect to the operations in $\mathcal{I}_0(S)$: $+$, $\cap$, $\cup$

If the poset $(\mathcal{I}_0(S),\preceq)$ is a lattice, with respect to meet and join, and relate these to the above operations


## Factorizations into irreducible elements

Study factorizations of ideals with respect to these operations and irreducible elements

In particular, study factorization invariants of factorizations of numerical semigroups (idempotent ideals) into irreducible numerical semigroups 

---

# Related problems

## Quotient of ideals

We can compute $I+J$, $I\cap J$ and $I\cup J$ for $I,J\in \mathcal{I}_0(S)$, from the Kunz coordinates of $I$ and $J$

A better understanding of the Kunz coordinates of $I-J= \{ z\in \mathbb{Z} : z+J\subseteq I \}$ would be useful


## Reflexive ideals

An ideal $I$ is reflexive if $S-(S-I)=I$

The star operation defined as $I^* = S-(S-I)$ is an involution on $\mathcal{I}_0(S)$

Find a characterization of reflexive ideals in terms of Kunz coordinates

---

# Related problems

## Associated numerical sets of a numerical semigroup

Let $S$ be a numerical semigroup and let $T$ be a cofinite subbset of $\mathbb{N}$ with $0\in T$

We say that $T$ is associated to $S$ if 

$$
S=\{x\in\mathbb{N} : x+T\subseteq T\}
$$

It easily follows that $T$ is associated to $S$ if and only if 
- $T\in \mathcal{I}_0(S)$, and 
- $T-T=S$

There is a one-to-one correspondence between the set of associated numerical sets of $S$ and the set of partitions associated to $S$ (partitions whose hook sets are $\operatorname{G}(S)$)

---
zoom: 0.9
---

# References

- V. Barucci, F. Khouja, On the class semigroup of a numerical semigroup, Semigroup Forum, 92 (2016), 377-392

- S. Bonzio, P. A. García-Sánchez, The poset of normalized ideals of numerical semigroups with multiplicity three, https://arxiv.org/abs/2407.21697

- S. Bonzio, P. A. García-Sánchez, When the divisibility poset of the ideal class monoid of a numerical semigroup is a lattice, https://arxiv.org/abs/2412.07281

- L. Casabella, M. D'Anna, P. A. García-Sánchez Apéry sets and the ideal class monoid of a numerical semigroup, Mediterr. J. Math. 21:7 (2024)

- M. Delgado,  P.A.  García-Sánchez,  and  J. Morais, NumericalSgps, A package for numerical semigroups, Version 1.3.1 (2022), (Refereed GAP package), https://gap-packages.github.io/numericalsgps

- P. A. García-Sánchez, The isomorphism problem for ideal class monoids of numerical semigroups, Semigroup Forum 108 (2024), 365–376.

- P. A. García-Sánchez, Factorizations into irreducible numerical semigroups, https://arxiv.org/abs/2410.13729

- P. A. García-Sánchez, S. Tringali, Semigroups of ideals and isomorphism problems, Proc. Am. Math. Soc. 153 (2025), 2323–2339.


---
layout: cover
background: ""
---

# Thank you for your attention!

Find our more at [numerical-semigroups.github.io](http://numerical-semigroups.github.io/)

[Slides](https://github.com/pedritomelenas/slides-CANT-2025) produced with [slidev](https://es.sli.dev/)

<!--<SlideCurrentNo /> -->