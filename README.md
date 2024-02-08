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
Keeping the following property of logs in mind: $\log_{a}x = [\log_{b}x/\log_{b}a]$

\
First let's show that $\log_{2} n \in O(\log_{5} n)$. That is we must show that $\exists c, n_0: \log_{2} n \leq c \cdot \log_{5} n, \forall n \geq n_0$. 

We can rewrite $\log_{2} n$ as $[\log_{5} n/\log_{5} 2]$ and now we must show that $[\log_{5} n/\log_{5} 2] \leq c \cdot \log_{5} n, \forall n \geq n_0$

$[\log_{5} n/\log_{5} 2] \leq c \cdot \log_{5} n$

$\log_{5} n \leq c \cdot [\log_{5} 2 \cdot \log_{5} n]$

the final line is obviously true and thus we've proven that $\log_{2} n \in O(\log_{5} n) \iff \exists c, n_0: \log_{2} n \leq c \cdot \log_{5} n, \forall n \geq n_0$.

\
Now we can show the reverse, that $\log_{5} n \in O(\log_{2} n)$. To do this we'll use a similar method as above. 

First we'll rewrite $\log_{5} n$ as $[\log_{2} 5 / \log_{2} n]$ and now we must show that $[\log_{2} n / \log_{} 5] \leq c \cdot \log_{2} n, \forall n \geq n_0$

$[\log_{2} n/\log_{2} 5] \leq c \cdot \log_{2} n$

$\log_{2} n \leq c \cdot [\log_{2} 5 \cdot \log_{2} n]$

Once again it is trivial that $\log_{2} n \leq c \cdot [\log_{2} 5 \cdot \log_{2} n]$. 

We've now shown that $\log_{2} n \in O(\log_{5} n)$ and $\log_{5} n \in O(\log_{2} n)$. 

By using the log property: $\log_{a}x = [\log_{b}x/\log_{b}a]$, and the examples above we can see that the only difference between logs of different bases, such as $\log_{a}x$ and $\log_{b}x$ is a constant factor $1/\log_{b}a$, and since asymptotic analysis ignores constants this difference doesn't matter. Thus log bases do not affect asymptotic complexity. 
