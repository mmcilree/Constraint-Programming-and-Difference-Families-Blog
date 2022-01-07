# Applying Homomorphisms to EDFs

We would like to apply a homomorphism to a group where there exists an external difference family, so we can analyse the properties of the image of the EDF under the homomorphism, preferably in a smaller group.

### **Note 1: Useful homomorphisms may not always exist:**

For example if we have an $(n, m, k, \lambda)$ to an external difference family where $n$ is prime. Then the underlying group $G$ is of prime order.

Suppose there exists a homomorphism $\phi : G \to H$ for some group $H$ where $|H| \leq n$.

$G$ must be the cyclic group of order $n$, so $G = \langle a\rangle$ for some $a \in G$.

Now  $\phi(e_G) = \phi(a^n) = (\phi(a))^n = e_H$.

So the order of the element $\phi(a) \in H$ must both divide $n$ and $|H|$. But $\gcd(n, |H|) = 1$ as $n$ is prime and $|H| \leq n$. So the order of $\phi(a)$ is 1. Hence $\phi(a) = e_H$.

Since for any $x \in G$, $x = a^k$ for some $k \in \mathbb Z$ we have

$\phi(x) = \phi(a^k) = (\phi(a))^k = e_H^k = e_H$.

So the only homomorphism is trivial. Which isn't very interesting.

In fact this argument would hold whenever $|G|$ and $|H|$ are coprime.

### **Note 2: There are examples of a non trivial homomorphisms acting on EDFs:**

**2.1**

Take $\mathbb Z_{10}$. We have a $(10, 2, 3, 2)$-EDF given by the sets:

$\{0, 1, 2\}, \{3, 6, 9\}$

Check:
$$
& 3 - 2 = 1
& 0 - 9 = 1
& 3 - 1 = 2
& 1 - 9 = 2
& 3 - 0 = 3
& 2 - 9 = 3
\\
& 6 - 2 = 4
& 0 - 6 = 4
& 6 - 1 = 5
& 1 - 6 = 5
& 6 - 0 = 6
& 2 - 6 = 6
\\
& 9 - 2 = 7
& 0 - 3 = 7
& 9 - 1 = 8
& 1 - 3 = 8
& 9 - 0 = 9
& 2 - 3 = 9
\\
$$
There are 2 occurences of each non zero element.

Define a mapping $\phi : \mathbb Z_{10} \to \mathbb Z _5$ by $\phi (x) = x \mod 5$.

For $x, y \in \mathbb Z_{10}$, 
$$
\begin{align}
\phi (x + y) &\equiv x + y \equiv \phi(x) + \phi(y)
\end{align}
$$
So this is a homomorphism. The image of the EDF is:

$\{0, 1, 2\}, \{3, 1, 4\}$

Note the disjoint property has been lost (so not an EDF). However:
$$
& 1 - 1 = 0
& 0 - 4 = 1
& 2 - 1 = 1
& 3 - 2 = 1
& 1 - 0 = 1
& 0 - 3 = 2
\\
& 1 - 4 = 2
& 3 - 1 = 2
& 4 - 2 = 2
& 1 - 3 = 3
& 2 - 4 = 3
& 3 - 0 = 3
\\
& 4 - 1 = 3
& 0 - 1 = 4
& 2 - 3 = 4
& 1 - 2 = 4
& 4 - 0 = 4
$$
We still have a constant (4) number of occurences of the non-zero elements of the group as external differences. Will this always happen?

Check a couple more examples:

**(2.2)**

$\phi : \mathbb Z_{10} \to \mathbb Z _5$ by $\phi (x) = 3x \mod 5$. The image of the EDF is:

$\{0,3,1\}, \{4, 3, 2\}$
$$
& 3 - 3 = 0
& 0 - 4 = 1
& 3 - 2 = 1
& 4 - 3 = 1
& 2 - 1 = 1
& 0 - 3 = 2
\\
& 1 - 4 = 2
& 3 - 1 = 2
& 2 - 0 = 2
& 0 - 2 = 3
& 1 - 3 = 3
& 4 - 1 = 3
\\
& 3 - 0 = 3
& 3 - 4 = 4
& 1 - 2 = 4
& 4 - 0 = 4
& 2 - 3 = 4
$$
Again 4 occurences each of the non-zero elements of the group.

