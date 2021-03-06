# Constructing an External Difference Family

We haven't actually seen any concrete examples of external different families. Let's use a construction theorem to try to find one.

## The Theorem

One way to create external difference families has been discovered independently by various people ([Tonchev 2003](https://pages.mtu.edu/~tonchev/dssn.pdf), [Huang 2006](https://link.springer.com/article/10.1007%2Fs10623-006-0005-7)). We'll try to understand how it works (but maybe not *why*, just now).

Suppose $q = 2ul + 1$  is a power of a prime number, where $u$ and $l$ are odd. We can construct a $(q, u, l, (q - 2l - 1)/4)$-EDF in the group (field in fact) $\mathbb F_q$ as follows:

1. Find a [primitive](https://en.wikipedia.org/wiki/Primitive_element_(finite_field)) element of $\mathbb F_q$, call it $\alpha$. 
2. Take the subgroup $C$ of $\mathbb F_q^*$ (that is, of the non-zero element of $\mathbb F_q$) that has order $u$ and index $2l$. We know that this exists as $\mathbb F_q^*$ is a group with $2ul$ elements, so it has a subgroup of order $u$.
3. Take the $l$ cosets $\alpha^{2i}C$ for $(0 \leq i \leq l-1)$ - this is the EDF!

...pretty neat that that works. No clue why right now 😅

Let's try find an example then. 

## The Example

We'll start by find a $q$, $31 = 2*3*5 + 1$ is one that works. 31 is prime and so $\mathbb F_q \cong \mathbb Z_{31}$ with multiplication and addition mod 31. 

Now, $3$ is a primitive element. This isn't exactly easy to see straight off, but a bit of [code](https://stackoverflow.com/questions/40190849/efficient-finding-primitive-roots-modulo-n-using-python) stolen from StackOverflow can brute force all the primitive elements as being.
$$
\{3, 11, 12, 13, 17, 21, 22, 24\}
$$
We can check this by noting:
$$
3^1=3 &3^2=9 &3^3=27 &3^4=19 &3^5=26\\3^6=16 &3^7=17 &3^8=20 &3^9=29 &3^{10}=25\\3^{11}=13 &3^{12}=8 &3^{13}=24 &3^{14}=10 &3^{15}=30\\3^{16}=28 &3^{17}=22 &3^{18}=4 &3^{19}=12 &3^{20}=5\\3^{21}=15 &3^{22}=14 &3^{23}=11 &3^{24}=2 &3^{25}=6\\3^{26}=18 &3^{27}=23 &3^{28}=7 &3^{29}=21 &3^{30}=1
$$
That's all 30 non-zero elements!

Next we need to find the subgroup of order $u$ = 3 - equivalent to finding an element of order 3. $5$ should do the job as $5^3 = 125 = 1 \mod 31$.

The subgroup generated by $5$ is $C = \{1, 5, 25\}$.

Now let's find some cosets! We use even powers of 3 from 0 up to $2*(5 - 1) = 8$
$$
3^0C = & \{1, 5, 25\} \\
3^2C = & \{9, 14, 8\} \\
3^4C = & \{19, 2, 10\} \\
3^6C = & \{16, 18, 28\} \\
3^8C = &\{20, 7, 4\}\\
$$
Now, by the reckoning of Huang and Tonchev, these 5 sets should make up an external difference family in  $\mathbb Z_{31}$. Let's check that ourselves. 

We need to verify that the difference between elements of the sets make up all the elements of $\mathbb Z _{31}$ the same number of times. According to the theory, this number should be $(q - 2l - 1)/4 = (31 - 10 - 1)/4 = 5$. Okay deep breath...
$$
& 1 - 9 = 23 & 1 - 14 = 18 & 1 - 8 = 24 & 5 - 9 = 27 & 5 - 14 = 22 & 5 - 8 = 28\\
 & 25 - 9 = 16 & 25 - 14 = 11 & 25 - 8 = 17 & 1 - 27 = 5 & 1 - 2 = 30 & 1 - 10 = 22\\
 & 5 - 27 = 9 & 5 - 2 = 3 & 5 - 10 = 26 & 25 - 27 = 29 & 25 - 2 = 23 & 25 - 10 = 15\\
 & 1 - 16 = 16 & 1 - 18 = 14 & 1 - 28 = 4 & 5 - 16 = 20 & 5 - 18 = 18 & 5 - 28 = 8\\
 & 25 - 16 = 9 & 25 - 18 = 7 & 25 - 28 = 28 & 1 - 20 = 12 & 1 - 7 = 25 & 1 - 4 = 28\\
 & 5 - 20 = 16 & 5 - 7 = 29 & 5 - 4 = 1 & 25 - 20 = 5 & 25 - 7 = 18 & 25 - 4 = 21\\
 & 9 - 1 = 8 & 9 - 5 = 4 & 9 - 25 = 15 & 14 - 1 = 13 & 14 - 5 = 9 & 14 - 25 = 20\\
 & 8 - 1 = 7 & 8 - 5 = 3 & 8 - 25 = 14 & 9 - 27 = 13 & 9 - 2 = 7 & 9 - 10 = 30\\
 & 14 - 27 = 18 & 14 - 2 = 12 & 14 - 10 = 4 & 8 - 27 = 12 & 8 - 2 = 6 & 8 - 10 = 29\\
 & 9 - 16 = 24 & 9 - 18 = 22 & 9 - 28 = 12 & 14 - 16 = 29 & 14 - 18 = 27 & 14 - 28 = 17\\
 & 8 - 16 = 23 & 8 - 18 = 21 & 8 - 28 = 11 & 9 - 20 = 20 & 9 - 7 = 2 & 9 - 4 = 5\\
 & 14 - 20 = 25 & 14 - 7 = 7 & 14 - 4 = 10 & 8 - 20 = 19 & 8 - 7 = 1 & 8 - 4 = 4\\
 & 27 - 1 = 26 & 27 - 5 = 22 & 27 - 25 = 2 & 2 - 1 = 1 & 2 - 5 = 28 & 2 - 25 = 8\\
 & 10 - 1 = 9 & 10 - 5 = 5 & 10 - 25 = 16 & 27 - 9 = 18 & 27 - 14 = 13 & 27 - 8 = 19\\
 & 2 - 9 = 24 & 2 - 14 = 19 & 2 - 8 = 25 & 10 - 9 = 1 & 10 - 14 = 27 & 10 - 8 = 2\\
 & 27 - 16 = 11 & 27 - 18 = 9 & 27 - 28 = 30 & 2 - 16 = 17 & 2 - 18 = 15 & 2 - 28 = 5\\
 & 10 - 16 = 25 & 10 - 18 = 23 & 10 - 28 = 13 & 27 - 20 = 7 & 27 - 7 = 20 & 27 - 4 = 23\\
 & 2 - 20 = 13 & 2 - 7 = 26 & 2 - 4 = 29 & 10 - 20 = 21 & 10 - 7 = 3 & 10 - 4 = 6\\
 & 16 - 1 = 15 & 16 - 5 = 11 & 16 - 25 = 22 & 18 - 1 = 17 & 18 - 5 = 13 & 18 - 25 = 24\\
 & 28 - 1 = 27 & 28 - 5 = 23 & 28 - 25 = 3 & 16 - 9 = 7 & 16 - 14 = 2 & 16 - 8 = 8\\
 & 18 - 9 = 9 & 18 - 14 = 4 & 18 - 8 = 10 & 28 - 9 = 19 & 28 - 14 = 14 & 28 - 8 = 20\\
 & 16 - 27 = 20 & 16 - 2 = 14 & 16 - 10 = 6 & 18 - 27 = 22 & 18 - 2 = 16 & 18 - 10 = 8\\
 & 28 - 27 = 1 & 28 - 2 = 26 & 28 - 10 = 18 & 16 - 20 = 27 & 16 - 7 = 9 & 16 - 4 = 12\\
 & 18 - 20 = 29 & 18 - 7 = 11 & 18 - 4 = 14 & 28 - 20 = 8 & 28 - 7 = 21 & 28 - 4 = 24\\
 & 20 - 1 = 19 & 20 - 5 = 15 & 20 - 25 = 26 & 7 - 1 = 6 & 7 - 5 = 2 & 7 - 25 = 13\\
 & 4 - 1 = 3 & 4 - 5 = 30 & 4 - 25 = 10 & 20 - 9 = 11 & 20 - 14 = 6 & 20 - 8 = 12\\
 & 7 - 9 = 29 & 7 - 14 = 24 & 7 - 8 = 30 & 4 - 9 = 26 & 4 - 14 = 21 & 4 - 8 = 27\\
 & 20 - 27 = 24 & 20 - 2 = 18 & 20 - 10 = 10 & 7 - 27 = 11 & 7 - 2 = 5 & 7 - 10 = 28\\
 & 4 - 27 = 8 & 4 - 2 = 2 & 4 - 10 = 25 & 20 - 16 = 4 & 20 - 18 = 2 & 20 - 28 = 23\\
 & 7 - 16 = 22 & 7 - 18 = 20 & 7 - 28 = 10 & 4 - 16 = 19 & 4 - 18 = 17 & 4 - 28 = 7\\
$$
That should be all the external differences... annd we need to check that each difference occurs 5 times ...that should be all the external differences (yes I used Python to generate that). Now all we need to do it count to make sure there are 5 of each. We can sort them by result to see this easily:
$$
& 5 - 4 = 1
& 8 - 7 = 1
& 19 - 18 = 1
& 2 - 1 = 1
& 10 - 9 = 1
& 20 - 19 = 1
\\
& 9 - 7 = 2
& 10 - 8 = 2
& 16 - 14 = 2
& 7 - 5 = 2
& 4 - 2 = 2
& 20 - 18 = 2
\\
& 5 - 2 = 3
& 19 - 16 = 3
& 10 - 7 = 3
& 8 - 5 = 3
& 28 - 25 = 3
& 4 - 1 = 3
\\
& 1 - 28 = 4
& 14 - 10 = 4
& 8 - 4 = 4
& 9 - 5 = 4
& 18 - 14 = 4
& 20 - 16 = 4
\\
& 25 - 20 = 5
& 9 - 4 = 5
& 2 - 28 = 5
& 10 - 5 = 5
& 19 - 14 = 5
& 7 - 2 = 5
\\
& 25 - 19 = 6
& 8 - 2 = 6
& 10 - 4 = 6
& 16 - 10 = 6
& 7 - 1 = 6
& 20 - 14 = 6
\\
& 25 - 18 = 7
& 9 - 2 = 7
& 14 - 7 = 7
& 8 - 1 = 7
& 16 - 9 = 7
& 4 - 28 = 7
\\
& 5 - 28 = 8
& 28 - 20 = 8
& 9 - 1 = 8
& 2 - 25 = 8
& 16 - 8 = 8
& 18 - 10 = 8
\\
& 25 - 16 = 9
& 16 - 7 = 9
& 14 - 5 = 9
& 10 - 1 = 9
& 18 - 9 = 9
& 28 - 19 = 9
\\
& 14 - 4 = 10
& 19 - 9 = 10
& 18 - 8 = 10
& 4 - 25 = 10
& 20 - 10 = 10
& 7 - 28 = 10
\\
& 25 - 14 = 11
& 8 - 28 = 11
& 18 - 7 = 11
& 19 - 8 = 11
& 16 - 5 = 11
& 20 - 9 = 11
\\
& 1 - 20 = 12
& 14 - 2 = 12
& 9 - 28 = 12
& 19 - 7 = 12
& 16 - 4 = 12
& 20 - 8 = 12
\\
& 1 - 19 = 13
& 10 - 28 = 13
& 2 - 20 = 13
& 14 - 1 = 13
& 18 - 5 = 13
& 7 - 25 = 13
\\
& 1 - 18 = 14
& 18 - 4 = 14
& 8 - 25 = 14
& 19 - 5 = 14
& 28 - 14 = 14
& 16 - 2 = 14
\\
& 25 - 10 = 15
& 2 - 18 = 15
& 19 - 4 = 15
& 9 - 25 = 15
& 16 - 1 = 15
& 20 - 5 = 15
\\
& 25 - 9 = 16
& 1 - 16 = 16
& 5 - 20 = 16
& 10 - 25 = 16
& 18 - 2 = 16
& 4 - 19 = 16
\\
& 25 - 8 = 17
& 5 - 19 = 17
& 14 - 28 = 17
& 2 - 16 = 17
& 18 - 1 = 17
& 4 - 18 = 17
\\
& 1 - 14 = 18
& 5 - 18 = 18
& 25 - 7 = 18
& 19 - 1 = 18
& 28 - 10 = 18
& 20 - 2 = 18
\\
& 8 - 20 = 19
& 2 - 14 = 19
& 28 - 9 = 19
& 20 - 1 = 19
& 7 - 19 = 19
& 4 - 16 = 19
\\
& 5 - 16 = 20
& 8 - 19 = 20
& 9 - 20 = 20
& 14 - 25 = 20
& 28 - 8 = 20
& 7 - 18 = 20
\\
& 25 - 4 = 21
& 9 - 19 = 21
& 8 - 18 = 21
& 10 - 20 = 21
& 28 - 7 = 21
& 4 - 14 = 21
\\
& 5 - 14 = 22
& 1 - 10 = 22
& 9 - 18 = 22
& 19 - 28 = 22
& 16 - 25 = 22
& 7 - 16 = 22
\\
& 1 - 9 = 23
& 25 - 2 = 23
& 8 - 16 = 23
& 10 - 18 = 23
& 28 - 5 = 23
& 20 - 28 = 23
\\
& 1 - 8 = 24
& 9 - 16 = 24
& 28 - 4 = 24
& 2 - 9 = 24
& 18 - 25 = 24
& 7 - 14 = 24
\\
& 1 - 7 = 25
& 14 - 20 = 25
& 10 - 16 = 25
& 19 - 25 = 25
& 2 - 8 = 25
& 4 - 10 = 25
\\
& 5 - 10 = 26
& 14 - 19 = 26
& 2 - 7 = 26
& 28 - 2 = 26
& 20 - 25 = 26
& 4 - 9 = 26
\\
& 5 - 9 = 27
& 14 - 18 = 27
& 16 - 20 = 27
& 10 - 14 = 27
& 28 - 1 = 27
& 4 - 8 = 27
\\
& 5 - 8 = 28
& 25 - 28 = 28
& 1 - 4 = 28
& 2 - 5 = 28
& 16 - 19 = 28
& 7 - 10 = 28
\\
& 5 - 7 = 29
& 8 - 10 = 29
& 14 - 16 = 29
& 2 - 4 = 29
& 18 - 20 = 29
& 7 - 9 = 29
\\
& 1 - 2 = 30
& 9 - 10 = 30
& 19 - 20 = 30
& 18 - 19 = 30
& 4 - 5 = 30
& 7 - 8 = 30
\\
$$

$\{1, 5, 31\}, \{9, 14, 8\},\{27, 2, 10\},\{16, 18, 28\},\{20, 7, 4\}$ does indeed appear to be an external difference family: a $(31, 3, 5, 6)$-EDF - just as the theorem predicted 😊.

...

...um no actually?? 😅 The theorem predicted a $(31, 3, 5, 5)$-EDF. Hmm.

Well either I've done something wrong or there's a slight mistake in the statement of the theorem. If we were told to expect $(q, u, l, (q - \mathbf{2u} - 1)/4)$-EDF rather than a  $(q, u, l, (q - \mathbf{2}l - 1)/4)$-EDF then it would all be fine, so maybe it's just the wrong way around. I will check and confirm next time.

