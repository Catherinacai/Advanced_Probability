# *Measure Space*

why  $\sigma$-algebra?
We construct a $\sigma$-algebra from $\Omega$ to make sure this set is closed under sets operations (intersection, complementation,.. ). Thus the measure defined on it can be well-defined.
The reason we don't just define the measure on the $\Omega$  is that  $\Omega$ is too large there are some redundant elements we are not care about.


Th. $\sigma$-algebras(respectively, algebras) are  closed under countable( respectively, finite) intersections.

just check the definition of  $\sigma$-algebra.

*this theorem suggests that for any set $\mathcal A \subset \Omega$ , we can generate  a smallest $\sigma$-algebra that contains $\mathcal A$ by taking intersection of all the  $\sigma$-algebras containing $\mathcal A$*


Lemma Let$(\Omega,\mathcal F, \mu)$ denote a measure space.
(1) (Continuity from below) if $A_{1}\subseteq A_{2}\subseteq\dots$ are all measurable then $\mu(A_{n})\uparrow \mu(\bigcup_{m=1}^{\infty}A_{m})$ as $n\to \infty$.
(1) (Continuity from above) if $A_{1}\supseteq A_{2}\supseteq\dots$ are all measurable and $\mu(A_{n})<\infty$ for some $n$ , then $\mu(A_{n})\downarrow \mu(\bigcup_{m=1}^{\infty}A_{m})$ as $n\to \infty$.

these are results follow from Lebesgue Measure theory.

# *Lebesgue Measure*

## *The Carathéodory Extension Theorem*
Suppose $\Omega$ is a set, and $\mathcal A$ denotes an *algebra* of subsets of $\Omega$. Given a *countably additive* set function $\mu$ on $\mathcal A$, there exists a measure $\overline\mu$ on $(\Omega,\sigma(\mathcal A))$, such that $\mu(E)=\overline\mu(E)$ for all $E\in\mathcal A$. 
Suppose, in addition, that there exist $\Omega_{1}\subseteq \Omega_{2}\subseteq\dots$ in $\mathcal A$ such that $\bigcup_{m=1}^{\infty}\Omega_{m}=\Omega$ and $\mu(\Omega_{i})<\infty$ for all $i\geq {1}$. Then the extension $\overline{\mu}$ of $\mu$ is *unique* and $\overline\mu$ is a $\sigma-finite$ measure with $\mu(\Omega)=\overline\mu(\Omega)$.

This inspires us that, once we can define a countably additive set function $\mu$ on an algebra $\mathcal A$, we can extend it to become a measure on $(\Omega,\sigma(\mathcal A))$

the way we construct Lebesgue's measure on $(0,1]^d$ for $d\geq {2}$ is just follow the theorem. 
we define measure of hypercube as $$m\left\{x\in(0,1]^d:a_{j}<x_{j}<b_{j}\right\}=\prod_{j=1}^{d}(b_{j}-a_{j})$$since the collection of all finite unions of hypercubes is an algebra that generates $\mathcal B((0,1]^d)$
thus the definition can be extended to $\mathcal B((0,1]^d)$.

Th.(the definition of density function of $\mu$)
Suppose $f:R^d \to R_{+}$ is a *continuous function such that the Riemann integral $\int_{R^d}f(x)dx=1$*. Given $a,b\in R^d$ with $a_{j}\leq b_{j}$ for all $j\leq d$, consider the hypercube $C:=(a_{1},b_{1}]\times\dots\times(a_{d},b_{d}]$, and define $\mu(C)=\int_{C}f(x)dx$. Then $\mu$ extends uniquely to a probability measure on $(R^d,\mathcal B(R^d))$, and $f$ is called the density function of $\mu$.

mark: the collection of all finite unions of disjoint hypercubes of the type mentioned is an algebra of subsets of $R^d$. We can do as we did when we constructed the Lebesgue measure. 


# *Completion*

Thinking: 
Consider the $([0,1],\mathcal B[0,1],m)$, where $m$ is the Lebesgue's measure. We can prove that the Cantor Set $\mathcal C$ satisfies:
1. $\mathcal C \in \mathcal B[0,1]$
2. $m(\mathcal C)=0$
3. the cardinality of $\mathcal C>$ the cardinality of $[0,1]$
these suggests that there exist many subsets of $\mathcal C$ which are not borel sets! For these subsets, they are not measurable. But logically their measure are 0.
There inspires us to attach a strong limitation to prevent these happening.

*Completion Definition*
Given a measure space $(\Omega,\mathcal F,\mu)$, a measurable set $E$ is $null$ if $\mu(E)=0$. The $\sigma-$algebra $\mathcal F$ is said to be $complete$ if *all subsets of null sets are themselves measurable and null*. When $\mathcal F$ is complete, we say also that $(\Omega,\mathcal F,\mu)$ is complete.

