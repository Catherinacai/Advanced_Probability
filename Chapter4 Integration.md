
Throughout $(\Omega,\scr F,\mu)$ denotes a measure space.

# *Measurable Functions*

Def(Random variables)
A function $f:\Omega\to R^n$ is (Borel) $measurable$ if $f^{-1}(E)\in\scr F$ for all $E\in{\scr B}(R^n)$. Measurable functions on probability space are often referred to as $random\ variables$.

Lemma( an easier way to check the measurability)
If $\scr A$ is an *algebra that generates ${\scr B}(R^n)$* and  $f^{-1}(A)\in\scr F$ for all $A\in\scr A$, then $f:\Omega\to R^n$ is measurable.

Proof: check that $\left\{{\scr A}\in{\scr B}(R^n):f^{-1}(A)\in\scr F\right\}$ is a monotone class containing $\scr A$. Using the monotone class theorem.


# *Modes of Convergence*

Throughout, $f_{1},f_{2},\dots:\Omega\to R$ are measurable.

Def(convergence almost everywhere)
We say that $f_{n}$ convergences to $f$ $\mu-almost\ everywhere$ ($\mu-a.e.$) if
$$
\mu\left( \left\{\omega\in\Omega:\lim_{ n \to \infty }\sup\left|f_{n}(\omega)-f(\omega)\right|>0 \right\} \right)=0
$$
equivalently
$$
\mu\left( \left\{\bigcup_{l=1}^{\infty}\bigcap_{N=1}^{\infty}\bigcup_{n=N}^{\infty}\left|f_{n}(\omega)-f(\omega)\right|> \frac{1}{l}\right\} \right)=0
$$
when $(\Omega,\scr F,\mu)$ is probability space and $X,X_{1},X_{2},\dots$ are random variables on this space, we say instead that $X_{n}$ convergences to $X$ $almost\ surely$ (a.s)

Def(convergence $L^p(\mu)$ and in measure)
We say that $f_{n}\to f$ in $L^p(\mu)$ if $\lim_{ n \to \infty }\left\|f_{n}-f\right\|_{p}=0$
also, $f_{n}\to f$ in measure if $\lim_{ n \to \infty }\mu\left\{\left|f_{n}-f\right|\geq\epsilon\right\}=0$

Th.
Either a.e.-convergence or $L^p$-convergence implies convergence in measure.
Conversely, if $sup_{j\geq n}\left|f_{j}\right|\to0$ in measure, then $f\to 0$ almost everywhere.

*Markov's Inequality*
If $f\in L^1(\mu)$, then for all $\lambda>0$,
$$
\mu\left\{\left|f\right|>\lambda\right\}\leq \frac{1}{\lambda}\int_{\left\{\left|f\right|>\lambda\right\}}\left|f\right|d\mu\leq \frac{\left\|f\right\|_{1}}{\lambda}
$$
proof
$$
\int_{\left\{\left|f\right|>\lambda\right\}}\left|f\right|d\mu\geq \int_{\left\{\left|f\right|>\lambda\right\}} \lambda d\mu=\lambda \mu{\left\{\left|f\right|>\lambda\right\}}
$$
this yields the first inequality.
the second one trivial to check.

applying the result to $L^p$ space we have
*Chebyshev's Inequality*
for all $\lambda>0$, $p>0$ and $f\in L^p(\mu)$,
$$
\mu\left\{\left|f\right|>\lambda\right\}\leq \frac{1}{\lambda^p}\int_{\left\{\left|f\right|>\lambda\right\}}\left|f\right|^pd\mu\leq \frac{\left\|f\right\|_{p}}{\lambda^p}
$$

Proof of Th.
The chebyshev's inequality suggests that $L^p$-convergence implies convergence in measure.