**(2.3)**

$\phi : \mathbb Z_{10} \to \mathbb Z _5$ by $\phi (x) = x \mod 2$

Image is $\{0,1\}, \{0, 1\}$ (note here the set sizes have also decreased).

Obviously we'll get a constant number of occurences of the single non-zero element here.

**(2.4)**

An example with a different EDF:

Take $\mathbb Z_{3} \times \mathbb Z_3$. 

There is a $(9, 2, 4, 4)$-EDF given by

$\{(1, 0), (0, 1), (2, 0), (0, 2)\}, \{(1, 1), (1, 2), (2, 1), (2, 2)\} $

Check:
$$
& (1, 0) - (1, 2) = (0, 1)
& (2, 0) - (2, 2) = (0, 1)
& (1, 1) - (1, 0) = (0, 1)
\\
& (2, 1) - (2, 0) = (0, 1)
& (1, 0) - (1, 1) = (0, 2)
& (2, 0) - (2, 1) = (0, 2)
\\
& (1, 2) - (1, 0) = (0, 2)
& (2, 2) - (2, 0) = (0, 2)
& (0, 1) - (2, 1) = (1, 0)
\\
& (0, 2) - (2, 2) = (1, 0)
& (1, 1) - (0, 1) = (1, 0)
& (1, 2) - (0, 2) = (1, 0)
\\
& (2, 0) - (1, 2) = (1, 1)
& (0, 2) - (2, 1) = (1, 1)
& (1, 2) - (0, 1) = (1, 1)
\\
& (2, 1) - (1, 0) = (1, 1)
& (0, 1) - (2, 2) = (1, 2)
& (2, 0) - (1, 1) = (1, 2)
\\
& (1, 1) - (0, 2) = (1, 2)
& (2, 2) - (1, 0) = (1, 2)
& (0, 1) - (1, 1) = (2, 0)
\\
& (0, 2) - (1, 2) = (2, 0)
& (2, 1) - (0, 1) = (2, 0)
& (2, 2) - (0, 2) = (2, 0)
\\
& (1, 0) - (2, 2) = (2, 1)
& (0, 2) - (1, 1) = (2, 1)
& (1, 1) - (2, 0) = (2, 1)
\\
& (2, 2) - (0, 1) = (2, 1)
& (1, 0) - (2, 1) = (2, 2)
& (0, 1) - (1, 2) = (2, 2)
\\
& (1, 2) - (2, 0) = (2, 2)
& (2, 1) - (0, 2) = (2, 2)
$$
$\phi : \mathbb Z_3 \times \mathbb Z_3 \to \mathbb Z _3$ by $\phi (x, y) = x$

Note for $(a, b), (c,d) \in \mathbb Z_3 \cross \mathbb Z_3$, $\phi((a, b) + (c, d)) = \phi(a + b, c + d) = a + c = \phi(a, b) + \phi(c, d)$.

So this is a homomorphism.

The image of the EDF would be:

$\{1, 0, 2\}, \{1, 2\}$. Note the sizes of the sets are no longer the same, as well as the sets no longer being disjoint. However:
$$
& 1 - 1 = 0
& 2 - 2 = 0
& 0 - 2 = 1
& 2 - 1 = 1
& 1 - 0 = 1
& 1 - 2 = 2
\\
& 0 - 1 = 2
& 2 - 0 = 2
$$
Once again, 3 occurences of 1s and 3 occurences of 2s.

**(2.5)**

Here's an example of one that isn't an SEDF. Take the 3 sets.
$$
D_1 = \{(1, 2), (2, 1), (2, 2), (2, 3), (3, 2)\}, 
     D_2 = \{(0, 1), (0, 3), (1, 3), (2, 0), (3, 1)\},
     D_3 = \{(0,2), (1, 0), (1, 1), (3, 0), (3,3)\}
