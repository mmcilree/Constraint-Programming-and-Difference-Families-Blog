# Post 11 - Proof Attempt for Homomorphic SEDF Property

As seen in previous examples, it does appear that the images of SEDFs under homorphism form what I have been calling an "OEDFs" overlapping (strong) external difference family. That is, the conditions on the external differences appear to still hold under homomorphism, providing the requirement that sets be disjoint is ignored and a number of zero differences is allowed. 

## 11.1 Condition for OEDF property

For some group $G$ of order $n$, let the sets $A_1, ..., A_m \subseteq G$ form an $(n, m, k, \lambda)$-SEDF. Let $\phi$ be a homomorphism from $G$. By the first isomorphism theorem $G/\ker\phi \simeq \text{im} \phi$. Denote $H = \ker \phi$ and note that this is a normal subgroup. 

For  $i \neq j$ each element of $G$ occurs $\lambda$ times as an external difference between the sets $A_i$ and $A_j$. And we know that each element of $K$ is mapped to by exactly $|H|$ elements. So for a given non zero element of $K$ there are exactly $\lambda \cdot |H|$ pairs $x \in A_i$, $y \in A_j$ such that $\phi(x)(\phi(y))^{-1}$ equals that element. 

If we define the image of the SEDF as being the multisets $A_1', A_2', \dots, A_m'$ by having each $A_1'$ contain all the images of the elements in $A_1$ (including duplicates), then we have an overlapping-OEDF like structure in $K$ where each non-zero element occurs as exactly $\lambda \cdot |H|$ external differences (counting the duplicates) between any two multisets. 

If however we define the image of the SEDF as being normal sets and eliminating duplicate elements, it is not clear that constancy of the external difference occurences wouldn't be violated. 

We can formalise this as follows:

An image (as a family of normal sets) of an SEDF has an OEDF structure if and only if:

for any $c \in K$ and $i \neq j$, there are a constant number of quadruples $(x_1, x_2, y_1, y_2)$ where $x_1, x_2 \in A_i$, where either $x_1 \neq x_2,$ or $y_1 \neq y_2$ (or both) and $ \phi(x_1) = \phi(x_2)$ and $\phi(x_1y_1^{-1}) = \phi(x_2y_2^{-1}) = c$.

This captures the idea of there being a constant number of external differences in the image that are ignored due to being duplicates.

### Possible Proof Direction

It may be the case that every strong edf image satisfies this property. Indeed all of the examples in Post 10 appear to. Therefore we might attempt to prove that the condition always holds, and thereby show that every SEDF image is an OEDF (unlike for EDFs).

To simply notation, we may argue in terms of cosets of the normal subgroup $H$, as $\phi(x_1) = \phi(x_2) \iff x_1$ and $x_2$ are in the same coset $Hx_1$.  

The condition may then be rewritten as:

for any coset $H\alpha$ and $i \neq j$  there are a constant number of quadruples $(x_1, x_2, y_1, y_2)$ where $x_1, x_2 \in A_i$, where either $x_1 \neq x_2,$ or $y_1 \neq y_2$ (or both), $x_1$ and $x_2$ are in the same coset, and $x_1y_1^{-1}, x_2y_2^{-1} \in H\alpha$.

One possible idea for proving this is to show that each distinct quadruple for a coset $H\alpha$ implies the existence of such a distinct quadruple for any given different coset $H\beta$. This would mean that the number of quadruples for $H\alpha$ is less than or equal to the number of quadruples for any given $H\beta$, and since the reverse reasoning could be applied to $H\beta$, we would conclude that they are the same. 

It's not clear how to draw such an implication however... and it's quite possible that there are a counterexample. The largest example checked has size 50, and only one interesting homomorphism. Larger examples may yield better counterexamples. 