$f_{n}\to f$ a.e. iff $\mu\left( \left\{\bigcap_{N=1}^{\infty}\bigcup_{n=N}^{\infty}\left|f_{n}(\omega)-f(\omega)\right|\geq \epsilon\right\} \right)=0$, for all $\epsilon>0$
since $\mu$ is continuous from above,
$$
f_{ n}\to f\ a.e.\ \iff\ \lim_{ N \to \infty }\mu(\bigcup_{n=N}^{\infty}\left|f_{n}(\omega)-f(\omega)\right|\geq \epsilon)=0\ \ \ \forall \epsilon>0
$$
because $\mu\left\{\left|f_{n}-f\right|\geq\epsilon\right\}=0\leq \mu(\bigcup_{n=N}^{\infty}\left|f_{n}(\omega)-f(\omega)\right|\geq \epsilon)$
that is if $f_{n}\to f$ a.e. then $f_{n}\to f$ in measure

finally, if $sup_{j\geq n}\left|f_{j}\right|\to0$ in measure them
$$
\mu\left( \left\{\bigcap_{N=1}^{\infty}\bigcup_{n=N}^{\infty}\left\{sup_{j\geq n}\left|f_{j}\right|\right\}\geq \epsilon\right\} \right)=\lim_{ n \to \infty }\mu(sup_{j\geq n}\left|f_{j}\right|\geq\epsilon)=0
$$
for all $\epsilon>0$
thus $\limsup_{ m \to \infty }\left|f_{m}\right|\leq  \limsup_{n }sup_{j\geq n}\left|f_{j}\right|<\epsilon$ a.e.
Let $N(\epsilon)$ denotes *the set of $\omega$'s for which the inequality fails*,
since $\lim_{m}\left|f_{m}\right|<\epsilon$ a.s., for all $\epsilon\in Q_{+}$
$$\mu\left\{\bigcup_{{\epsilon\in Q_{+}}}N(\epsilon)\right\}=0$$
as $Q$ is dense in $R$ 
thus $f_{n}\to 0$ a.e.


# *The Radon-Nikodým Theorem*

Q: Given two measures $\mu$ and $\nu$ , one can ask, "when can we find a function $\pi_{\star}$ such that for *all measurable sets $A$*, $\nu(A)=\int_{A}\pi_{\star}d\mu$ ?"
Suppose $\mu$ denotes the Lebesgue's measure and the function $\pi_{\star}$ is a probability density function, then the prescription $\nu(A):=\int_{A}\pi_{\star}d\mu$ defines a probability measure $\nu$.

Def(absolutely continuous)
Given two measures $\mu$ and $\nu$ on $(\Omega,\scr F)$, we say that $\nu$ is $absolutely\ continuous$ with respect to $\mu$ (written $\nu\ll \mu$) if $\nu(A)=0$ for all $A\in\scr F$ such that $\mu(A)=0$.

*The Radon-Nikodým Theorem*
If $\nu\ll \mu$ are two *finite measures* on $(\Omega,\scr F)$, then there exists a non-negative $\pi_{\star}\in L^1(\mu)$ such that $\int fd\nu=\int f\pi_{\star}d\mu$ for all *bounded measurable functions* $f:\Omega\to R$. Furthermore, $\pi_{\star}$ is unique up to a $\mu$-null set.

Remark:
Frequently we write $\pi_{\star}:=\frac{d\nu}{d\mu}$. The function $\pi_{\star}$ is called the Radon-Nikodým derivative of $\nu$ with respect to $\mu$.

Proof:
First, we proof the theorem under the stronger domination condition that $\nu(A)\leq \mu(A)$ for all $A\in\scr F$

Step1. The Case $\nu\leq \mu$
Consider the linear functional ${\scr L}(f)=\int fd\nu$ that acts on all $f\in L^1(\nu)$. By the Cauchy-Schwarz inequality,
$$
\left|{\scr L}(f)\right|^2\leq \nu(\Omega)\int\left|f\right|^2d\mu
$$
Hence $\scr L$ is bounded linear functional on $L^2(\mu)$
Since the *$L^2(\mu)$ is a Hilbert Space, using the Reisz represent Theorem*,  there exists a $\mu$-almost everywhere unique $\pi\in L^2(\mu)$ such that $\int fd\nu=\int f\pi d\mu$ for all $f\in L^2(\mu)$
choose an $\alpha>0$ and replace $f$ by $\mathcal 1_{\left\{\pi\leq-\alpha\right\}}$, then,
$$
\nu\left\{\pi\leq-\alpha\right\}=\int\mathcal 1_{\left\{\pi\leq-\alpha\right\}} d\nu=\int 1_{\left\{\pi\leq-\alpha\right\}}\pi d\mu\leq-\alpha \mu\left\{\pi\leq-\alpha\right\}\leq0
$$
this happens only when $\mu\left\{\pi\leq-\alpha\right\}=0$
It follows from right continuity of $\mu$ that $\pi\geq0$ a.e.$[\mu]$
That is we have established the theorem for all $f\in L^2(\mu)$.
*Especially, the theorem holds for all simple functions*.
By the monotone convergence theorem this fact holds for all measurable $f\geq {0}$, using the same construction from establishing the integral, we see that the theorem follows with $\pi_{\star}=\pi$.

