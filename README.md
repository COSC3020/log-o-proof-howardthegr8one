[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/fbkbKZ5N)
# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

# My Proof

$T(n) \in O(\log_{5} n)$ if $\exists c, n_0: T(n) \leq c \cdot \log_{5} n, \forall n \geq n_0$. 

We can rewrite $\log_{5} n$ as $[\log_{2} n / \log_{2} 5]$ which gives us

$T(n) \in O(\log_{5} n)$ if $\exists c, n_0: T(n) \leq c \cdot [\log_{2} n / \log_{2} 5], \forall n \geq n_0$. 

Now combine $c$ with our new constant, $1/\log_{2}5$, to get $d_0 = c / \log_{2}5$

$T(n) \in O(\log_{5} n)$ if $\exists c, n_0: T(n) \leq d_0 \cdot \log_{2}n, \forall n \geq n_0$. 

---

$T(n) \in O(\log_{2} n)$ if $\exists c, n_0: T(n) \leq c \cdot \log_{2} n, \forall n \geq n_0$. 

rewrite $\log_{2} n$ as $[\log_{5} n / \log_{5} 2]$

$T(n) \in O(\log_{2} n)$ if $\exists c, n_0: T(n) \leq c \cdot [\log_{5} n / \log_{5} 2], \forall n \geq n_0$. 

combine $c$ with our new constant, $1/\log_{5}2$ to get $d_1 = c / \log_{5}2$

$T(n) \in O(\log_{2} n)$ if $\exists c, n_0: T(n) \leq d_1 \cdot \log_{2}n, \forall n \geq n_0$. 

---

Therefore by using the log property: $\log_{a}x = [\log_{b}x/\log_{b}a]$ and the examples above we've shown $T(n) \in O(\log_{2}n) \wedge T(n) \in O(\log_{5}n)$, proving that asymptotically the only difference between logs of different bases is a constant factor, and since asymptotic analysis ignores lower terms and constants this difference does not affect asymptotic complexity. 
