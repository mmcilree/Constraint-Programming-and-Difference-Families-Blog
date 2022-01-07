# Ammending the previous conjecture

## 1 A counterexample to the previous conjecture

(**Conjecture 8.3.1**)

Suppose the sets $A_1, \dots A_m$ make up an $(n, m, k, \lambda)$-EDF in a group $G$.

Then for any homomorphism $\phi : G \to H$ where $H$ is a group with $|H| \leq |G|$

the sets $\phi(A_1), \dots \phi(A_m)$ satisfy, for some $l \in \mathbb N$
$$
\sum_{i=1}^mN_i(\delta) = l \qquad \forall \delta \in H\backslash e_H
$$
where $N'_i(\delta)$ is the number of occurences of $\delta$ as an external difference from the set $\phi A_i$.

**Counterexample 1.1**

$\{0, 1, 6\}, \{2, 3, 5\}$ in $\mathbb Z_{10}$?

It is an EDF:
$$
& 6 - 5 = 1
& 2 - 1 = 1
& 2 - 0 = 2
& 3 - 1 = 2
& 6 - 3 = 3
& 3 - 0 = 3
\\
& 6 - 2 = 4
& 5 - 1 = 4
& 0 - 5 = 5
& 5 - 0 = 5
& 1 - 5 = 6
& 2 - 6 = 6
\\
& 0 - 3 = 7
& 3 - 6 = 7
& 0 - 2 = 8
& 1 - 3 = 8
& 1 - 2 = 9
& 5 - 6 = 9
\\
$$
Image is: $\{0, 1\}, \{2, 3, 0\}$ under the homomorphism $\phi (x) = x \mod 5$

Differences are:
$$
& 0 - 0 = 0
& 1 - 0 = 1
& 2 - 1 = 1
& 0 - 3 = 2
& 2 - 0 = 2
& 3 - 1 = 2
\\
& 0 - 2 = 3
& 1 - 3 = 3
& 3 - 0 = 3
& 1 - 2 = 4
& 0 - 1 = 4
$$
Note there is 2 occurences of 1 and 4, and 3 occurences of 2 and 3, so this is not an OEDF.

## 2 Rethinking the conjecture

It was interesting how many of the examples in Post 8 worked however. Could the conjecture hold when the EDF is strong?

