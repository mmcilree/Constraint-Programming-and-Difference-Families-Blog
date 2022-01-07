# Homomorphic Images of SEDFs

Recall: I have defined an "OEDF" to mean a set family that satisfies the (S)EDF property except the sets do not have to be disjoint (and so there may be some number of 0s occuring in the differences)

## 10.0 SEDF in C3xC3

$$
\begin{array}{ c|cccc }
 & (1, 0) & (0, 1) & (2, 0) & (0, 2) & \\
 - \\
\hline
(1, 1) & (0, 2) & (2, 0) & (1, 2) & (2, 1) & \\
(1, 2) & (0, 1) & (2, 2) & (1, 1) & (2, 0) & \\
(2, 1) & (2, 2) & (1, 0) & (0, 2) & (1, 1) & \\
(2, 2) & (2, 1) & (1, 2) & (0, 1) & (1, 0) & \\
\end{array}
\qquad 
\begin{array}{ c|cccc }
 & (1, 1) & (1, 2) & (2, 1) & (2, 2) & \\
 -\\
\hline
(1, 0) & (0, 1) & (0, 2) & (1, 1) & (1, 2) & \\
(0, 1) & (1, 0) & (1, 1) & (2, 0) & (2, 1) & \\
(2, 0) & (2, 1) & (2, 2) & (0, 1) & (0, 2) & \\
(0, 2) & (1, 2) & (1, 0) & (2, 2) & (2, 0) & \\
\end{array}
$$

Recall from the previous post that the images of this formed an OEDF.

## 10.1 SEDF in D10

Consider the Dihedral group of degree 10 with the usual generators $\alpha$ and  $\beta$ ($\alpha$ being the rotation and $\beta$ being the reflection).
$$
\{e, \alpha, \beta\}, \{\beta\alpha, \alpha^3, \beta\alpha^4\}
$$
is a non-abelian (10, 2, 3, 1)-SEDF.
$$
& \alpha - \beta\alpha = \beta & \beta\alpha - \alpha = \beta & \beta - \beta\alpha = \alpha & \beta\alpha^4 - \beta = \alpha & e - \beta\alpha = \beta\alpha & \beta\alpha - e = \beta\alpha \\
& e - \alpha^3 = \alpha^2 & \alpha^3 - \alpha = \alpha^2 & \beta - \alpha^3 = \beta\alpha^2 & \alpha^3 - \beta = \beta\alpha^2 & \alpha - \alpha^3 = \alpha^3 & \alpha^3 - e = \alpha^3 \\
& \alpha - \beta\alpha^4 = \beta\alpha^3 & \beta\alpha^4 - \alpha = \beta\alpha^3 & \beta - \beta\alpha^4 = \alpha^4 & \beta\alpha - \beta = \alpha^4 & e - \beta\alpha^4 = \beta\alpha^4 & \beta\alpha^4 - e = \beta\alpha^4 \\
$$
There are 3 possible homomorphic images, corresponding to quotients by the three normal subgroups ($\{e\}$, $\langle \alpha \rangle$ and $D_{10}$ itself). 

1. The trivial homomorphism $f : D_{10} \to \{e\}$, in which the SEDF has image $\{\{e\}, \{e\}\}$ (vacuous OEDF).
2.  The homomorphism given by $f: D_{10} \to \langle \beta \rangle$ given by $f(\alpha^i\beta^j) = \beta^j$. Here the SEDF has image:

$$
\{e, \beta\}, \{e, \beta\}
$$

​		This is clearly an OEDF.

3. The homomorphism mapping the group to itself, which retains the SEDF structure (and so is also an OEDF).

Often in the examples there are only one or two interesting homomorphic images, since 

## 10.2 SEDF in C5xC5

In the group $\mathbb Z_5 \cross \mathbb Z_5$
$$
\{(0, 0), (1, 0), (0, 1), (2, 0), (0, 2), (3, 0), (2, 1), (1, 2), (2, 3), (1, 4), (3, 3), (3, 4)\}, \\
\{(1, 1), (0, 3), (3, 1), (2, 2), (1, 3), (0, 4), (4, 1), (3, 2), (4, 2), (2, 4), (4, 3), (4, 4)\}
$$
is an SEDF. 
$$
\begin{array}{ c|cccccccccccc }
 & (0, 0) & (1, 0) & (0, 1) & (2, 0) & (0, 2) & (3, 0) & (2, 1) & (1, 2) & (2, 3) & (1, 4) & (3, 3) & (3, 4) & \\
 - & \\
