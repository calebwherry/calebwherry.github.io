---
layout: post
title: "Interesting CppCon 2014 Talks - Part 1"
date: 2015-01-24
modified: 2015-03-14
categories:
- Programming
- Software Engineering
- Technology
tags:
- C++
- C++11
- C++14
status: publish
comments: true
excerpt: CppCon talks.
---

There were some very interesting talks last year at CppCon 2014 (<a target="_blank" href="https://www.youtube.com/user/CppCon">main Youtube channel</a>). Unfortunately, I did not get to go to the conference but I'm really hoping I can go next year. There is a ton of valuable information from this conference and it is truly the place to be if you are interested in cutting edge topics dealing with the C++ language and how it is used in academia and industry. Fortunately, the CppCon committee procured funds to make all of the talks available for free online so I got to see the main ones I was interested in! Below are the videos plus some of my thoughts. I will follow-up with a part 2 that has more videos as well.

### Keynote 1: Bjarne Stroustrup (C++ Creator)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/nesCaocNjtQ" allowfullscreen frameborder="0"> </iframe>
</figure>

I enjoyed this talk a lot. Bjarne is very adamant about keeping things simple when you are programming in C++ and he really drives this idea home here. Many people jump into C++ and try and be really fancy right off the bat and either over engineer the system or waste time on premature optimization. In this talk Bjarne gives the base essentials to writing good, clean C++ code without all the fancy new bells and whistles like move semantics, r-value references, etc. For the majority of C++ engineers, the stuff he goes over is all you need to write good software that is already optimized in some ways by the compiler. Nothing truly new here or out of left field but a good talk.

### Keynote 2: Mark Maimone (Rover Software Architect @ NASA JPL)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/3SdSKZFoUa8" allowfullscreen frameborder="0"> </iframe>
</figure>

I was kind of let down by this talk. I was hoping for a lot more and got a lot less. Mark didn't really go into <em>how</em> they used C++, just some of the things they do with it like writing video/image processing algorithms. I was hoping for some more meat on how they designed their rover projects and fit that into C++. I did find it very interesting that they only use a very small subset of C++. Originally is was a very hard sell to even use C++ instead of the standard C on space vehicles. They eventually got it approved but with a super reduced set of functionality. The biggest things they don't allow are: templates, exceptions, operator/function overloading (except in very rare situations), and any allocations on the free store (heap). They have wrappers around the new/delete keywords that use "placement new" semantics that wrap around and place the memory back in the stack frame of the current location. This means that the calling function can only corrupt the part of memory it is in so restarting that process is all that should need to be done. This keeps the rover from having to be completely shutdown if some operation with the camera malfunctions.

Although I didn't like the talk too much, I was very glad to see this as a keynote. The CppCon organizers are really trying to pull in all domain experts that use C++ and showcase their use of the language. I think this is key to the survival of C++ for the next 20-30 years.

### Keynote 3: Mike Acton (Engine Director @ Insomniac Games)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/rX0ItVEVjHc" allowfullscreen frameborder="0"> </iframe>
</figure>

Very, very interesting talk. Just as with Mark's talk above he begins by laying all of the features of C++ that they don't use in the gaming industry (templates, exceptions, function overloading, etc) which I find fascinating. Beyond that, I was skeptical at first when listening to Mark's talk but after about 10 minutes the idea of data-oriented design clicked and I understood why it is essential in the gaming world (and other data-oriented fields). Mike gives a wonderful example of a chair in a game. Thinking about it like a typical OOP problem: a PhysicsChair, StaticChair, BreakableChair, etc are all subclasses of a chair. But in reality (solving/dealing with the chair in the game), they are handled entirely different and share almost no similarity thus there is no class hierarchy like there would be in the real world. Modeling things after how we see them in the real world becomes an issue. So using typical OOP design muddles the data representation and confuses the idea of a real-world chair and the game chair data you are trying to manipulate. This struck me as odd at first but it really does make sense since they are very different data representations of a chair, not some abstract idea of a chair. 

