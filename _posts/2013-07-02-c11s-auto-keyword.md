---
layout: post
title: "C++11's 'auto' Keyword"
date: 2013-07-02
status: publish
comments: true
share: true
categories:
- Programming
tags:
- C++
- C++11
image:
  feature: main-banner-2.jpg
---

<a href="http://isocpp.org/blog/2013/07/http-accu.org-var-uploads-journals-Overload115.pdf" target="_blank">Interesting article</a> on C++11's 'auto' keyword.

When I first started using the 'auto' keyword, I had a weird feeling start growing inside me. I didn't like the type being inferred for me by the compiler, I like knowing exactly what my code does and what is going on. However, when you start down the road of iterators on templated objects in for loops you start getting into some loooong expressions (or also lambda return values, which can be a bit complex sometimes). So the auto keyword really helped to compactify the code and really helped with readability.

I'm still up in the air about though, I have not yet gotten into a situation where it has bitten me in the ass. I'm sure when I do get there, I might rethink using it.