\hline
(1, 1) & (4, 4) & (0, 4) & (4, 0) & (1, 4) & (4, 1) & (2, 4) & (1, 0) & (0, 1) & (1, 2) & (0, 3) & (2, 2) & (2, 3) & \\
(0, 3) & (0, 2) & (1, 2) & (0, 3) & (2, 2) & (0, 4) & (3, 2) & (2, 3) & (1, 4) & (2, 0) & (1, 1) & (3, 0) & (3, 1) & \\
(3, 1) & (2, 4) & (3, 4) & (2, 0) & (4, 4) & (2, 1) & (0, 4) & (4, 0) & (3, 1) & (4, 2) & (3, 3) & (0, 2) & (0, 3) & \\
(2, 2) & (3, 3) & (4, 3) & (3, 4) & (0, 3) & (3, 0) & (1, 3) & (0, 4) & (4, 0) & (0, 1) & (4, 2) & (1, 1) & (1, 2) & \\
(1, 3) & (4, 2) & (0, 2) & (4, 3) & (1, 2) & (4, 4) & (2, 2) & (1, 3) & (0, 4) & (1, 0) & (0, 1) & (2, 0) & (2, 1) & \\
(0, 4) & (0, 1) & (1, 1) & (0, 2) & (2, 1) & (0, 3) & (3, 1) & (2, 2) & (1, 3) & (2, 4) & (1, 0) & (3, 4) & (3, 0) & \\
(4, 1) & (1, 4) & (2, 4) & (1, 0) & (3, 4) & (1, 1) & (4, 4) & (3, 0) & (2, 1) & (3, 2) & (2, 3) & (4, 2) & (4, 3) & \\
(3, 2) & (2, 3) & (3, 3) & (2, 4) & (4, 3) & (2, 0) & (0, 3) & (4, 4) & (3, 0) & (4, 1) & (3, 2) & (0, 1) & (0, 2) & \\
(4, 2) & (1, 3) & (2, 3) & (1, 4) & (3, 3) & (1, 0) & (4, 3) & (3, 4) & (2, 0) & (3, 1) & (2, 2) & (4, 1) & (4, 2) & \\
(2, 4) & (3, 1) & (4, 1) & (3, 2) & (0, 1) & (3, 3) & (1, 1) & (0, 2) & (4, 3) & (0, 4) & (4, 0) & (1, 4) & (1, 0) & \\
(4, 3) & (1, 2) & (2, 2) & (1, 3) & (3, 2) & (1, 4) & (4, 2) & (3, 3) & (2, 4) & (3, 0) & (2, 1) & (4, 0) & (4, 1) & \\
(4, 4) & (1, 1) & (2, 1) & (1, 2) & (3, 1) & (1, 3) & (4, 1) & (3, 2) & (2, 3) & (3, 4) & (2, 0) & (4, 4) & (4, 0) & \\
\end{array}
$$

$$
\begin{array}{ c|cccccccccccc }

 & (1, 1) & (0, 3) & (3, 1) & (2, 2) & (1, 3) & (0, 4) & (4, 1) & (3, 2) & (4, 2) & (2, 4) & (4, 3) & (4, 4) & \\