$$
A similar check to those above will show that this is an EDF. To see that it is not an SEDF note that the differences from $D_1$ to the other sets yields:
$$
& (1, 2) - (1, 1) = (0, 1)
& (2, 1) - (2, 0) = (0, 1)
& (3, 2) - (3, 1) = (0, 1)
\\
& (1, 2) - (1, 0) = (0, 2)
& (2, 2) - (2, 0) = (0, 2)
& (3, 2) - (3, 0) = (0, 2)
\\
& (1, 2) - (1, 3) = (0, 3)
& (2, 3) - (2, 0) = (0, 3)
& (3, 2) - (3, 3) = (0, 3)
\\
& (1, 2) - (0, 2) = (1, 0)
& (2, 1) - (1, 1) = (1, 0)
& (2, 3) - (1, 3) = (1, 0)
\\
& (1, 2) - (0, 1) = (1, 1)
& (2, 1) - (1, 0) = (1, 1)
& (2, 2) - (1, 1) = (1, 1)
\\
& (2, 1) - (1, 3) = (1, 2)
& (2, 2) - (1, 0) = (1, 2)
& (2, 3) - (1, 1) = (1, 2)
\\
& (3, 2) - (2, 0) = (1, 2)
& (1, 2) - (0, 3) = (1, 3)
& (2, 2) - (1, 3) = (1, 3)
\\
& (2, 3) - (1, 0) = (1, 3)
& (2, 1) - (0, 1) = (2, 0)
& (2, 2) - (0, 2) = (2, 0)
\\
& (2, 3) - (0, 3) = (2, 0)
& (1, 2) - (3, 1) = (2, 1)
& (2, 2) - (0, 1) = (2, 1)
\\
& (2, 3) - (0, 2) = (2, 1)
& (3, 2) - (1, 1) = (2, 1)
& (1, 2) - (3, 0) = (2, 2)
\\
& (2, 1) - (0, 3) = (2, 2)
& (2, 3) - (0, 1) = (2, 2)
& (3, 2) - (1, 0) = (2, 2)
\\
& (1, 2) - (3, 3) = (2, 3)
& (2, 1) - (0, 2) = (2, 3)
& (2, 2) - (0, 3) = (2, 3)
\\
& (3, 2) - (1, 3) = (2, 3)
& (2, 1) - (3, 1) = (3, 0)
& (2, 3) - (3, 3) = (3, 0)
\\
& (3, 2) - (0, 2) = (3, 0)
& (2, 1) - (3, 0) = (3, 1)
& (2, 2) - (3, 1) = (3, 1)
\\
& (3, 2) - (0, 1) = (3, 1)
& (1, 2) - (2, 0) = (3, 2)
& (2, 1) - (3, 3) = (3, 2)
\\
& (2, 2) - (3, 0) = (3, 2)
& (2, 3) - (3, 1) = (3, 2)
& (2, 2) - (3, 3) = (3, 3)
\\
& (2, 3) - (3, 0) = (3, 3)
& (3, 2) - (0, 3) = (3, 3)
$$
The differences occur a different number of times, so this doesn't satisfy the strong property.

But still, if we apply the obvious homomorphism:

$\phi : \mathbb Z_4 \times \mathbb Z_4 \to \mathbb Z _3$ by $\phi (x, y) = x$

and obtain the images of the original sets:
$$
\{1, 2, 3\},
     \{0, 1, 2, 3\},
     \{0, 1, 3\}
$$

$$
& 1 - 1 = 0
& 2 - 2 = 0
& 3 - 3 = 0
& 0 - 0 = 0
\\
& 1 - 0 = 1
& 2 - 1 = 1
& 3 - 2 = 1
& 0 - 3 = 1
\\
& 1 - 3 = 2
& 2 - 0 = 2
& 3 - 1 = 2
& 0 - 2 = 2
\\
& 1 - 2 = 3
& 2 - 3 = 3
& 3 - 0 = 3
& 0 - 1 = 3
$$

Four copies of each of the non-zero elements of $\mathbb Z_4$. Perhaps let's call this structure an Overlapping External Difference Family **OEDF**.

**(2.6)**