Step2. General $v,\mu$.
Since $\nu\leq(\mu+\nu)$, Step1 exacts a $(\mu+\nu)$-a.e. unique and non-negative $\pi\in L^2(\mu+\nu)$ such that $\int fd\nu= \int f\pi d(\mu+\nu)$ for all $f\in L^2(\mu+\nu)$.
that is $\int f(1-\pi)d\nu= \int f \pi d\mu$
Replace $f$ by $\mathcal 1_{\left\{\pi\geq1\right\}}$, we have $\mu(\pi\geq{1})=0$. Consequently,
$$
\int_{\pi\leq1} f(1-\pi)d\nu= \int_{\pi\leq1} f \pi d\mu\ \ \ \ \forall f\in L^2(\mu+\nu)
$$
By the monotone convergence theorem this fact holds for all measurable $f\geq {0}$.
Replace $f$ by $f(1-\pi)^{-1}{\mathcal 1}_{\left\{\pi<1\right\}}$, and consider $\Pi:=\pi(1-\pi)^{-1}{\mathcal 1}_{\left\{\pi<1\right\}}$
Then $\int_{\pi\leq1} fd\nu= \int_{\pi\leq1} f \Pi d\mu$ for all measurable $f\geq {0}$.
*Since $\nu\ll \mu$ ,then $\mu(\pi\geq{1})=0$ implies that $\nu(\pi\geq{1})=0$*, hence for all measurable $f\geq {0}$, 
$$
\int fd\nu= \int f \Pi d\mu
$$
Plug in $f\equiv {1}$, we have $\int\Pi d\mu=\nu(\Omega)<\infty$
It follows that $\Pi\in L^1(\mu)$, and the theorem concludes with $\pi_{\star}=\Pi$.

Step3. Uniqueness.
Suppose that there exists $\pi_{\star},\pi^\star\in L^1(\mu)$ such that $\int f\pi_{\star}d\mu=\int f\pi^{\star}d\mu$ for all bounded measurable functions $f:\Omega\to R$.
we shall prove that $\pi_{\star}=\pi^\star$ a.e.$[\mu]$.
fix $\epsilon>0$ and define $f=\mathcal 1_{A(\epsilon)}$, where $A(\epsilon):=\left\{\omega\in\Omega:\pi^{\star}(\omega)\geq\pi_{\star}(\omega)+\epsilon\right\}$,then,
$$
\int f\pi_{\star}d\mu=\int f\pi^{\star}d\mu\geq \int f(\pi_{\star}+\epsilon)d\mu=\int f\pi_{\star}d\mu+\epsilon \mu(A(\epsilon))
$$
since $\int f\pi_{\star}d\mu\leq \left\|\pi_{\star}\right\|_{L^1(\mu)}<\infty$, this suggests that $\mu(A(\epsilon))=0$ for all $\epsilon>0$. By the continuity properties of measures
$$
0=\lim_{ \epsilon \to 0,\epsilon\in Q}\mu(A(\epsilon))=\mu\left( \bigcup_{\epsilon>0,\epsilon\in Q}A(\epsilon) \right).
$$
this shows that $\mu(A(\epsilon))=0$ a.e. That is $\pi^\star\leq \pi_{\star}$ a.e.$[\mu]$
Reverse the roles of $\pi^\star$ and $\pi_{\star}$ shows that $\pi^\star=\pi_{\star}$ a.e.$[\mu]$.