- & \\
\hline
(0, 0) & (1, 1) & (0, 3) & (3, 1) & (2, 2) & (1, 3) & (0, 4) & (4, 1) & (3, 2) & (4, 2) & (2, 4) & (4, 3) & (4, 4) & \\
(1, 0) & (0, 1) & (4, 3) & (2, 1) & (1, 2) & (0, 3) & (4, 4) & (3, 1) & (2, 2) & (3, 2) & (1, 4) & (3, 3) & (3, 4) & \\
(0, 1) & (1, 0) & (0, 2) & (3, 0) & (2, 1) & (1, 2) & (0, 3) & (4, 0) & (3, 1) & (4, 1) & (2, 3) & (4, 2) & (4, 3) & \\
(2, 0) & (4, 1) & (3, 3) & (1, 1) & (0, 2) & (4, 3) & (3, 4) & (2, 1) & (1, 2) & (2, 2) & (0, 4) & (2, 3) & (2, 4) & \\
(0, 2) & (1, 4) & (0, 1) & (3, 4) & (2, 0) & (1, 1) & (0, 2) & (4, 4) & (3, 0) & (4, 0) & (2, 2) & (4, 1) & (4, 2) & \\
(3, 0) & (3, 1) & (2, 3) & (0, 1) & (4, 2) & (3, 3) & (2, 4) & (1, 1) & (0, 2) & (1, 2) & (4, 4) & (1, 3) & (1, 4) & \\
(2, 1) & (4, 0) & (3, 2) & (1, 0) & (0, 1) & (4, 2) & (3, 3) & (2, 0) & (1, 1) & (2, 1) & (0, 3) & (2, 2) & (2, 3) & \\
(1, 2) & (0, 4) & (4, 1) & (2, 4) & (1, 0) & (0, 1) & (4, 2) & (3, 4) & (2, 0) & (3, 0) & (1, 2) & (3, 1) & (3, 2) & \\
(2, 3) & (4, 3) & (3, 0) & (1, 3) & (0, 4) & (4, 0) & (3, 1) & (2, 3) & (1, 4) & (2, 4) & (0, 1) & (2, 0) & (2, 1) & \\
(1, 4) & (0, 2) & (4, 4) & (2, 2) & (1, 3) & (0, 4) & (4, 0) & (3, 2) & (2, 3) & (3, 3) & (1, 0) & (3, 4) & (3, 0) & \\
(3, 3) & (3, 3) & (2, 0) & (0, 3) & (4, 4) & (3, 0) & (2, 1) & (1, 3) & (0, 4) & (1, 4) & (4, 1) & (1, 0) & (1, 1) & \\
(3, 4) & (3, 2) & (2, 4) & (0, 2) & (4, 3) & (3, 4) & (2, 0) & (1, 2) & (0, 3) & (1, 3) & (4, 0) & (1, 4) & (1, 0) & \\
\end{array}
$$




Taking the homomorphism mapping to the first element of each tuple:
$$
\{0, 1, 2, 3\}, \{0, 1, 2, 3, 4\}
$$
We have differences
$$
& 0 - 0 = 0 & 1 - 1 = 0 & 2 - 2 = 0 & 3 - 3 = 0 \\
& 0 - 4 = 1 & 1 - 0 = 1 & 2 - 1 = 1 & 3 - 2 = 1 & 4 - 3 = 1 \\
& 0 - 3 = 2 & 1 - 4 = 2 & 2 - 0 = 2 & 3 - 1 = 2 & 4 - 2 = 2 \\
& 0 - 2 = 3 & 1 - 3 = 3 & 2 - 4 = 3 & 3 - 0 = 3 & 4 - 1 = 3 \\
& 0 - 1 = 4 & 1 - 2 = 4 & 2 - 3 = 4 & 3 - 4 = 4 & 4 - 0 = 4
$$
So an OEDF.

## 10.3 SEDF in C26

$\{0, 1, 2, 3, 4\}, \{5, 10, 15, 25\}$
$$
\begin{array}{ c|ccccc }
 & 0 & 1 & 2 & 3 & 4 & \\
 - & \\
\hline
5 & 21 & 22 & 23 & 24 & 25 & \\
10 & 16 & 17 & 18 & 19 & 20 & \\
15 & 11 & 12 & 13 & 14 & 15 & \\
20 & 6 & 7 & 8 & 9 & 10 & \\
25 & 1 & 2 & 3 & 4 & 5 & \\
\end{array}
\qquad 
\begin{array}{ c|ccccc }
 & 5 & 10 & 15 & 20 & 25 & \\
- & \\
\hline
0 & 5 & 10 & 15 & 20 & 25 & \\
1 & 4 & 9 & 14 & 19 & 24 & \\
2 & 3 & 8 & 13 & 18 & 23 & \\
3 & 2 & 7 & 12 & 17 & 22 & \\
4 & 1 & 6 & 11 & 16 & 21 & \\
\end{array}
$$
Under homomorphism $x \mapsto x \mod 13$

$\{0, 1, 2, 3, 4\}, \{5, 10, 2, 12\}$
$$
\begin{array}{ c|ccccc }
 & 0 & 1 & 2 & 3 & 4 & \\
- \\
\hline
5 & 8 & 9 & 10 & 11 & 12 & \\
10 & 3 & 4 & 5 & 6 & 7 & \\
2 & 11 & 12 & 0 & 1 & 2 & \\
7 & 6 & 7 & 8 & 9 & 10 & \\
12 & 1 & 2 & 3 & 4 & 5 & \\
\end{array}
\qquad 
\begin{array}{ c|ccccc }

 & 5 & 10 & 2 & 7 & 12 & \\
 - \\
