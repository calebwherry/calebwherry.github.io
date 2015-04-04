---
layout: post
title: "A Book Review: An Introduction to Computational Physics by Tao Pang"
date: 2013-10-15
status: publish
comments: true
share: true
categories:
- Book Reviews
- Computer Science
- Physics
- Programming
tags:
- Computational Physics
image:
  feature: main-banner-2.jpg
---


<figure>
	<img src="/images/an_intro_to_comp_physics-tao_pang.jpg" />
	<figcaption>ISBN-13: 978-0521532761</figcaption>
</figure>

> tl;dr: Good book. Go buy it especially if you want a ton of complete, runnable code examples.

I am using this book for my graduate class in Computational Physics this semester (Fall 2013 @ VaTech). I was pretty skeptical at first about using it because:

1. Almost all Computational Physics books I have read/seen are terrible.
1. The code in the main text is all written in Java.


The first reason might seem a bit subjective (okay a lot bit) but I honestly have read/seen a lot of Computational Physics books and they have all have been not-so-great. They either talk completely about physics and pay next to zero attention to creating algorithms/software or they try and talk Computer Science and get it completely wrong. I have never seen a book that handles Computational Physics well from both the Physics and Computer Science perspectives.

The second reason above was more of an "Umm... why?" question when I first opened the book. The author states in the preface that Java is becoming one of the main languages used in Scientific Computing in recent years. I disagree with this statement. Although Java has seen some nice numerical libraries created over the past 10 years and effort has been put into making it more suitable for scientific computations, it is definitely not a "main language for Scientific Computing". I am <i>not</i> going to give supporting details/sources to this claim because I do not want to get sidetracked from my main purpose here: a book review. So I will move on (maybe a follow-up post later on Java and scientific computing...)!

Once I actually started to read the book and work out the problems, I found it a very interesting read. The first thing to note here is that the author <i>does not</i> use any advanced features of Java. The code can be easily copied and, with only minor alterations, converted to C++. So my point above about using Java becomes mute since there are no special features of Java used.

From a Physics standpoint, I believe this book does a very good job at explaining some interesting Physics that goes along with each algorithm/problem set. The reader does not get overwhelmed with the amount of Physics that is being covered. It is manageable for someone who has exposure to undergraduate Physics (Quantum, E&M, Mechanics, etc). The problems at the end of each chapter are a nice update to some boring old problems I am used to seeing. Pang pulls in many different areas of Physics so the reader can stretch their skills to cover these topics. This book should be a great resource for Physics students who need a jump start on code for algorithms they are implementing. Pang provides code snippets throughout the text that are (usually) self-explanatory and can be copied and used right out of the gate.

Even with Java turning out to be a non-issue, from a Computer Science perspective, I do not think this book does a very good job. It provides lots of code but doesn't do a good job at explaining the innards. Pang also does not talk about computational efficiency with respect to the code which I think is a gross oversight. Analyses can be done all day for algorithms but a bad implementation can ruin it all. I wish there were more comments as to why he decided to do what he did in some of his algorithms.

For some people, having the amount of code that is available in this book is a good thing. However, I think at times it might be a little much. It sometimes leaves little for the reader to learn/implement. Pang tries to tie in extensions with the problems at the end of the chapters but in some cases I do not think it is enough. The book is more of a "methods" book in that regard since it gives complete, compilable/runnable code examples to almost all of the problems. This is definitely a great resource but for students learning Computational Physics, I believe Pang has already done a lot of the heavy lifting.

I think the biggest pet peeve I have about the whole book is that Pang uses these two words interchangeably: iterative and recursive. As a Computer Scientist this is a glaring error that any computational book should not contain. I know the book was written by a physicist but come on! They aren't even close to being the same thing...

All in all, it really is not a bad book and Pang did a great job. It is probably the best Computational Physics I have used. There are lots of examples, chapter problems, and code samples. Although the code samples are a bit 'complete' for my taste (reveal too much to the reader), for a Physicist I believe this to be a great resource if you are doing Computational Physics research. If you are Computer Scientist trying to really learn Computational Physics, I'd move along and find another source. You will get more mileage out of a Numerical Analysis book or traditional Computer Science text on numerical methods that deal with specifics like computational trade-offs and space/time complexity. If you are in middle (know some Physics and know some Computer Science), this is a perfect book should suit you well in learning introductory Computational Physics.