We can always ensure completeness.
Th. Given a measure space $(\Omega,\mathcal F,\mu)$, there exists a complete $\sigma-$algebra $\mathcal F'\supseteq \mathcal F$ and a measure $\mu'$ on $(\Omega,\mathcal F')$ such that $\mu$ and $\mu'$ agree on $\mathcal F$.
The measure space $(\Omega,\mathcal F',\mu')$ is called the completion of $(\Omega,\mathcal F,\mu)$.

How to construct?
For any two sets $A$ and $B$ define:
$$
\mathcal F'=\left\{A\subseteq\Omega: \exists B,N\subseteq \mathcal F \ such\ that\  \mu(N)=0\ and\ A\Delta B\subseteq N\right\}
$$
such $\mathcal F'$ is a $\sigma-$algebra.
Define measure $\mu'$:
For any $A\in\mathcal F'$  define $\mu'(A):=\mu(B)$, where $B\in\mathcal F$ is a set such that for a null set $N\in \mathcal F$, $A\Delta B\subseteq N$.
We can prove that $\mu'$ is a measure on $(\Omega,\mathcal F')$.


# *Proof of Carathéodory's Theorem*

Throughout, $\Omega$ is a set and $\mathcal A$ is an algebra of subsets of $\Omega$.

Definition (monotone class)
A collection of subsets of $\Omega$ is a $monotone\ class$
if it is closed under increasing countable unions and decreasing countable intersections.

Prop. An arbitrary intersection of monotone classes is a monotone class. In particular, there exists a smallest monotone class containing $\mathcal A$.

the smallest monotone class containing $\mathcal A$ is written as mc($\mathcal A$), and is called the monotone class generated by $\mathcal A$.

## *The Monotone Class Theorem*
Any monotone class that contains $\mathcal A$ also contains $\sigma(\mathcal A)$. In other words, mc($\mathcal A$)=$\sigma(\mathcal A)$.

proof:
since $\sigma(\mathcal A)$ is a monotone class, then $\sigma(\mathcal A)\supseteq mc(\mathcal A)$.
It suffices to prove that $\sigma(\mathcal A)\subseteq mc(\mathcal A)$.
Consider the following monotone classes:
$$
{\scr{C_{1}}}:=\left\{E\in\sigma(\mathcal A):E^c\in mc(\mathcal A)\right\}
$$
$$
{\scr{C_{2}}}:=\left\{E\in\sigma(\mathcal A):\forall F\in mc(\mathcal A),E\cup F\in mc(\mathcal A)\right\}
$$
$$
{\scr{C_{3}}}:=\left\{E\in\sigma(\mathcal A):\forall F\in\mathcal A,E\cup F\in mc(\mathcal A)\right\}
$$
${\scr{C_{1}}}$ is a monotone class contains $\mathcal A$, thus ${\scr{C_{1}}}\supseteq mc(\mathcal A)$
This means that $mc(\mathcal A)$ is closed under complementation.
${\scr{C_{3}}}$ is a monotone class contains $\mathcal A$, thus ${\scr{C_{3}}}\supseteq mc(\mathcal A)$
By reversing the roles of $E$ and $F$ in the definition of ${\scr{C_{3}}}$ we can see that ${\scr{C_{2}}}\supseteq mc(\mathcal A)$.
Thus $\mathcal A$ is closed under finite unions and is therefore a $\sigma-$algebra.
Consequently, we have $\sigma(\mathcal A)\subseteq mc(\mathcal A)$.


Proof of Carathéodory's Theorem(Existence):

We first define $\overline{\mu}(E)$ for all $E\subseteq\Omega$. This defines a set function $\overline{\mu}$ on the Power set ${\scr P}(\Omega)$ of $\Omega$ which may be too big a $\sigma-$algebra in the sense that $\overline{\mu}$ may fail to be countably additive on ${\scr P}(\Omega)$. However it will be additive on $\sigma(\mathcal A)$.

For all $E\subseteq\Omega$, define:
$$
\overline{\mu}(E):=inf\left\{\sum_{n=1}^{\infty}\mu(E_{n}):\forall j\geq {1},E_{j}\in\mathcal A\ and\ E\subseteq \bigcup_{n=1}^{\infty}E_{n} \right\}
$$
*Step 1. Countable Subadditivity of $\overline{\mu}$*
It is suffices to prove that $\overline{\mu}(\bigcup_{n=1}^{\infty}A_{n} )\leq\sum_{n=1}^{\infty}\overline\mu(A_{n})$ for all $A_{1},A_{2},\dots\subseteq\Omega$.
Consider any collection $\left\{A_{j,n}\right\}$ of elements of $\mathcal A$ such that $A_{n}\subseteq \bigcup_{n=1}^{\infty}A_{j,n}$, by the definition of $\overline{\mu}$,
$$
\overline{\mu}\left( \bigcup_{n=1}^{\infty}A_{n}  \right)\leq \sum_{n=1}^{\infty}\sum_{j=1}^{\infty}\mu(A_{j,n})
$$
also by the definition of inf, for any $\epsilon>0$, we can choose $A_{j,n}$ such that,
$$
\sum_{j=1}^{\infty}\mu(A_{j,n})\leq \frac{\epsilon}{2^n}+\overline{\mu}(A_{n})
$$
whence,
$$
\overline{\mu}\left( \bigcup_{n=1}^{\infty}A_{n}  \right)\leq\epsilon+\sum_{n=1}^{\infty}\overline\mu(A_{n})
$$
since $\epsilon>0$ is arbitrary, this yields the countable subadditivity of $\overline{\mu}$.

