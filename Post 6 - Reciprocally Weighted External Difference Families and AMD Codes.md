# Reciprically Weighted External Difference Families and AMD Codes

So how can we characterise R-Optimal AMD codes.

We know that the adversary wins if they have some $\delta$ such that $g + \delta$ is an encoding of a different source than one which $g$ could have been for. 

The probability that an adversary succeeds when they pick the group element $\delta$ is:
$$
e_\delta = {1 \over m}\left({1\over k_1}N_1(\delta) + {1\over k_1}N_2(\delta) + \dots + {1\over k_m}N_m(\delta) \right)
$$
(NB: Typing out all these formulas is kind of slow... so I might handwrite some stuff as well.)

Why? Remember what these symbols mean 

| **Symbol**    | **Means**                                                    |
| ------------- | ------------------------------------------------------------ |
| $m$           | Number of sources                                            |
| $N_i(\delta)$ | Number of external differences from the set $A_i$ equal to $\delta$ |
| $k_i$         | The size of the set $A_i$                                    |

A source is picked with probability $1/m$ and then for each source $N_i(\delta)$ of the possible $k_i$ encodings for the source is a win for the attacker.

The best strategy is therefore the max over all possible $\delta$s (non zero group elements).

Now, since we're dealing with R-Optimality, we want to know what the smallest max success probability is when the attacker chooses at random. "Smallest max"? As in, each code has its own max success probability, but what is the smallest this could be in any case?

Well, it's the average of the $e_\delta$ values. The best we can hope for is that all $\delta$ values are just as good/bad as any other. Let's work out the average.

![IMG_6DCD749E2B28-1](/Users/matthewmcilree/Documents/SHProject/SH Project Blog/IMG_6DCD749E2B28-1.jpeg)

The $T$ here is the same as the '$a$' we were using in previous posts.

Okay, finally its time to link EDFs and related structures to AMD codes. We need one final generalisation:

![IMG_DC88BD7C3F03-1](/Users/matthewmcilree/Documents/SHProject/SH Project Blog/IMG_DC88BD7C3F03-1.jpeg)

So basically, the number of occurrences of $\delta$ as an external difference *weighted* by a set of $w$ need to equal a constant (not even necessarily an integer).

This looks very close to the form form for our optimal AMD code! We just need to insist that the weights are 1 over the number of elements in each set.

![IMG_3FA1C9F4C3B5-1](/Users/matthewmcilree/Documents/SHProject/SH Project Blog/IMG_3FA1C9F4C3B5-1.jpeg)

Now the conditions for an R-Optimal AMD code and RWEDF look the same so we can say:

*An AMD code is R-Optimal precisely when it is an RWEDF*.

