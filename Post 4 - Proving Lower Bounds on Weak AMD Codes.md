# Proving Lower Bounds on AMD Codes

Right. Proving lower bounds on... what exactly... to do with AMD codes? Well, remember that our ultimate goal is for the adversary's best strategy to succeed in being undetected with the *lowest probability possible*. Therefore it makes sense to explore  what theoretical threshholds we can say are impossible to get below.

NB: A lower bound doesn't mean that probabilities higher than it are possible and probabilities lower are impossible. It just says that lower probabilities are impossible and... we don't know about the higher ones. So if we say that the probability the best strategy has a lower bound of $p$ - that means the probability of the best strategy is *at least* $p$.

We need all our symbols from the last time we talked about AMD codes, so let's keep a quick reference handy:

| Term              | Called                                 | Means                                                        |
| ----------------- | -------------------------------------- | ------------------------------------------------------------ |
| $\mathcal S$      | Source space                           | The set of all possible source messages.                     |
| $m$               | Number of sources                      | The size of the source space, $|\mathcal S|$.                |
| $\mathcal G$      | (Encoded) message space                | The set (group) of all possible tags.                        |
| $n$               | Number of tags                         | The size of the message space, $|\mathcal G|$.               |
| $A(s)$            | Valid encodings of $s$                 | The subset of $\mathcal G$ which are valid encodings of $s \in \mathcal S$ |
| $a_s$             | Number of valid encodings of $s$       | The size of the valid encoding set of $s$, $|A(s)|$.         |
| $\mathcal G_0$    | All valid encodings.                   | The union $\bigcup\limits_{s \in \mathcal S} A(s)$ of all the valid encodings. |
| $a$               | The total number of valid encodings.   | The size of the union of all the valid encodings, $\sum \limits_{s \in \mathcal S} a_s = |\mathcal G_0 |$ |
| $\mathcal A$      | The set of all valid encoding subsets. | The set $\{ A(s) : s \in \mathcal S \}$.                     |
| $E$               | The encoding function.                 | The function $E : \mathcal S \to \mathcal G$ that maps each $s$ in $\mathcal S$ to some $g$ in the corresponding $A(s)$. |
| $\Delta$          | Adversary's value.                     | The value in $\mathcal G \backslash \{ 0 \}$ chosen according to the adversary's strategy. |
| $\epsilon_\sigma$ | Success probability.                   | The probability that the adversary wins the AMD code game using the strategy $\sigma$. |
| $\hat \epsilon$   | Maximum success probability.           | The probability of the *best* possible strategy succeeding $\hat \epsilon = \max \limits_\sigma\{\epsilon_\sigma\}$. |

## A first lower bound