\hline
0 & 5 & 10 & 2 & 7 & 12 & \\
1 & 4 & 9 & 1 & 6 & 11 & \\
2 & 3 & 8 & 0 & 5 & 10 & \\
3 & 2 & 7 & 12 & 4 & 9 & \\
4 & 1 & 6 & 11 & 3 & 8 & \\
\end{array}
$$
Another **OEDF**

## 10.4 SEDF in D50

Take the following family of sets of elements in the Dihedral group of order 50 (with standard generators $\alpha$ and $\beta$)
$$
\{e, \alpha, \alpha^{2}, \alpha^{3}, \beta, \beta\alpha, \beta\alpha^{2}\}, \{\alpha^{7}, \alpha^{14}, \alpha^{21}, \beta\alpha^{10}, \beta\alpha^{3}, \beta\alpha^{17}, \beta\alpha^{24}\}
$$

This is an SEDF - easiest to demonstrate via difference tables, as follows:
$$
\begin{array}{ c|ccccccc }
 & e & \alpha & \alpha^{2} & \alpha^{3} & \beta & \beta\alpha & \beta\alpha^{2} & \\
\times (\;\cdot\;)^{-1} & \\
\hline
\alpha^{7} & \alpha^{18} & \alpha^{19} & \alpha^{20} & \alpha^{21} & \beta\alpha^{18} & \beta\alpha^{19} & \beta\alpha^{20} & \\
\alpha^{14} & \alpha^{11} & \alpha^{12} & \alpha^{13} & \alpha^{14} & \beta\alpha^{11} & \beta\alpha^{12} & \beta\alpha^{13} & \\
\alpha^{21} & \alpha^{4} & \alpha^{5} & \alpha^{6} & \alpha^{7} & \beta\alpha^{4} & \beta\alpha^{5} & \beta\alpha^{6} & \\
\beta\alpha^{10} & \beta\alpha^{10} & \beta\alpha^{9} & \beta\alpha^{8} & \beta\alpha^{7} & \alpha^{10} & \alpha^{9} & \alpha^{8} & \\
\beta\alpha^{3} & \beta\alpha^{3} & \beta\alpha^{2} & \beta\alpha & \beta & \alpha^{3} & \alpha^{2} & \alpha & \\
\beta\alpha^{17} & \beta\alpha^{17} & \beta\alpha^{16} & \beta\alpha^{15} & \beta\alpha^{14} & \alpha^{17} & \alpha^{16} & \alpha^{15} & \\
\beta\alpha^{24} & \beta\alpha^{24} & \beta\alpha^{23} & \beta\alpha^{22} & \beta\alpha^{21} & \alpha^{24} & \alpha^{23} & \alpha^{22} & \\
\end{array}
\qquad
\begin{array}{ c|ccccccc }
 & \alpha^{7} & \alpha^{14} & \alpha^{21} & \beta\alpha^{10} & \beta\alpha^{3} & \beta\alpha^{17} & \beta\alpha^{24} & \\
\times (\;\cdot\;)^{-1} & \\
\hline
e & \alpha^{7} & \alpha^{14} & \alpha^{21} & \beta\alpha^{10} & \beta\alpha^{3} & \beta\alpha^{17} & \beta\alpha^{24} & \\
\alpha & \alpha^{6} & \alpha^{13} & \alpha^{20} & \beta\alpha^{9} & \beta\alpha^{2} & \beta\alpha^{16} & \beta\alpha^{23} & \\
\alpha^{2} & \alpha^{5} & \alpha^{12} & \alpha^{19} & \beta\alpha^{8} & \beta\alpha & \beta\alpha^{15} & \beta\alpha^{22} & \\
\alpha^{3} & \alpha^{4} & \alpha^{11} & \alpha^{18} & \beta\alpha^{7} & \beta & \beta\alpha^{14} & \beta\alpha^{21} & \\
\beta & \beta\alpha^{18} & \beta\alpha^{11} & \beta\alpha^{4} & \alpha^{15} & \alpha^{22} & \alpha^{8} & \alpha & \\
\beta\alpha & \beta\alpha^{19} & \beta\alpha^{12} & \beta\alpha^{5} & \alpha^{16} & \alpha^{23} & \alpha^{9} & \alpha^{2} & \\
\beta\alpha^{2} & \beta\alpha^{20} & \beta\alpha^{13} & \beta\alpha^{6} & \alpha^{17} & \alpha^{24} & \alpha^{10} & \alpha^{3} & \\
\end{array}
$$
We can see that each element of $D_{50}$ occurs exactly once in each of the tables, and so we have a $(50, 2, 7, 1)$-SEDF. Furthermore, this is an example of an SEDF occurring in a non-abelian group. 

