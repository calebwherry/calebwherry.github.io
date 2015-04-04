---
layout: post
title: 'Math 101: Simple Flawed Proofs'
date: 2011-09-23
status: publish
comments: true
share: true
categories:
- Mathematics
tags: []
image:
  feature: main-banner-2.jpg
---

I wanted to post on types of proofs that I find highly interesting: ones that are completely and utterly wrong based on very simple mathematics. With these types of proofs, we can seemingly "prove" that 1=2 or 10 = 1,396. I have always found it interesting that most people cannot spot the mistakes in these proofs.  I'll give a simple example (there are many others, but I like this one most) and then go through some of the reasons why I think most people do not immediately understand the flaws.

## The "Proof"
Consider these simple statements:

Let \(a \in \mathbb{R}\)

Assume a = b

Isolating the equation, multiply both sides by a:

$$ a^2 = ab $$

Subtract \( b^2 \) from both sides:

$$ a^2 - b^2 = ab - b^2 $$

Now let us factor each side:
$$ (a+b)(a-b)=b(a-b) $$

We can now divide each side by \((a-b)\):

$$ \frac{(a+b)(a-b)}{(a-b)}=\frac{b(a-b)}{(a-b)} $$

This reduces to:

$$ a+b = b $$

Now since a and b are both equal (from the first statement), let us set them to 1 which produces:

$$
\begin{aligned}
1+1 & = 1 \\
2 & = 1 \; \; \mathbb{QED} \\
\end{aligned}
$$

Can you spot the error? I'll give you a second...

To most people, their immediate answer/reaction is that mathematics cannot be trusted and the above "proves" that Mathematics is sometimes wrong and untrustworthy (Mathematics is the problem, basically)... This could not be further from the truth! But why do they think this way? I believe it is a fundamental problem in the way that Mathematics is taught at a young age in the United States (I cannot vouch for other students around the world, this is just something I have noticed here in the states). The American education system is not a very good one when it comes to Mathematics (among other things). Case in point, more than half of the Mathematics I learned in college is learned by international students in their high school years! But I digress, this is not the main issue here. I do not necessarily care <i>for this post</i> that others learn more than we do (that is another issue), just that we learn things at a fundamental level wrong! It would be fine if the Mathematics that we are currently teaching is taught correctly, but it is not. This causes many problems down the road throughout people's lives, such as balancing their checkbooks and keeping up with their finances. Most people are forced to learn Mathematics in the most boring fashion when they are young and it does nothing for them. They are not taught the beauty of Mathematics.

This is a tragic mistake in our education system. Mathematics is vital to being able to keep a structured and stable life, even if it just means that you can sit down and plan out your finances so your family can eat! These types of things are so important but the fundamentals of them are taught as if they are chores instead of activities. If Mathematics is mentioned to the layperson, they usually get a disgusted look on their face and say something to the effect of "Oh I never use math, who wants to use that? That's for the smart people, it's useless to me!" This cannot be further from how we should view Mathematics.

This viewpoint stems from how we teach Mathematics. Children/young adults are pushed to learn and memorize formulas without understanding how or why any of it works. Most students have a deep hatred for Mathematics starting at a young age. This is most unfortunate because Mathematics is a beautiful and rich subject that should be treated as such when being taught. Unfortunately, this is not so (I am not here to describe how we can reform the system, that shall be another post at some point). Even something as simple as the Pythagorean Theorem has a beautiful representation if presented right. It is not such some symbols you memorize for a test! However, Mathematics teachers do not teach this way... But, as I said, that is for another post! Let us look at that proof...

What was the flaw? Let us examine the proof and oust the fundamental problem that lies within!

First off, when dealing with Mathematics, you have to have a very good memory sometimes. You cannot skip over even the smallest detail. I believe this is why most people see Mathematics as laborious and do not want to put forth the added brain power to fully understand what they are seeing/learning. The whole problem with this "proof" would be mitigated if people really understood the very first line and the implications of it: \( a=b \). What does this imply? Many things actually. The most basic is that what ever a is, b is also. Or, some might see it as whatever b is, a is as well (it does not matter which way you look at it in this case). But when we say this, there are direct implications like if a is even, then b is even, and if we multiply a and b then the result is even. We can pull out many properties like this depending on what the properties of the values we give a (and thus b) are.

So now that we are thinking down the path of implications of knowing properties of numbers, what would you say about subtraction? What can we imply about subtracting a and b after we make them equal? Well, the first thing that you should think of is "0"! And that is correct!

But we are still not done. We know that this should now yield a 0 value if we subtract them. There should be a fundamental rule of Mathematics that should immediately be coming to mind at this moment and be screaming at you... <b>NO DIVISION BY ZERO!</b>

Ah ha! We have realized a fundamental law that could be violated if we simply use the statement \( a-b \) where a and b are equal. This logical progression should be almost immediate to anyone that has learned Mathematics at its most basic levels. And this all comes from just the first line, all of this should have been going through your mind on the very first line of this proof! If this did occur to you on the first line, or even throughout the proof, then you most likely would not catch the error in the proof. Even if this did occur to you at some point, it still might not have registered with you. But why is this?

Another problem I would like to discuss is people's fundamental block in going from symbols to numbers. They do not understand that a, in this situation, can be any number. So, when they see "a", they do not see a number, they just see "a". That is why many people cannot make the jump from \(a-b\) means \(1-1\) or \(2-2\) or any other number. That means they will miss that it could yield a 0 result which could be problematic with division further down the road in the proof!

Well, that is my two cents on the subject. I love these types of proof but I wish more lay people could spot the error(s) in them.
