# Number Theory Meets Group Theory
I am learning group theory at a math club at work. We recently studied some properties of finite cyclic groups and I realized something. Given an arbitrary prime $p$, you can always find $A, B, x, y, k \geq 2$ such that this statement holds:
$$kp = A^x - B^y$$

Notably, this works for coprime $p$, $A$, and $B$. (This expression is trivial if you allow them to have a common factor.)

I've been too busy/lazy to write down the proof but I am pretty sure it is solid. It goes like this:
1. If $A^x$ and $B^y$ could be made congruent $mod \space p$, then those modulo parts would cancel out and all that would be left are multiples of $p$.
2. If $p$ is divided out of both the right-hand terms, you create two instances of multiplicative groups $modulo \space p$. These groups can be imagined as starting at $A \space mod \space p$ and $B \space mod \space p$, and then being "advanced" through exponentiation to where they ultimately land — $A^x \space mod \space p$ and $B^y \space mod \space p$, respectively.

So all one has to do is find two exponentiated natural numbers that are congruent $modulo \space p$ and then "rewind" them to the desired bases ($A$ and $B$). I've had a hard time coming up with a general algorithm to _find_ $A$, $B$, $x$, and $y$; my brain wants to jump out of group theory into graph theory, because this feels like a reachability question. I'll explore that at a future time. But I am pretty confident that such values exist for all primes.

I also want to know the properties of $k$. Will $k$ always be prime? Never be prime? Coprime with $p$? Could $k$ be a power of $p$?

## Example
I did think of a simple example to illustrate this.
- $p = 5$
- $A = 3$, $x = 3n$ for $n \geq 1$
- $B = 2$, $y = n$ (for the same $n$)

Put together, this looks like:
$$5k = 3^{3n} - 2^n$$

This example works because $3$ and $2$ are generators of the multiplicative group $modulo \space 5$; this means that, $modulo \space 5$, they can be faithfully represented as powers of each other:
- $3^3 \space mod \space 5 = 2 \space mod \space 5$
- $2^3 \space mod \space 5 = 3 \space mod \space 5$

So I am guaranteed that, as long as their exponents increase in lockstep, they will always be congruent. That is why $x = 3n$: every third power of $A = 3$ is congruent with a power of 2. (That's why $B = 2$ has exponent $y = n$; I picked this example to make one of the terms nice.)

This example reveals some very intriguing properties of $k$; for example, in this case $k \in 5\mathbb{Z}^+$. Does that hold for other $p$? There are other more intriguing patterns as $n$ increases but I will write those up another time.