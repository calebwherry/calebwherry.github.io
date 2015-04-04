---
layout: post
title: Infinite Sum of Zeros
date: 2010-11-20
status: publish
comments: true
share: true
categories:
- Mathematics
tags: []
image:
  feature: main-banner-2.jpg
---

Given the following statement, what would the "logical" answer be:

$$ 0 + 0 + 0 + 0 + \ldots \; = \; ? $$

Someone without any mathematical knowledge (but knowledge of what the above mathematical symbols mean, of course) will almost without hesitation say 0. But is this correct? Even someone with <i>some</i> mathematical knowledge would jump to this conclusion (like me). I fail to see how this does not equal zero, which one of my professors, Dr. Ben Ntatin, thinks is so...

So here is his "proof" on the matter. Now I am no expert on analysis or algebra so maybe I am missing a fundamentally logical proof or something. So, here we go...

We start off with some statements that we accept as true:

$$
\begin{aligned}
0 & = 0 \\
0 & = 0+0 \\
0 & = 1 - 1
\end{aligned}
$$

And we assume:

$$ 0\;=\;0+0+0+0+\ldots $$

Okay so everything seems fine thus far. But lets start delving a little deeper:

$$
\begin{aligned}
0 & = 0 + 0 + 0 + 0 + \ldots \\
0 & = (1-1) + (1-1) + (1-1) + (1-1) + \ldots
\end{aligned}
$$

This is a legitimate statement given the rules we accepted as true above. All I did was replace each 0 with (1-1). My next step should be familiar to someone with a little mathematical background with the knowledge that real numbers are associative under the binary operator + (and also the fact that - is the same as + with the negative reals). So, we have associativity:

$$ (a+b) + (c+d) + (e+f) = a + (b+c) + (d+e) + f $$

All I did was rearrange the order in which I added the numbers together. This is a perfectly legitimate mathematical statement. But this is where my quarrel starts. Even if you move the parenthesis over one number as I did above, you will always have one number on the end that matches up with the beginning term. We now look at the above rule with Dr. Ntatin's next step:

$$
\begin{aligned}
0 & = 0 + 0 + 0 + 0 + \ldots \\
0 & = (1-1) + (1-1) + (1-1) + (1-1) + \ldots \\
0 & = 1 + (-1+1) + (-1+1) + -1 \ldots \\
0 & = 1 + 0 + 0 + 0 \ldots \\
0 & = 1
\end{aligned}
$$

Thus we have reached a contradiction so our original assumption of:

$$ 0 = 0 + 0 + 0 + 0 + \ldots $$

is wrong. But I don't think that is true. I don't think the algebra is correct above. I am still sticking to the fact that if you shift the associativity in the sum, you will still always have a term on the end that cancels out that first number in the sum. Because each zero is replaced by 2 numbers, 1 and -1, then you will always have an even number of numbers. So, you will always have a matching number to cancel out the first.

Now this is where I will admit that the concept of infinity is not at all intuitive. When studying mathematical analysis, there are things that make sense mathematically in the finite but do not make sense (and in some cases cannot be done) in the infinite. Maybe my reasoning above does not hold up because of this. Maybe my thinking of "grouping" infinitely many groups does not make sense. Maybe my thinking of there being an even number of 1's does not make sense either because it is an infinite sum. I am at a loss...