We now consider homomorphic images of this SEDF. There are two non-trivial proper normal subgroups (justify?) of $D_{50}$ and so two non-isomorphic images (aside from the identity and the whole group) under homormorphisms (justify?). These are $\Z_2$ and $D_{10}$. The $\mathbb Z_2$ case is not so interesting (trivially an OEDF), but the $D_{10}$ case gives us the following SEDF image:
$$
\{e, \beta, \alpha, \beta\alpha, \alpha^{2}, \beta\alpha^{2}, \alpha^{3}\} \{\beta, \alpha, \alpha^{2}, \beta\alpha^{2}, \beta\alpha^{3}, \alpha^{4}, \beta\alpha^{4}\}
$$

Note that this occurs under the obvious homomorphism which maps each element to the corresponding element in $D_{10}$ with the power of $\alpha$ mod 5. External differences are:
$$
\begin{array}{ c|ccccccc }
 & e & \beta & \alpha & \beta\alpha & \alpha^2 & \beta\alpha^2 & \alpha^3 & \\
\times (\;\cdot\;)^{-1} & \\
\hline
\beta & \beta & e & \beta\alpha^4 & \alpha^4 & \beta\alpha^3 & \alpha^3 & \beta\alpha^2 & \\
\alpha & \alpha^4 & \beta\alpha^4 & e & \beta & \alpha & \beta\alpha & \alpha^2 & \\
\alpha^2 & \alpha^3 & \beta\alpha^3 & \alpha^4 & \beta\alpha^4 & e & \beta & \alpha & \\
\beta\alpha^2 & \beta\alpha^2 & \alpha^2 & \beta\alpha & \alpha & \beta & e & \beta\alpha^4 & \\
\beta\alpha^3 & \beta\alpha^3 & \alpha^3 & \beta\alpha^2 & \alpha^2 & \beta\alpha & \alpha & \beta & \\
\alpha^4 & \alpha & \beta\alpha & \alpha^2 & \beta\alpha^2 & \alpha^3 & \beta\alpha^3 & \alpha^4 & \\
\beta\alpha^4 & \beta\alpha^4 & \alpha^4 & \beta\alpha^3 & \alpha^3 & \beta\alpha^2 & \alpha^2 & \beta\alpha & \\
\end{array}
\qquad
\begin{array}{ c|ccccccc }
 & \beta & \alpha & \alpha^2 & \beta\alpha^2 & \beta\alpha^3 & \alpha^4 & \beta\alpha^4 & \\
 \times (\;\cdot\;)^{-1} & \\
\hline
e & \beta & \alpha & \alpha^2 & \beta\alpha^2 & \beta\alpha^3 & \alpha^4 & \beta\alpha^4 & \\
\beta & e & \beta\alpha^4 & \beta\alpha^3 & \alpha^3 & \alpha^2 & \beta\alpha & \alpha & \\
\alpha & \beta\alpha^4 & e & \alpha & \beta\alpha & \beta\alpha^2 & \alpha^3 & \beta\alpha^3 & \\
\beta\alpha & \alpha & \beta & \beta\alpha^4 & \alpha^4 & \alpha^3 & \beta\alpha^2 & \alpha^2 & \\
\alpha^2 & \beta\alpha^3 & \alpha^4 & e & \beta & \beta\alpha & \alpha^2 & \beta\alpha^2 & \\
\beta\alpha^2 & \alpha^2 & \beta\alpha & \beta & e & \alpha^4 & \beta\alpha^3 & \alpha^3 & \\
\alpha^3 & \beta\alpha^2 & \alpha^3 & \alpha^4 & \beta\alpha^4 & \beta & \alpha & \beta\alpha & \\
\end{array}
$$

This is once again an **OEDF**, with three occurences of each of the non zero elements of $D_5$ occuring in each of the tables. 