Okay... ready for this! 
$$
\hat \epsilon \geq {a(m - 1)\over m(n-1)}
$$
Okay, why? Well the best strategy has got to be at least as good as the strategy of choosing $\Delta$ *randomly* (we'll call this strategy `rand`). So let's work out what the probability for that turns out to be.

For any given tag $g$ in a valid encoding set $A(s)$, there are $n -1$ values in total that $g + \Delta$ could be (anything except $g$), and $(a - a_s)$ values where the adversary would win. Because $\Delta$ is chosen randomly, the probability the adversary wins is therefore $(a - a_s)/(n -1)$.

Now we don't know what the probability of each $g$ appearing might be: it depends on the encoding function. We'll call this $\textbf{Pr}[E(s) = g]$ So for a given source $s$, the sucess probability is:
$$
\sum \limits_{g \in A(s)} \textbf{Pr}[E(s) = g] \times { a - a_s \over n - 1}
$$
And so the overall probability is:
$$
\epsilon_{\text{rand}} = \sum \limits_s \textbf {Pr}[s]\left(\sum \limits_{g \in A(s)} \textbf{Pr}[E(s) = g] \times { a - a_s \over n - 1} \right)
$$
We can tidy this up by moving the $(a - a_s)/(n -1)$ outside of the summation (since it doesn't depend on $g$), and then collapsing the sum $\sum_{g \in A(s)} \textbf{Pr}[E(s) = g]$ into just $1$ (as it has to be one of them!) This gives us:
$$
= \sum \limits_s \left( \textbf {Pr}[s] \times { a - a_s \over n - 1} \right)
$$
What the original source actually is might depend on a lot of things, often purely a whim of the sender; so although it is an approximation, we'll assume that all the source are equiprobable and randomly chosen. That simplifies things further.

There's $m$ possible sources, so $\textbf{Pr[s]}$ is $1/m$. We then have:
$$
=& \sum \limits_s \left( {1\over m} \times { a - a_s \over n - 1} \right) \\
= &\sum \limits_s {a - a_s\over m(n - 1)} \\
= &\sum \limits_s \left( {a \over m(n - 1)} - {a_s \over m(n-1)} \right)\\
= &\sum \limits_s {a \over m(n - 1)} - \sum \limits_s {a_s \over m(n-1)} \\
= & m \times {a \over m(n - 1)} - \sum \limits_s {a_s \over m(n-1)} \\
= & {a \over n - 1} - \sum \limits_s {a_s \over m(n-1)}
$$
This final summation turns out to be easy: remember that $a$ is just defined as $\sum_s a_s$. So we end up with:
$$
=& {a \over n - 1} - {a \over m(n-1)} \\
= & {a\over n - 1}\left(1 - {1\over m}\right) \\
= & {a\over n - 1}\left(m-1\over m\right) \\
= & {a(m-1)\over m(n- 1)}
$$
There it is (might need to scroll up to remember that's the expression we were looking for)! Now we can say that since the random adversarial strategy will always succeed with probability $a(m-1)/m(n-1)$ then the *best* strategy can always do at least this well.
$$
\hat \epsilon \geq {a(m - 1)\over m(n-1)}
$$
Mwaha, proved.  ☑️

## k-uniformity

It may be the case that all of the $A(s)$ sets are the same size, say $k$. In that case we'll call the code **k-uniform**. In this case, $a$ would just be $km$, and so our lower bound would be:
$$
\hat \epsilon \geq {k(m - 1)\over n-1}
$$


## R-Optimal AMD Codes

If we've somehow defined an AMD code so that the best strategy can't do any better than random, i.e.
$$
\hat \epsilon = {a(m - 1)\over m(n-1)}
$$
Then we'll call this an **R-Optimal** AMD code. Easy to remember why: `rand` is an optiminal strategy!

## Another lower bound 

Hold on... think about something we said way back in a previous post. For an encoding to have a chance of working, we have to have at least 1 valid tag for each source, and the sets of valid tags for each source can't overlap. 

So the total number of valid tags must be greater than the total number of sources! $a \geq m$. Hence ${a \over m} \geq 1$. If our $\hat \epsilon$ is bigger than $m-1 / n - 1$ multiplied by a number greater than 1, it's certainly got to be bigger than that number multiplied by just 1. So another lower bound can just be:
$$
\hat \epsilon \geq {m - 1\over n-1}
$$
We need a deterministic code in order to meet this lower bound; but we can prove a different lower bound using a different adverserial strategy to define a different class of AMD codes

## G-Optimal AMD Codes

$$
\hat \epsilon \geq {1\over a}
$$

Oho that's a cool lower bound. Is it a better lower bound than our other one? *We don't know* - we don't know the size of $1/a$ relative to $m - 1/n - 1$. It's just a different lower bound based on a different strategy.

Okay, so this time we won't use a random strategy, but still a very straightforward one. We'll call it `guess`. The encoding function and its probabilities are assumed to be public, so let's imagine our adversary puts all their eggs in one basket and simply banks on the encoding $g$ that occurs being the one that they know to have the highest probability. We'll call that particular encoding  $\hat g$.

What's the lowest the probability of getting $\hat g$ could be? Well if all $a$ of the valid $g$s had equal probability, they would each have a probability of $1\over a$. We could make any of them smaller than that, but in order to make one smaller, we'd have to make another one bigger (since the always have to add up to one). Hence the smallest that the one with the largest probability can be is $1\over a$.

Basically, the adversary will just pick a $\Delta$ that will work for $\hat g$ (i.e. take another $g \neq \hat g$ and choose $\Delta = g - \hat g$. 

So if the encoding function produces $\hat g$, the adversary is in luck and wins with probability 1. Hence the overall probability that they succeed is just $\textbf{Pr}[E(s) = \hat g] \geq {1\over a}$.

We can then say:
$$
\hat \epsilon \geq \epsilon_\text{guess} \geq {1\over a}
$$
Proved again! ☑️

Once more, if we have an AMD code that actually means that $1/a$ is the best an adversary can hope for, then we'll call it **G-Optimal** (`guess` is an optimal strategy).

## Combining R and G Optimality

We now have two different bounds. We might as well multiply them together to say that:
$$
\hat \epsilon^2 \geq {m - 1 \over m(n-1)}
$$
(note the squared).

If a code meets this bound with equality... as in if we can somehow say that:
$$
\hat \epsilon^2 = {m - 1 \over m(n-1)}
$$
Then we'll declare that it is simultaenously R-Optimal and G-Optimal.





...



Excellent. We have proved some lower bounds for weak AMD codes!

It'd be nice if we actually knew of any encodings that are these things (R-Optimal etc.) Maybe we'll look into that next time... Till then!