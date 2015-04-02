---
layout: post
title: "Continuous Integration + GitHub Repos"
date: 2014-02-19
status: publish
comments: true
share: true
categories:
- Programming
- Software Engineering
tags:
- GItHub
- Travis-CI
image:
  feature: main-banner-2.jpg
---

There are countless reasons why a Software Engineer should adhere to best practices when designing software and I would like to discuss some uses of these using GitHub. Throughout my Computer Science education and my entire professional career I have tried to stay true to the <a href="http://agilemanifesto.org/" target="_blank">Agile Methodology</a> of developing software: performing code reviews, unit testing, small iterative dev cycles, and beyond. I feel it makes development a much more fun process and allows me to think critically more often than I would on projects that have longer dev cycles and less adherence to testing standards. Not to say methods like the Waterfall Method don't have their place, they certainly do, it's just that I find I work better in an Agile environment. But I digress...

Today I want to share my experience with using <a href="http://en.wikipedia.org/wiki/Continuous_integration" target="_blank">Continuous Integration</a> (CI) on some of my GitHub repos. I have been thinking a lot recently about doing this but never took the plunge. To be honest, I didn't want to go in and write the Git hooks to fire off the builds when commits were made. They wouldn't be terribly complicated but I knew it wouldn't be very elegant.

This is where <a href="https://travis-ci.org/" target="_blank">Travis-CI</a> comes in.

Travis-CI is a free CI framework that easily hooks up to your GitHub repos to run builds/tests/etc after each commit. You simply have to enable the hooks between Travis-CI and GitHub and BAM you are up and running with CI. This is extremely beneficial since you will know almost immediately if anything you have pushed to your repo has broken any tests or the build itself. On smaller projects this may seem like overkill but the benefit is really seen as projects get bigger and there are many dependency layers within your code and tests. I use the <a href="https://code.google.com/p/googletest/" target="_blank">Google Test</a> framework to write all of my unit tests and it allows me to scramble the order of tests to make sure I do not have unnecessary dependencies even in my tests. These two tools together make it so that I am very confident that at any moment in time my build and tests are healthy.

I have been in development situations where other members of the team commit stuff to master at random without any regard to the overall health of the repository. This really pisses me off. People do not think about what other things they could break just by making changes to libraries. For example, one thing that happened A LOT at one place I worked was that people would make changes to base libraries (things used by ALL applications) and never run build tests on their local branches before committing to master. There were multiple times a week where the builds for the mainline failed because of this. On top of that, we did not have CI on any of the repos, we did nightly tests and builds. This meant that everything from that day could be hosed because someone introduced a bug at 8AM and never bothered to test anything. Using CI, you can help solve issues like this since as soon as a commit happens, a build is kicked off so build errors/test failures will be known almost as soon as they happen. An even better situation would be that the actual commit doesn't go through until the build passes. This, however, takes a lot more infrastructure setup. Unfortunately, this can also make developers lazy and rely on the CI to find errors in their code. Developers should think critically at all points in development and not get too dependent on CI to debug their code. All-in-all it is good to use CI so you should.

Okay, enough of the stories and back to actually using Travis-CI with GitHub! On the repo side, all you have to do is add an extra file to the top level of your repo: `.travis.yml`. This file contains simple instructions for Travis-CI to perform when a commit happens. Here is the Travis-CI file for one of my projects <a href="https://github.com/calebwherry/Concurrent-GARTH" target="_blank">Concurrent-GARTH</a>:

<script src="http://gist-it.appspot.com/github/calebwherry/Concurrent-GARTH/blob/master/.travis.yml?slice=17:55"></script>

As you can see, we can specify the main language the project is in (mine is C++) and the compilers that we want to use. I tend to run all my builds using both the GNU gcc compiler and clang compilers so that I can develop such that both are supported. Since we do not own the servers Travis-CI runs the builds on, the build environment might not (is not in my case) be setup exactly as we need it. For Concurrent-GARTH, I need g++-4.8 because it correctly implements the C++11 standard features I need (native threads, lambdas, etc). I also use the Google Test framework so I have to make and install it before I can run my build. There are a few other options in the Travis-CI config but reading the documentation does wonders so check it out!

Here is the <a href="https://travis-ci.org/calebwherry/Concurrent-GARTH" target="_blank">Travis-CI page</a> for my Concurrent-GARTH project. You can see the entire history of all the CI builds that have been run and the states of each. This is extremely cool! I love being able to see how my repo's health has evolved over time based on commits.

One last note: I figured out recently that if you DO NOT want CI to be run on a certain commit, all you have to do is include this anywhere in your commit message: `[skip ci]` or `[ci skip]`.