In $\mathbb Z_{10}$ we have: $\{9, 0, 5, 4\}, \{1, 3, 8, 6\}$, a $(10, 2, 4, 4)$-EDF
$$
& 9 - 8 = 1
& 4 - 3 = 1
& 1 - 0 = 1
& 6 - 5 = 1
\\
& 0 - 8 = 2
& 5 - 3 = 2
& 1 - 9 = 2
& 6 - 4 = 2
\\
& 9 - 6 = 3
& 4 - 1 = 3
& 3 - 0 = 3
& 8 - 5 = 3
\\
& 0 - 6 = 4
& 5 - 1 = 4
& 3 - 9 = 4
& 8 - 4 = 4
\\
& 9 - 3 = 6
& 4 - 8 = 6
& 1 - 5 = 6
& 6 - 0 = 6
\\
& 0 - 3 = 7
& 5 - 8 = 7
& 1 - 4 = 7
& 6 - 9 = 7
\\
& 9 - 1 = 8
& 4 - 6 = 8
& 3 - 5 = 8
& 8 - 0 = 8
\\
& 0 - 1 = 9
& 5 - 6 = 9
& 3 - 4 = 9
& 8 - 9 = 9
\\
$$
Using the same homomorphism as in **2.1** we get:

$\{4, 0\}, \{1, 3\}$
$$
& 4 - 3 = 1
& 1 - 0 = 1
& 0 - 3 = 2
& 1 - 4 = 2
& 4 - 1 = 3
& 3 - 0 = 3
\\
& 0 - 1 = 4
& 3 - 4 = 4
$$
Which is in fact also an EDF

### Note 3: EDF images have at least 1 shared property:

**Conjecture 3.1:**

Suppose the sets $A_1, \dots A_m$ make up an $(n, m, k, \lambda)$-EDF in a group $G$.

Then for any homomorphism $\phi : G \to H$ where $H$ is a group with $|H| \leq |G|$

the sets $\phi(A_1), \dots \phi(A_m)$ satisfy, for some $l \in \mathbb N$
$$
\sum_{i=1}^mN_i(\delta) = l \qquad \forall \delta \in H\backslash e_H
$$
where $N'_i(\delta)$ is the number of occurences of $\delta$ as an external difference from the set $\phi A_i$.

**Partial Proof:**

Since $|H| \leq |G|$, $\phi$ must be surjective by the pigeonhole principle.

Let $h \in H$ and write $P$ for the pre-image of $h$, that is, $\{g \in G : \phi(g) = h\}$.

Since $\phi$ is surjective, $P$ is non empty, so let $g \in P$.

Now write $\ker \phi g$ for $\{xg : x \in \ker \phi \}$.

If $a \in \ker\phi g$ then $a = xg$ for $x \in \ker \phi$

So $\phi(a) = \phi(xg) = \phi(x)\phi(g) = \phi(g) = h$, and therefore $a \in P$.

If $b \in P$ then $\phi(b) = h$
$$
\begin{align}
&\implies \phi(b) = \phi(g) \\
&\implies bg^{-1} \in \ker \phi \\
&\implies bg^{-1}g \in \ker \phi g \\
&\implies b \in \ker \phi g
\end{align}
$$
So $P = \ker \phi g$

And note that $x \mapsto xg$ is an obvious bijection between $\ker \phi$ and $\ker \phi g$.

So $|P| = |\ker \phi|$.

Hence the same number of elements in $G$ map to each element of $H$. Call this number $t$.

Now for any $p \in P$, if $p = s_1s_2^{-1}$ for $s_1 \in A_i$, $s_2 \in A_j$, and $i \neq j$, then $\phi(p) = \phi(s_1)(\phi(s_2))^{-1}$.

So $h = \phi(s_1)(\phi(s_2))^{-1}$ where $\phi(s_1) \in \phi A_i$ and $\phi(s_2) \in \phi A_j $.

_________

So maybe for each $p \in P$, $h$ occurs as an external difference between sets $\phi A_i$, $\phi A_j$ exactly $\lambda$ times? Hence overall $h$ occurs as an external difference between sets $\lambda t$ times?

Clearly not: see example 2.4. $\lambda = 3, t = 3$ but $l$ from the conjecture above is also $3$.

_____

We might have the situation where:

$p = s_1s_2^{-1}$ $p = s_3s_4^{-1}$ for $s_1, s_3 \in A_i$, $s_2, s_4 \in A_j$ and $i \neq j$, BUT

$\phi(s_1) = \phi(s_3)$ and $\phi(s_2) = \phi(s_4)$ (so we'd be double counting).

Indeed that is what is happening in example 2.4:
$$
\{(1, 0), \bold{(0, 1)}, (2, 0), \bold{(0, 1)}\}, \{\bold{(1, 1)}, \bold{(1, 2)}, (2, 1), (2, 2)\}
$$

Maybe there's a counterexample.

### 



