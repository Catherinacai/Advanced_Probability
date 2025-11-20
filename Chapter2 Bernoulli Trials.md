Below $S_{n}$ denotes the total number of successes, and has the binomial distribution with parameters $n$ and $p$.

# *Bernoulli's law of Large Number*
$p$ does not depend on $n$,then for any $\epsilon>0$ 
$$
\lim_{ n \to \infty }P\left\{ \left\vert \frac{S_{n}}{n}-p\right\vert>\epsilon\right\}=0
$$
It follows at once from Chebyshev's inequality

## *Chebyshev's inequality*
For all $n>0$, $\epsilon>0$
$$
P\left\{ \left\vert S_{n}-np\right\vert>n\epsilon \right\}\leq \frac{p(1-p)}{n\epsilon^2} 
$$

proof:
$$
\begin{align}
P\left\{ \left\vert S_{n}-np\right\vert>n\epsilon \right\}&=\sum_{0\leq k\leq n,\left\vert k-np\right\vert>\epsilon}\binom{n}{k}p^k(1-p)^k \\
&\leq\sum_{0\leq k\leq n,\left\vert k-np\right\vert>\epsilon}\left( \frac{k-np}{n\epsilon} \right)^2\binom{n}{k}p^k(1-p)^k \\
&\leq \frac{1}{(n\epsilon)^2}\sum_{k=0}^{n}(k-np)^2\binom{n}{k}p^k(1-p)^k \\ \\
&=\frac{varSn}{(n\epsilon)^2}=\frac{p(1-p)}{n\epsilon^2}

\end{align}
$$
# *The de Moivre-Laplace Central Limit Therom*
$p$ does not depend on n, then for all finite numbers $a<b$,
$$
\lim_{ n \to \infty } P\left\{ a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq b\right\}=P\{a<N(0,1)\leq b\}
$$

to estimate $\binom{n}{k}$ ,we only need to estimate $k!$ for all $k$. Then we have result below

## *de Movire's Formula*
There exists $\beta \in(0, +\infty)$ such that
$$
n!\sim\beta n^{n+1/2}e^{-n}\ \ \ \ \ \ \ \ \ \ \ \ \ as\ n\to\infty
$$

proof:
define: $f(n)=\frac{n!}{\beta n^{n+1/2}e^{-n}}$
$f(1)=e$, then we can write $f(n)$ as
$$
f(n)=e\prod_{k=2}^{n}\frac{f(k)}{f(k-1)}=\exp\left\{ 1+\sum_{k=2}^{n}\ln f(k)-\ln f(k-1) \right\}
$$
as $k\to \infty$,
$$
ln f(k)-\ln f(k-1)=1+\left( k-\frac{1}{2}\ \right)\ln\left( 1-\frac{1}{k} \right)\sim-\frac{1}{12k^2}
$$
since
$$
\sum_{k=2}^{\infty}\ln f(k)-\ln f(k-1)<\infty
$$
we have the result.

proof of The de Moivre-Laplace CLT:
let $q=1-p$
$$
\begin{align}
P\left\{ a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq b\right\}&=\sum_{np+a\sqrt{ npq }<k\leq np+b\sqrt{ npq }}\binom{n}{k}p^kq^{n-k} \\
&=\sum_{a\sqrt{ npq }<\lambda\leq b\sqrt{ npq }}\binom{n}{\lambda+np}p^{\lambda+np}q^{nq-k}
\end{align}
$$
The index $k$ is in $\{0,...,n\}$, while $\lambda$ runs over all real numbers of the form $k-np$,
let us call any $\lambda$ of this form an $n-admissible$ number.
According to the de Movire's Formula:
as $n\to\infty$:
$$
\binom{n}{\lambda+np}\sim \frac{1}{\beta \sqrt{ npq }}\left( \frac{\lambda}{n}+p\right)^{-\lambda-np}\left( q-\frac{\lambda}{n} \right)^{-nq{+\lambda}}
$$
for all $n-admissible$ number $\lambda\in \left[ a\sqrt{ npq },b\sqrt{ npq } \right]$
Thus as $n\to\infty$:
$$
P\left\{ a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq b\right\}\sim\frac{1}{\beta \sqrt{ npq }}\sum_{a\sqrt{ npq }<\lambda\leq b\sqrt{ npq}}\left( \frac{\lambda}{n}+p\right)^{-\lambda-np}\left( q-\frac{\lambda}{n} \right)^{-nq{+\lambda}}
$$
since as $n\to\infty$:
$$
\left( \frac{\lambda}{n}+p\right)^{-\lambda-np}\left( q-\frac{\lambda}{n} \right)^{-nq{+\lambda}}\sim e^{-\lambda^2/2npq}
$$
and by the definition of Riemann integrals:
$$
P\left\{ a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq b\right\}\sim\frac{1}{\beta \sqrt{ npq }}\int_{a\sqrt{ npq }}^{b\sqrt{ npq }}e^{-x^2/2npq}dx
$$
that is 
$$
\lim_{ n \to \infty } P\left\{ a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq b\right\}=\int_{a}^b \frac{e^{-\frac{x^2}{2}}}{\beta}dx=\frac{\sqrt{ 2\pi }}{\beta}\int_{a}^{b}\phi(x)dx
$$
$\phi(x)$ demotes the standard-normal density function.

we then proof that $\beta=\sqrt{ 2\pi }$

By chebyshev's inequality:
$$
1\geq P\left\{ -a<\frac{Sn-np}{\sqrt{ np(1-p) }}\leq a\right\}\geq 1-\frac{1}{a^2}
$$
for all $n>0$, $a>0$
let $n\to\infty$:
$$
\frac{\beta}{\sqrt{ 2\pi }}\geq\\\int_{-a}^{a}\phi(x)dx\geq\frac{\beta}{\sqrt{ 2\pi }}(1-\frac{1}{a^2})
$$
let $a\to\infty$:
$$
\int_{-\infty}^{\infty}\phi(x)dx=\frac{\beta}{\sqrt{ 2\pi }}=1
$$
thus $\beta=\sqrt{ 2\pi }$


we verify that $\beta=\sqrt{ 2\pi }$, we have the Stiring formula:
## *Stiring Formula:*
$$
n!\sim n^{n+1/2}e^{-n}\sqrt{ 2\pi }\ \ \ \ \ \ \ \ \ \ \ \ \ as\ n\to\infty
$$
