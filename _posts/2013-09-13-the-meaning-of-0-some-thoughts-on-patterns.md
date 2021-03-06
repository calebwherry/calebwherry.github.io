---
layout: post
title: The Meaning of \(0!\) & Some Thoughts on Patterns
date: 2013-09-13
status: publish
comments: true
share: true
categories:
- Education
- Mathematics
tags: []
image:
  feature: main-banner-2.jpg
---

Let me start out with this: I love mathematics. Even the simplest things in mathematics have a beauty that most people take for granted. This is extremely unfortunate since there is such power in mathematics. I wish more people were excited about mathematics but there are decades of education that have been bred into society that makes mathematics out to be dull and uninteresting. This couldn't be further from the truth. Mathematics is fun, interesting, and powerful. This post reflects these things and how I feel about some very fundamental aspects of mathematics.

With that being said, let's talk about some math! When I was an undergraduate, I took a lot of mathematics courses. I learned a lot of neat things and obtained a very diverse set of skills. One of those things I learned more than once during those times was this definition:

$$ 0! = 1 $$

When I and others asked "Why is this true?", the answer that was always told (and the answer that is in the books) is that we take this as an axiom, a truth without proof. And that was that. No other explanation or intuition to the axiom. I have always had issues with these types of things. I do not like things that are true because we say they are true, they seem made-up to me. I like concrete evidence as to why something is the way it is. This is, however, not how fundamental mathematics works and there are always axioms that have to be chosen in order for the framework we work in to be consistent.

However, there are beautiful formulas, patterns, recurrence relations, etc. that are often discovered once a set of laws/rules/axioms are set forth. One such pattern is for the definition of the factorial. If you are a little rusty, a factorial is defined as:

$$ n! = n*(n-1)*(n-2)* \cdots *3*2*1 \, \, \, , n \in \mathbb{Z_+} $$

Along with this definition, we are usually given the above axiom of \(0!=1\). As I said, we are never given any reason as to why this is the case. And really, it is an axiom so there is no "reason" as to why it is the way it is. For convention, things work out better when \(0! = 1\) and so we define it to be an axiom.

I hadn't thought about these things in a very long time but the other day I saw a <a href="http://www.youtube.com/watch?v=Mfk_L4Nx2ZI" target="_blank">Youtube video</a> talking about this issue on the Numberphile's Youtube channel. It was a very illuminating video and showed a pattern that is very beautiful for the axiom above. I'll write out the pattern below:

$$
5! = \frac{6!}{6} = \frac{6*5*4*3*2*1}{6} = 5*4*3*2*1 = 5! = 120 \\
4! = \frac{5!}{5} = 24 \\
3! = \frac{4!}{4} = 6 \\
2! = \frac{3!}{3} = 2 \\
1! = \frac{2!}{2} = 1 \\
0! = \frac{1!}{1} = 1
$$

When I saw this I was amazed! Why hadn't anyone ever showed me this before?! It was so simple and once I had seen it, seemed so obvious! I know this pattern does not explain the axiom \(0!=1\) but it gives us some sort of handle on a different way to look at the definition of factorial and the axioms we use. It lets us recognize that although we have a strict definition for factorial, that is not the only way we have to look at the problem.

Now I would like to point out that some people do not like the above pattern because it seems completely post hoc. I disagree very much with this sentiment. Just because a pattern is seen after the fact doesn't make it any less relevant or useful. Patterns help us understand advanced ideas and I believe it to be very important for anyone to look at a problem from any direction they can imagine. Looking at problems/definitions/laws from different perspectives leads to new revelations and/or revolutions. A famous example is that of M-Theory. In the beginning stages of String Theory, the field hit a road block: they had 5 self-consistent theories of how strings behaved but NONE of these theories were consistent with each other. They all had sound mathematical and physical bases but unfortunately they did not fit together in a unified framework, something wasn't right. However, a brilliant mathematical physicist by the name of Edward Witten proved that these 5 theories were actually <i>the same theory</i>! He had a fresh perspective and looked at the problem just right to recognize a pattern no one else had seen. His insight brought the 5 theories together which created M-Theory, the unified theory for String Theory. Was his pattern completely post hoc? Absolutely. Was is revolutionary and changed how String Theory was viewed from that point on? Definitely. Without his insight, String Theory could well have become a dead theory and not the thriving field of theoretical physics it is today.

All that to say: patterns are extremely powerful. They can lead to new discoveries and more. Simple patterns like the one showed above for factorials can help ground the theories for people that are learning them and really make them concrete instead of so abstract. I find that I always question the definitions given to me in science and see if I can explain them differently. It really stretches my mind and allows me to try and draw conclusions that are not typically drawn. I find this helps most in teaching when I am dealing with people with all types of learning styles. As an educator, you have to be ready to explain something to a person who has a very different learning style than others do. Being able to show people patterns that cut through some of the fundamental theories is an extremely powerful tool and I wish my teachers had used it more in my earlier education.
