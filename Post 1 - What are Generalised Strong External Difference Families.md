# Generalised Strong External Difference Families

I'm about to start studying and finding out about... GSEDFs. 

Maybe I can pronounce it "Gus-eh-dufs"? It's rather a lot of words in a name for single *thing*. One of those fun academic concepts where each new idea gains all the name-words from the thing it's based on, along with another word to distinguish it from it's parent concepts ([it's a bit like Dr. Seuss's tweetle beetles tongue twister](https://www.goodreads.com/quotes/9409559-what-do-you-know-about-tweetle-beetles-well-when-tweetle)).

Let's break it down and then build back up to it.

## Difference Sets

(We're talking about special subsets of [groups](https://en.wikipedia.org/wiki/Group) here.)

Take a group $G$ and a subset $A$. We essentially want to know whether the *differences* between all the elements of $A$ turn out to be the non zero elements of $G$, possibly repeated some number of times.

Formally we say that the [multiset](https://en.wikipedia.org/wiki/multiset)
$$
M = \{x - y :x, y \in A, x \neq y \} = \lambda(G\backslash\{0\})
$$
$\lambda(G\backslash\{0\})$ just means: $\lambda$ occurences of the non-zero elements of G. The common theme through all of these seems to be obtaining this multiset somehow. 

With this $\lambda$ along with the size of the group, say $n$, and the size of the subset $A$, say $k$, we can "name" any difference set we come across. We'll call it a $(n, k, \lambda)$*-difference set*. 

Cute 😊

## Difference Families 

Extending that concept, let's now say we have a few subsets of $G$: $A_1, \dots, A_m$.

Rather than having to have each of the $A$'s differences make up a $\lambda(G\backslash\{0\})$ multiset, they can work together in their union to do the job. 

So:
$$
M = \bigcup_i\{x - y: x, y \in A_i, x \neq y\} = \lambda(G\backslash\{0\})
$$
We can then refer to this collection of $A$s as a $(n, k, \lambda)$*-difference family*. 

## External Difference Families

Difference sets and families have been around for a while. *External* difference families (see, adding words fast 😀) are a newer concept. 

Basically, getting our $\lambda(G\backslash\{0\})$ by taking the *internal* differences and then the union is just tooo eeaasssy. We want the *external* differences to make it up, i.e.  taking the differences between elements in *different* subsets in the family collection.

Note also that with groups we're happy with either [additive notation](https://proofwiki.org/wiki/Definition:Additive_Notation) $a - b$  or [multiplicative notation](https://proofwiki.org/wiki/Definition:Multiplicative_Notation) $ab^{-1}$. But multiplicative notation is more general (not requiring commutativity and all that), so let's switch to that from now. We'll therefore talk about $\lambda(G\backslash\{e\})$, where $e$ is the identity element.

This time then:
$$
M = \{xy^{-1} : x \in A_i, y \in A_j, i \neq j\} = \lambda(G\backslash\{e\})
$$
For some reason, (guess I might find out later), it's also useful to know how many $A$s we have here, so we refer to the collection as a $(n, m, k, \lambda)$*-external difference family*. Already it seems reasonable to shorten this to EDF.

## Strong External Difference Families

Okay there's two ways we can go from here. First the bog-standard *strong* external difference families. We place an additional restriction here, that even if we force the first the element of the difference to be in one of the $A$s in particular, we still get a our $\lambda(G\backslash\{e\}$, every time, for any of the $A$s. That's pretty strong 💪.

So for every $i$ from 1 up to $m$.
$$
M_i = \{xy^{-1} : x \in A_i, y \in \cup_{j \neq i}A_j\} = \lambda(G\backslash\{e\})
$$
We'll call that a  $(n, m, k, \lambda)$*-strong external difference family*

## Generalised Strong External Difference Families

Last one for now! Let's now go for a different way of generalising EDFs. Rather than saying each $A$ has to be the same size, and result in the same $\lambda$ occurences of the non-zero elements of $G$, we can have each $A_i$ it's own size, $k_i$, and each multiset of external differences result in a different $\lambda_i(G\backslash\{e\})$. 

We would say, for every $i$ from 1 up to $m$.
$$
M_i = \{xy^{-1} : x \in A_i, y \in \cup_{j \neq i}A_j\} = \lambda_i(G\backslash\{e\})
$$
Not much difference there, just the $\lambda_i$s. The name on the other hand has to get biiiggg. Gotta list all the difference sizes of the $A$s as well as all the different $\lambda$s.

We'll call that a  $(n, m; k_1, \dots k_m; \lambda_1, \dots, \lambda_m)$*-generalised strong external difference family*.

It's cool to note that a $(n, m; k, \dots, k; \lambda, \dots, \lambda)$-GSEDF is the same as a $(n, m, k, \lambda)$-SEDF.

...

Anyway, there we are. GSEDFs! Got there in the end! More to come later.

