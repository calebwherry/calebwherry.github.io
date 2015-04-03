---
layout: post
title: "Rubik's Cube Upper Bound Meets Lower Bound at 20 Moves!"
date: 2010-08-16
status: publish
comments: true
share: true
categories:
- Computer Science
- Mathematics
tags: []
image:
  feature: main-banner-2.jpg
---

<img src="/images/rubiksCube.jpg" />

God's Number, the absolute number of moves by which any 3x3 Rubik's Cubes can be solved (and I suppose any nxn if you want to get technical, although at the moment 3x3 is quite impressive), has been sought after for many years. Many have tried to find God's Number but have only raised/lowered the upper and lower bounds of this problem. As of July 2010, this is now a <a href="http://www.cube20.org/">closed problem</a>! What is interesting about this result is that they used a brute force method to come up with God's Number so <a href="http://en.wikipedia.org/wiki/God's_algorithm">God's Algorithm</a> was not found, just the number by which God's Algorithm will have to abide. The site I linked above shows the computations that were done to arrive at this answer. They also have an analysis of which problems were the hardest with their methods.

There are $$43,252,003,274,489,856,000$$ different positions that the Rubik's Cube can take on so from a computational standpoint, this was quite a feat! 35 CPU years were used in performing this computation. Not that bad for such a hugh problem actually! I would have expected a lot more. The only thing left now is to find God's Algorithm which will solve any 3x3 Rubik's Cube in 20 moves using only <i>one</i> method! I do not foresee this coming around anytime soon though...
