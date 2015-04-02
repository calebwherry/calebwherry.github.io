---
layout: post
title: "Raspberry Pi 2 - Projects"
excerpt: "Raspberry Pi 2 projects I want to tackle."
date: 2015-03-10
status: publish
comments: true
share: true
categories:
- Technology
tags:
- "Raspberry PI 2"
image:
  feature: main-banner-2.jpg
---

<figure>
	<img src="/images/raspberry_pi_2.jpg">
	<figcaption>Raspberry Pi 2 bare minimum.</figcaption>
</figure>

My Raspberry Pi 2 came in the mail a few days ago. I have been wanting to buy one to play around with but could never commit. Now I have! I have a few projects in mind to use it on but have not settled on which I should pursue first. I really want to combine 2 of them together but I think that would be a bit much for my first project.

### Idea 1: Mini-TinyTitan

<a href="http://tinytitan.github.io/" title="TinyTitan" target="_blank">TinyTitan</a> is an awesome project developed by a close friend and colleague of mine at Oak Ridge National Lab: <a href="http://www.robertdfrench.me/" title="Robert French" target="_blank">Robert French</a>. I wrote a proposal to extend this work at GTRI that was (most likely) going to get funded. It used a different board (Zybos, which have an FPGA on the same die as the CPU) but since I am leaving GTRI, I'm not sure what will happen with it. I didn't really want to work with the Zybos anyways so I am starting to plan on my Mini-TinyTitan.

One of the really nice things about the Pi 2's is that they have 4 core CPUs and 1GB of ram. This allows for much for flexibility in the computations that can be performed on the Pi 2s. I want to setup my Mini-TinyTitan to have 1 head node and 4 slaves for a total of 16 compute cores. I am hoping to make it as small as possible and draw not very much power. I am unsure how that will go since I am wanting to do HPC related tasks with it but that will come with experimentation.

When I started thinking about this project, I had the idea of creating a mobile TinyTitan. That is where I wanted to take this idea and merge it with my Idea 2 below. However, there are many complications with merging the two and I think I should get an alpha version of one done before I try and combine them. With that being said, I think it would make a great show piece for something like the Atlanta Science Festival to have a mobile HPC robot. We will see where I get on thees projects this summer!

### Idea 2: PiRobot

I've always wanted to build a robot, especially one with skid control so I can use a PlayStation or XBox controller to move it around. There are tons of interesting tutorials and models out there for building Pi driven robots so that is what I want to do. As with Mini-TinyTitan, I really want the system to be low power but also have some decent torque. These two things don't usually go together so I'm pretty sure I'm going to have to give up on the low power aspect. Furthermore, if I ever plan on merging this with the Mini-TinyTitan, that is going to be both heavy and suck up a lot of power. Another reason as to why I won't want to tackle them both at the same time right now.

I believe I am going to start with this project since it only needs 1 Pi and will be the most fun. I am still trying to decide on the chassis. I can either CAD the entire thing myself (which I have no experience with) or buy a kit and put it together. Buying a kit seems like a cop-out so I am still unsure. PiBorg makes a <a href="https://www.piborg.org/diddyborg" target="_blank">really cool model</a> but it is a bit pricey. I might just buy a super cheap one and see where that goes.

### Idea 3: Auto Cat Toy

I have been telling Meagan for a while that I want to build some sort of play toy for our cats (we have 2 cats: Chunk and Scrappy). My original idea was to create some sort of moving board that had stuff behind it. However, I think a better model would either be an auto laser pointer or something that swings a cat toy around.

The laser pointer would be the easiest to do but I'm not sure how engaging it will be for the cats. The "arm" will be harder and there are a lot of issues that come up like making something sturdy enough so the cats don's destroy it. Also making something that keeps their attention is key. I think it would be really cool if I could create some sort of machine learning algorithm that learned from the cats interaction with the toy and was able to anticipate their actions and create new, better ways to swing the cat toy. That way it isn't random and also isn't repetitive. That's not an easy task though so we will see if I ever get around to implementing that part or not.

### Conclusion

Whatever I end of doing first, I am going to chronicle the build process on this blog. I've never done a project like this so I'm looking forward to it! As I said above, hopefully I can create something interesting enough that I can showcase it at the Atlanta Science Festival or some other event. TinyTitan itself has been wildly successful so I think a Mini/Mobile HPC robot would be pretty successful as well.