He goes on to talk about how data should be he focus, not software. The data is persistent from point A to B with the software being a transition point. This is an interesting idea that makes sense when you are thinking data-oriented design. Although I tend to think that software is very important and that its design should be well-thought out, if you have a very good handle on your data then the focus should be on how to manipulate that data. However, in some cases this just isn't possible in my mind. Especially when the data is not structured or has anomalies in it that only designing good software can help deal with.

Mark ended with a very interesting quote about how programmers who follow design patterns are pretty much mindless and will continue to produce crappy code that has complete disregard to how data is laid out in memory and how it is accessed throughout the code. I'm not sure I would have agreed with someone saying this to me before this talk but Mark did a good job convincing me otherwise. OOP design really does hide a lot of things that are potential bottlenecks that new iterations of C++ are trying to solve. Just as Mark said, C++ is trying to solve problems it itself created by creating classes, inheritance, function/operator overloading, etc.

A great quote towards the end from Mark: "Ok, great. You don't care how long it takes ... Great. But people who don't care how long it takes is also the reason why I have to wait 30 seconds for Word to boot." This was in reference to a question about people who program and don't care about how long it takes to read from certain data structures or their software's performance. Pretty awesome answer and I think he is spot on in his assessment that the user is always interested in performance no matter the domain.

### Herb Shutter (Lead C++ Software Architect @ M$)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/xnqTKD8uD64" allowfullscreen frameborder="0"> </iframe>
</figure>

This was just an all around great talk. It got into some really neat new things that C++11/14/17 are brining to the table and explained a few topics that I myself was somewhat shaky on with the new standards. I would highly recommend this talk to anyone that is interested in learning what C++ has to offer these days. Herb is a great speaker and really knows his stuff.

### Titus Winters (C++ Library Team Lead @ Google)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/NOCElcMcFik" allowfullscreen frameborder="0"> </iframe>
</figure>

I didn't really get much from this talk. Titus pretty much just went over Google's style guide and the things they do and do not allow in their code base. He is super against exceptions and many people in the audience ask him about it and all he says is "Show me a case study where is doesn't hurt performance." With a code base as large as Google's I do understand the need to scrutinize the language and trim the things that hurt performance but he also didn't give any good reasons why <em>not</em> to use them, just that they were bad. I was hoping for some cool insider information or something about Google but it is a was pretty boring.

### Scott Meyers (Software Consultant)

<figure>
	<iframe width="560" height="315" src="http://www.youtube.com/embed/wQxj20X-tIU" allowfullscreen frameborder="0"> </iframe>
</figure>

Scott has written a lot of C++ books that people love (Effective C++ series) and he really knows his stuff. This talk is essentially how type deduction works in C++ when dealing with templates and the new auto semantics. Tons of useful information and some really good material for interview questions for C++ guru jobs, IMO. I know only a handful of these rules and would be hard pressed to reason through some of these examples simply because I don't have enough exposure to using them. I need to beef up my understanding of how the underlying systems in C++ work more.

He has a really interesting example about an easy way of finding out what type the deductions are coming up with since there are so many different rules. Below is the code he showed.

{% highlight cpp %}
template <typename T>
class TD; // "Type Displayer"
 
// Figure out template deduction types:
template <typename T>
void f(T& param)
{
  TD<T> tType;
  TD<decltype(param)> paramType;
}
 
// Figure out auto deduction types:
int x = 22;
const int& rx = x;
 
auto y = x;
TD<decltype(y)> yType; 
{% endhighlight %}

All it does is create a class that has no definition and then tries and instantiate it with the types you are trying to inspect. Since there is no class definition, it will not compile but the compiler will spit out why it can't compile something with the specific type supplied. This is a super clever and handy trick to have and use. Since there are so many different rules now for type deduction, this could really be beneficial when you aren't sure what type the compiler is deducing.

### Conclusion

I think that is enough for part 1. I have had this post as a draft for over 2 months so I needed to push it out. I will follow-up in the next month with part 2 hopefully. I really enjoy watching these videos and have found some recent videos from the C++ Meeting that are also excellent. Maybe I'll also write about those...