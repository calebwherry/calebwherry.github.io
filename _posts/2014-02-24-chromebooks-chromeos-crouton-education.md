---
layout: post
title: "Chromebooks, ChromeOS, crouton, & Education"
date: 2014-02-24
status: publish
comments: true
share: true
categories:
- Education
- Programming
- Technology
tags:
- ChomeOS
- Chromebook
- crouton
image:
  feature: main-banner-2.jpg
---

<a href="http://www.google.com/intl/en/chrome/devices/" target="_blank">Chromebooks</a> are awesome and so is <a href="http://en.wikipedia.org/wiki/Chrome_OS" target="_blank">ChromeOS</a>: I bought a Chromebook last year and love it! My wife <a href="http://meaganjsouth.com/" target="_blank">Meagan </a> didn't like it very much at first but now has pretty much stolen it from me and uses it at school all the time. I would like to talk a little about my experience with the Chromebook and some of the things I have done to supercharge it.

The first thing to realize is that ChromeOS is completely cloud-centric. You should be comfortable storing and using cloud services (mainly Google's) to do all of your daily tasks. Many people have pointed out that the Chromebooks come with very little built-in memory but the reason for this is because you don't <em>need</em> that much built-in memory when you store everything in the cloud. I use Google Docs everyday and have been porting over all of my old M$ documents to the Google format over the past year (I have a lot and want to verify the transition since the mapping between the two is not one-to-one). There is no space charge (currently) for documents that are in Google's format so I get free storage of my documents and can easily access them from wherever I want. This means that the hardware I use to access these documents can be smaller, lighter, and less powerful since I am off-loading all the storage to the cloud. That is why the Chromebook is lightweight, fast, and power efficient: it does not need all that extra hardware that your other computers have to run things like M$ Word, PowerPoint, etc. Once you get used to using Google's cloud services, you will fall in love with them and never turn back.

Another awesome feature is that all your settings for your Chromebook are also stored in the cloud! This means that if you really screw up your Chromebook (I talk more about that later in this post) then you can easily "powerwash" your machine and undo any settings/installs that screwed up your machine. Since you can't install any native software (all is installed through Chrome and Google Play), this problem is pretty much mute unless you do more advanced things.

Although I really like ChromeOS, I wanted to use my Chromebook as a dev machine so that I could take it to class easily and work on my software projects (there are tools to do this in the cloud but I needed too many compiler/system specific tools to do dev so they were not feasible solutions). In comes <a href="https://github.com/dnschneid/crouton" target="_blank">crouton</a>. Crouton stands for <em>ChRomium Os Universal chrooT envirONment</em> and is an awesome tool to have/use if you own a Chromebook. It allows you to install another Linux OS on your Chromebook, called a chroot after the UNIX command that allows for multiple environments to run simultaneously. The benefit of installing a chroot is that you do not have the memory overhead and speed decrease that you have when running 2 operating systems at the same time (like you would with a virtual machine, say with Parallels/VirtualBox/etc). With a chroot, the two OSes share the same system resources (there is a security risk in doing this but we will not talk about that here, follow the links provided to learn more) but one is strictly confined to its own file system. I have all the new gcc and clang compilers installed on my chroot and do development all the time on it. I love being able to carry around a super lightweight device that I can also do dev on. There is obviously a performance hit since the hardware is much less speedy but it has worked out so far for me. I compile a lot of C++11 programs and $\LaTeX$ files which seem to be a fine workload for it.

Using crouton, I run Ubuntu 13.10 (Saucy Salamander) and have not had very many issues. I found <a href="http://solvitor.com/2013/09/02/a-better-arm-chromebook-lamp-stack-based-on-crouton-and-debian/" target="_blank">this tutorial</a> to be invaluable in setting up my chroot with crouton. I had very little issues with installing the version of Ubuntu I wanted. I did screw up a few times and had to powerwash my Chromebook but that was a super simple task and didn't cause too much headache (I would recommend doing backups of your chroot, it makes it easier to restore them. Check the crouton docs on how to do this).

There is another topic that I would like to bring up that has also benefited greatly from Chromebooks: education. There are entire schools that have gone to Chromebook centered computing labs. When I was in high school, we had the <a href="http://en.wikipedia.org/wiki/IBook" target="_blank">iBooks</a> which were undoubtedly expensive and were lugged around in extremely heavy rolly containers. With the Chromebooks, children/teenagers/young adults are now able to get access to cutting edge technology at a fraction of the educational cost. A school can purchase Chromebooks in bulk and have their students using technology that is amazing and backed by a company that is committed to the education of our youth. This is probably the main reason why I love the Chromebook so much: it can and is being used to change how education it being taught and how technology is being used in the classroom. This is a very powerful tool that could change the future for so many young people and I am glad that I can help support a company who is invested so much in outreach for communities, our society, and the education of our youth.