*Step 2. $\overline{\mu}$ extends $\mu$*
It is suffices to prove that $\overline{\mu}$ and $\mu$ agree on $\mathcal A$.
$\overline{\mu}(E)\leq \mu(E)$ for all $E\subseteq \mathcal A$.
we seek to prove the converse inequality.
Consider a collection of $E_{1},E_{2},\dots$ of elements of $\mathcal A$ that cover $E$.
For any $\epsilon>0$, we can choose $E_{n}$ such that $\sum_{n=1}^{\infty}\mu(E_{n})\leq\overline{\mu}(E)+\epsilon$.
Since $\mu$ is countably additive on $\mathcal A$,
$$
\mu(E)\leq \mu(\bigcup_{n=1}^{\infty}E_{n})\leq\sum_{n=1}^{\infty}\mu(E_{n})\leq\overline{\mu}(E)+\epsilon.
$$
since $\epsilon>0$ is arbitrary, Step2 is completed.

*Step 3. Countable Additivity*
we now complete our proof by showing that the restriction of $\overline\mu$ to $\sigma(\mathcal A)$ is countable additivity.
thanks to step1, it is suffices to prove that $\overline{\mu}(\bigcup_{n=1}^{\infty}A_{n} )\geq\sum_{n=1}^{\infty}\overline\mu(A_{n})$, for all disjoint $A_{1},A_{2},\dots\in\sigma(\mathcal A)$.
Consider,
$$
{\scr M}=\left\{E\in\Omega:\forall F\in\mathcal A,\overline{\mu}(E)=\overline{\mu}(E\cap F)+\overline{\mu}(E\cap F^c)\right\}
$$
According to step2, $\scr M$ contains $\mathcal A$.
By the Countable Subadditivity of $\overline{\mu}$,
$$
{\scr N:}=\left\{E\in\Omega:\forall F\in\mathcal A,\overline{\mu}(E)\geq\overline{\mu}(E\cap F)+\overline{\mu}(E\cap F^c)\right\}={\scr M}
$$
We can prove that *$\scr N$ is a monotone class containing $\mathcal A$*.
thanks to the Monotone Class Theorem, $mc(\mathcal A)=\sigma(\mathcal A)\subseteq\scr N$
this suggests that $\overline\mu$ is finitely additive on $\sigma(\mathcal A)$, since $A_{n}$ is disjoint, it follows that,
$$
\overline{\mu}\left( \bigcup_{n=1}^{\infty}A_{n}  \right)\geq\overline{\mu}\left( \bigcup_{n=1}^{N}A_{n}  \right)=\sum_{n=1}^{N}\overline\mu(A_{n})
$$
for every $N\geq {1}$.
whence the Carathéodory's Theorem(Existence) follows from letting $N\to \infty$.


Proof of Carathéodory's Theorem(Uniqueness):
If $\mu(\Omega)<\infty$,
Suppose there were two extensions $\overline\mu$ and $\nu$, and define
$$
{\scr C:}=\left\{E\in\sigma(\mathcal A):\overline\mu(E)=\nu(E)\right\}
$$
we can check that $\scr C$ is a monotone class that contains $\mathcal A$
thus $mc(\mathcal A)=\sigma(\mathcal A)\subseteq\scr C$
that is $\overline\mu(E)=\nu(E)$ for all $E\subseteq\sigma(\mathcal A)$ 
If $\mu(\Omega)=\infty$ and $\bigcup_{m=1}^{\infty}\Omega_{m}=\Omega$,  $\mu(\Omega_{i})<\infty$ for all $i\geq {1}$.
for every $n>0$, $E\in\sigma(\mathcal A)$, as we proved before 
$$
\overline\mu(E\cap\Omega_{n})=\nu(E\cap\Omega_{n})
$$
let $n\to \infty$, since $E\cap\Omega_{n}\to E$, using the Continuity from below of measure,
$$
\overline\mu(E)=\lim_{ n \to \infty }\overline\mu(E\cap\Omega_{n})=\lim_{ n \to \infty } \nu(E\cap\Omega_{n})=\nu(E)
$$


