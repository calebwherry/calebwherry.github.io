---
layout: post
title: "Concurrent GARTH (Genetic AlgoRiTHms) using C++11: A Framework for Concurrent GAs"
date: 2014-02-22
status: publish
comments: true
share: true
categories:
- Computer Science
- Programming
- Research
- Science
tags:
- Genetic Algorithms
- Lock-Free Objects
- Multiprocessor Programming
image:
  feature: main-banner-2.jpg
---

> tl;dr: Genetic algorithms are awesome. C++11 is awesome. Concurrency is awesome. Let's combine them all: <a href="https://github.com/Korovasoft/Concurrent-GARTH" target="_blank">Concurrent-GARTH</a>!

I am taking a pretty cool graduate class this semester at VaTech: Multiprocessor Programming. We have to do a semester research project so I decided take a project <a href="http://www.robertdfrench.me/" target="_blank">Robert French</a> and I have been working on for some years and make it <a href="http://en.wikipedia.org/wiki/Concurrent_computing" target="_blank">Concurrent</a>. The project name we coined awhile back was GARTH (Genetic AlgoRiTHs) so the new project name is going to be, you guessed it, Concurrent-GARTH! Here is <a href="https://github.com/Korovasoft/GARTH" target="_blank">one of the many manifestations of GARTH</a> that Robert and I worked on written in Java. Its aim was to be distributed but I am not entirely sure if I am going to try to add that piece in just yet to my design. I think it would be nice to have a concurrent version and distributed version then try to combine them later.

One of the biggest challenges I see for this project is the fact that GARTH is database driven. However, for this class I have to implement a Lock-free object so I really can't use the database anymore, it'd be cheating. The task at hand is going to be to construct a concurrent object that I can then unleash X-number of threads on to do my bidding. Many databases use a <a href="http://en.wikipedia.org/wiki/B-tree" target="_blank">B-tree</a> implementation to access all their data but I feel like that might be overkill for this project. It would be awesome to implement a concurrent B-tree but I really want to apply what I implement to some interesting problems. I could spend the next semester making an awesome concurrent B-tree implementation but I think that would be all I would have time for. So, I have decided to back away from that and use some other concurrent object... which I have yet to decide upon, ha! It won't be terribly complicated in the end but it should still be something substantial enough to warrant a research project using it. We'll see what I come up with...

A cool aspects of this project is that I am using the new(ish) C++11 standard so I get to use the shiny native thread libraries! I have no idea how this is going to work out in practice but I have high hopes that I won't have to turn to other libraries like OpenMP to get work done. I am new to the world of concurrent C++ so I have a lot to learn. It is looking to be a pretty cool project that hopefully I can get some nice results from. The main area of application that I am going to apply the <a href="http://en.wikipedia.org/wiki/Genetic_algorithm" target="_blank">genetic algorithm</a> framework to is some problems that come up in quantum condensed matter physics: finding optimal placements of charged particles on different surfaces given varying cost functions. This problem becomes quite intractable when the number of particles grows beyond just a few dozen. Using GAs can help search the configuration space of the particles on the surface and converge towards an optimal solution better than other types of optimization methods. This is not a ridiculously hard problem but it is a very neat application area for GAs. I am not going to talk anymore about the GA side of the house now but if you are interested, there is plenty of literature out there dealing with these methods.

All software for this project can be found at 2 places: <a href="https://github.com/calebwherry/Concurrent-GARTH" target="_blank">my forked repo</a> and the <a href="https://github.com/Korovasoft/Concurrent-GARTH" target="_blank">Korovasoft repo</a>. I perform development in my forked repo and push upstream to the Korovasoft repo periodically. All official releases (if/when we have any) of the software will be done on the Korovasoft repo. Continuous Integration is being run on each of these repos and can be found <a href="https://travis-ci.org/calebwherry/Concurrent-GARTH" target="_blank">here for my forked repo</a> and <a href="https://travis-ci.org/Korovasoft/Concurrent-GARTH" target="_blank">here for the Korovasoft repo</a> (if you are interested in Continuous Integration more, check out <a title="Continuous Integration + GitHub Repos" href="http://www.calebwherry.com/blog/2014/02/19/continuous-integration-github-repos/" target="_blank">my other post</a> about it).

A few quick clarifying notes about the previous paragraph:

* Korovasoft is the company Robert created back in late 2007. I came on board shortly after in 2008 while we were in undergrad. We are both somewhat Co-Founders in the effort and try to publish/present work we do under the company name. Eventually, we hope to solidify the company more and (maybe) make it our jobs instead of just a side-gig.
* All code is released under the MIT license and copyright of Korovasoft.
* If interested in the work, check out the <a href="http://www.korovasoft.com/" target="_blank">Korovasoft website</a> and contact us.

Follow the repo if you are interested in the work! I might post more once I get deeper into the project so stay tuned!
