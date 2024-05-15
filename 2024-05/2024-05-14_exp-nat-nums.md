# Exponentiated Natural Numbers $mod \space 5$
Yesterday, I wrote [some observations](./2024-05-13_number-theory.md) about exponentiated natural numbers and modular arithmetic. I can't stop thinking about it, so I am going to elaborate on that subject.

## General Form Of Congruent Numbers
In yesterday's post, I observed that one could always get multiples of 5 using the function:
$$f[n] = 3^{3n} - 2^n$$

This worked because of two facts:
1. $3^3 \space mod \space 5 \equiv 2 \space mod \space 5$
2. $2^3 \space mod \space 5 \equiv 3 \space mod \space 5$

I picked two and three because I knew them both to be generators of the multiplicative group $modulo \space 5$, which means I could ensure they were congruent if I got their exponents just right.

I picked these particular values because of my knowledge of these numbers but this expression can be generalized a little:
$$kp = a^{n \times log_a(b \space mod \space p)} - b^n, \forall n \in \mathbb{Z}^+$$

The expression $log_a(b \space mod \space p)$ is [discrete logarithm](https://math.mit.edu/classes/18.783/2022/LectureNotes9.pdf) — at least, I thought it was until I encountered that 18-page document. Apparently there is more to the discrete log than I realized.

## Simplifying The General Form
One property of logarithms is that $a^{log_a(b)} = b$. That means I can reduce the general form to:
$$kp = b^n \space mod \space p - b^n$$

That might seem trivial, but $b^n \space mod \space p$ refers to a family of values — all natural numbers that are congruent with $b \space mod \space n$. Again, not a very fascinating assertion because that's basically how I established the theorem in yesterday's post.

But there is more to that first term. For example, $2 \space mod \space p \equiv 2 \space mod \space p$. (Duh.) But also, $2^{|2 \space mod \space p|} \equiv 2 \space mod \space p$. (The vertical bars here are _order_, as in the order of an element of a group.)

Suppose $p = 5$. Because $|2 \space mod \space 5| = 4$, I know the following are all true without any computation:
- $2^5 \space mod \space 5 \equiv 2 \space mod \space 5$
- $2^{32} \space mod \space 5 \equiv 2^8 \space mod \space 5$
- Generally, for any $x \space mod \space |2 \space mod \space 5| \equiv y \space mod \space |2 \space mod \space 5|$, $2^x \space mod \space 5 \equiv 2^y \space mod \space 5$

And there is nothing special about 5 here — kind of. Look at $2^5 \space mod \space 5 \equiv 2 \space mod \space 5$ again. That is saying that $2^5 - 2$ is a multiple of five. And it is: $5 | 30$.

What else divides 30? I won't enumerate all the factors but 6 does. What is $|2 \space mod \space 6|$? I don't think that question is meaningful because $2^n \not\equiv 1 \space mod \space 6$  — there is no value of $n$ that ever allows $2^n$ to equal $1 \space mod \space 6$.

But let's do 3; it's coprime with 2 and so might have a well-defined order. Sure enough, $|2 \space mod \space 3| = 2$. That means $2^5 \space mod \space 3 \equiv 2 \space mod \space 3$.

I am too tired to elaborate on that more. Maybe tomorrow I'll share more observations.

... except I need to explain that "kind of" comment. As stated in a preceding paragraph, there are other $p$ values for which $2^5 \space mod \space p \equiv 2 \space mod \space p$. But this only works for $p$ where $|2 \space mod \space p|$ divides 4. Take, for example, $p = 7$: $|2 \space mod \space 7| = 3$. Sure enough, $2^5 = 32 = 4 \space mod \space 7 \not\equiv 2 \space mod \space 7$.