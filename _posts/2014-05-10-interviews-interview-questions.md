---
layout: post
title: "Interviews & Interview Questions"
date: 2014-05-10
status: publish
comments: true
share: true
categories:
- Life
- Programming
- Software Engineering
tags:
- Interview Questions
image:
  feature: main-banner-2.jpg
---

> tl;dr: This is a really long post and full of interview questions. If you are just interested in the code, it can be 
> <a href="https://github.com/calebwherry/BlogCode/tree/master/interviews_and_interview_questions" target="_blank">found on my GitHub</a>.

I'll update this post from time to time whenever I change jobs/careers to include new interview information/questions. All new sections will appear at the end of this post.

*Updated: 3/5/2015 - Nexidia, Inc. (Accepted - Senior Software Engineer)*

<hr />

I've had many interviews over the past 8 years, some good and some bad. Each one has been a mix of both technical and behavioral questions. I would like to document some of the technical questions here along with some of my experiences. All code is compilable so enjoy (some might need C++11 support so compile with correct std flag: g++ -std=c++11 file)!

### OEM Tube Assemblies (Internship) - Accepted Offer (Spring 2008)

This was my very first interview. It was for a local company in Clarksville, TN for the Spring of my Sophomore year. I was not interviewed by anyone on a technical basis, just had a recommendation from one of my professors. I remember talking with their HR person but I can't remember if they asked any questions or not. In the end, an easy interview!

### Lawrence Livermore National Lab (Internship) - Accepted Offer (Summer 2008)

This interview was a step up from OEM Tube Assemblies in that I had a phone interview with my potential boss before getting an offer. He asked me what classes I was taking and some projects I had worked on. Nothing technical at all, he gave me a pitch for the project and I said I'd do it.

### NASA Langley Research Center (Internship) - Accepted Offer (Fall 2008)

No technical interview, I received an email from my potential boss before getting an offer. He pitched his project, asked if I was interested, and I said yes.

### NASA Jet Propulsion Lab (Internship) - Accepted Offer (Spring 2009 & Summer 2009)

No technical interview and no contact from potential boss. Accepted sight unseen.

<h3>Google (Internship) - No Offer</h3>
<p>This was my first interview with a big software tech company. It was after my sophomore year, during my 2nd NASA internship. I had 2 phone interviews but it didn't proceed any further. The questions were general at first about my school work then they ask me some technical questions. I don't remember them very much but here are the ones I do remember.</p>
<p>Question 1: How would you design ads to be displayed for a given 3 word query (example query: "red horse barn")? Keep in mind scalability!</p>
<ul>
<li>I took the first 10 minutes or so to talk through some ideas I had for this question since it was pretty broad. I don't recall what they were really but the interviewer shot down a lot of them. I then decided to take a more mathematical approach and talked about the binomial theorem and how that fleshed out problems for data structures that weren't hash-based (look-up being the major bottleneck). The interviewer was impressed with the mathematics I used and liked how I incorporated it into my hashing approach. I can't remember the actual details though.</li>
</ul>
<p>Question 2: Given a list of increasing numbers, how would you turn that list into spreadsheet headings (A-Z, AA-ZZ, AAA-ZZZ, etc)?</p>
<ul>
<li>I really screwed this question up and it cost me the internship I think. I could not get the inner loop logic correct and the interviewer didn't give me any help. This meant the question took up the whole 20 minutes we had and she didn't seem too impressed. Oh well, it would have been cool to intern at Google but I took NASA instead which was pretty badass. Here is a particular implementation that works.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>int main()<br />
{</p>
<p>  // Constants:<br />
  const int BASE = 26,            // Base that we are computing labels for.<br />
            ASCII_START_VAL = 65, // ASCII value of 'A', where we start.<br />
            MAX_NUM = 100;        // Maximum number of headings to process.</p>
<p>  // Grouping count for headings:<br />
  int groupCount = 0;</p>
<p>  // Loop through and print out each label, one per line:<br />
  for (int i=0; i&lt;MAX_NUM; ++i)<br />
  {</p>
<p>    // Increment group count if multiple of BASE:<br />
    if ( ((i%BASE) == 0) ) groupCount++;</p>
<p>    // Print each letter per group count:<br />
    for(int j=0; j&lt;groupCount; ++j)<br />
    {<br />
      cout &lt;&lt; static_cast&lt;char&gt;( (i%BASE) + ASCII_START_VAL);<br />
    }   </p>
<p>    cout &lt;&lt; endl;</p>
<p>  }</p>
<p>  return 0;<br />
}<br />
[/code]
</p></div>
</div>
<hr />
<h3>IBM (Internship) - Wait-listed</h3>
<p>This interview was pretty fun, it was for IBM's Extreme Blue Internship, their elite program. I had 2 phone interviews and was wait-listed for a project but I suppose the project leads didn't like my background or interview answers. I would have liked to participate, I got my buddy Robert French to apply the following year and he was selected and liked it a lot. I forgot a ton of the questions they asked but here the ones I remember.</p>
<p>Question 1: What is the difference between final, finally, and finalize in Java?</p>
<ul>
<li>Final has 3 use cases:
<ul>
<li>Variable: Can't be changed.</li>
<li>Function: Can't be over-ridden.</li>
<li>Class: Can't be inherited.</li>
</ul>
</li>
<li>Finally: Third section that can used with try/catch block that ALWAYS gets called, even when exceptions happen.</li>
<li>Finalize: Called when an object is destructed by garbage collector.</li>
</ul>
<p>Question 2: Explain some different types of SQL joins.</p>
<ul>
<li>ANSI joins: inner, left outer, right outer, full outer, and cross. All of these joins depends on what you want your result set to be and how you are pulling the data from your tables (examples below are for only 2 tables A & B).
<ul>
<li>Inner: This is the most typical and natural join and does not usually need to be explicitly stated. The result set is a combination of rows from table A and table B that match the where clause directly. NULL values are ignored and are not matched (unless explicitly looked for).</li>
<li>Outer (Full, right, left): Outer joins allow us to match against null values. Full allows NULLs from both table A and table B, right allows NULLs from table B, and left allows NULLs from table A.</li>
<li>Cross: This join is the same as the mathematical (Cartesian) cross product. For every row in table A, this join matches it with every row in table B. Therefore you get a matching of every row in each table.</li>
</ul>
</li>
</ul>
<p>Question 3: How would you find all phone numbers in a given file?</p>
<ul>
<li>Most people would use awk or sed to accomplish this but I prefer grep! The one below is a little bit fancier than the one I came up with in the interview (this one takes into account spaces) but I couldn't help sprucing it up.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="shell"]<br />
$ grep -o '([0-9]\{3\})\s*[0-9]\{3\}\s*-\s*[0-9]\{4\}' filename<br />
[/code]
</div>
</div>
<p>Question 4: Describe the 3 pillars of OOP.</p>
<ul>
<li>Encapsulation: Single word - abstraction. Create classes that hide data and implementation that the users do not need to know about.</li>
<li>Polymorphism: Create functions/classes that can take multiple types without having to explicitly code for the types (templates in C++). Function overloading is also sometimes considered polymorphic since you use the same function names but different return type and parameters.</li>
<li>Inheritance: The ability for classes to have subclasses that can use the data that is present in the parent class. This allows for the creation of hierarchy in class structure and reduce code duplication. It also helps with encapsulation.</li>
</ul>
<p>Question 5: Explain what happens when you type in a URL and press the enter key. Use as much detail as possible at all levels (hardware and software).</p>
<ul>
<li>I'm not even going to try and answer this question here since it has so many levels. I stumbled through about 10 minutes of going into as much detail about every level of the computer I knew. I talked about circuits, graphics, the IP stack, DNS servers, packets, AES encryption, etc. It was a pretty cool question and I think it really shows how much someone knows about computing systems as a whole.</li>
</ul>
<hr />
<h3>Microsoft (Internship) - No Offer</h3>
<p>Interviewing with M$ was a lot of fun, which I didn't expect! They flew me out to Redmond and the hotel was extremely nice! I loved the office too, very pretty and the campus was great. I thought they wined-and-dined us interviewees (there were multiple people interviewing) and it was nice talking to them.</p>
<p>Question 1: Flip the least significant '1' bit in a given integer.</p>
<ul>
<li>I spent waaaay too long on this question and didn't get the answer. It was a super simple answer and the guy had a smirk on his face the entire time I was at the whiteboard. I went through trying to convert the integer to a string and then finding the last significant and flipping it. This was pretty ridiculous, to say the least. I have highlighted the line below that does the logic to flip the bit.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp" highlight="14"]<br />
#include &lt;bitset&gt;<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>int main()<br />
{<br />
  int a = 11;<br />
  bitset&lt;8&gt; b(a);</p>
<p>  cout &lt;&lt; &quot;Before flip: value = &quot; &lt;&lt; a &lt;&lt; &quot; | bits = &quot; &lt;&lt; b &lt;&lt; endl;</p>
<p>  // Main logic for lowest '1' bit to be flipped:<br />
  a = (a-1) &amp; a;</p>
<p>  b = bitset&lt;8&gt;(a);<br />
  cout &lt;&lt; &quot;After flip: value = &quot; &lt;&lt; a &lt;&lt; &quot; | bits = &quot; &lt;&lt; b &lt;&lt; endl;</p>
<p>  return 0;<br />
}<br />
[/code]
</p></div>
</div>
<p>Question 2: Write code to traverse a Binary Tree by inorder, preorder, and postorder traversals.</p>
<ul>
<li>This one I knew easily and I think he gave it to me because I screwed up the previous question. I am not going to write out the answers here but link you to the code I wrote for a library to do this: <a href="https://github.com/calebwherry/Cpp-Libraries/blob/master/lib/DataStructures/BinaryTree.hpp" target="_blank">BinaryTree implementation</a>.</li>
</ul>
<p>Question 3: Write a default constructor, custom constructor, destructor, copy constructor, and assignment operator for a given class with a character array as a private data member.</p>
<ul>
<li>This question was straight forward and just took some time to write on the board. I think it is a very good question because it sees if the person knows the difference between some fundamental principles in C++ and also if they are familiar with deep vs shallow copy. I think I goofed on the syntax for the operator overloading during the actual interview but here is a working solution.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;cstring&gt;<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>class MyClass<br />
{</p>
<p>  private:</p>
<p>    char* data;</p>
<p>  public:</p>
<p>    // Default constructor:<br />
    MyClass()<br />
    {<br />
      data = new char[0];<br />
    }   </p>
<p>    // Custom constructor:<br />
    MyClass(char* data_)<br />
    {<br />
      data = new char[strlen(data_)];<br />
      strcpy(data, data_);<br />
    }   </p>
<p>    // Destructor:<br />
    ~MyClass()<br />
    {<br />
      delete[] data;<br />
    }   </p>
<p>    // Assignment operator:<br />
    MyClass&amp; operator= (const MyClass &amp;rhs)<br />
    {<br />
      // Check for self-assignment:<br />
      if( this == &amp;rhs)<br />
      {<br />
        return *this;<br />
      }   </p>
<p>      // Copy contents:<br />
      data = new char[strlen(rhs.data)];<br />
      strcpy(data, rhs.data);</p>
<p>      // Return obj:<br />
      return *this;<br />
    }</p>
<p>    // Print function:<br />
    void display()<br />
    {<br />
      cout &lt;&lt; &quot;Data: &quot;;</p>
<p>      size_t size = strlen(data);</p>
<p>      for (int i=0; i&lt;size; ++i)<br />
      {<br />
        cout &lt;&lt; data[i];<br />
      }</p>
<p>      cout &lt;&lt; endl;<br />
    }</p>
<p>};</p>
<p>int main()<br />
{</p>
<p>  char data[] = &quot;hello&quot;;<br />
  MyClass c1, c2(data);</p>
<p>  c1.display();<br />
  c2.display();</p>
<p>  c1 = c2;</p>
<p>  c1.display();<br />
  c2.display();</p>
<p>  return 0;</p>
<p>}<br />
[/code]
</p></div>
</div>
<hr />
<h3>Institute for Quantum Computing - Offer Accepted (Summer 2010)</h3>
<p>There was no interview for this position (Research Scholar), I just submitted by resume and a cover letter for a 2-week summer school program in Quantum Information Science. The position was also awarded with my acceptance into the summer school.</p>
<hr />
<h3>NASA Marshall Space Flight Center (Internship) - Declined Offer</h3>
<p>I had a few email correspondences with my potential boss and then we had a phone interview. I had already had some experience with Genetic Algorithms and this was specifically for doing some work in that area. He asked me some basic questions about GAs and my software development experience, nothing too serious. In the end I really wanted the position at IQC (above) so I declined this offer.</p>
<hr />
<h3>Amazon - No Offer</h3>
<p>I really can't remember this interview very much. They flew me out to Seattle and that's about all I remember! Here are the 2 questions I do remember:</p>
<p>Question 1: Given a clock with an hour and minute hand, find the degrees between the hands.</p>
<ul>
<li>This is a neat little problem. On the whiteboard I wrote out all the math for this problem but it all reduces to the code below.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;<br />
#include &lt;math.h&gt;</p>
<p>using namespace std;</p>
<p>int main()<br />
{</p>
<p>  // Constants for Time:<br />
  const int HOUR = 12,<br />
            MINUTE = 30; </p>
<p>  // Degree variables:<br />
  double hourDegrees = 0.0,<br />
         minuteDegrees = 0.0,<br />
         totalDegrees = 0.0;</p>
<p>  // Calculations:<br />
  hourDegrees = 0.5 * (60*HOUR + MINUTE);<br />
  minuteDegrees = 6*MINUTE;<br />
  totalDegrees = fabs(hourDegrees - minuteDegrees);<br />
  totalDegrees = fmin(totalDegrees, 360-totalDegrees);</p>
<p>  // Display result:<br />
  cout &lt;&lt; &quot;Time - &quot; &lt;&lt; HOUR &lt;&lt; &quot;:&quot; &lt;&lt; MINUTE &lt;&lt; endl;<br />
  cout &lt;&lt; &quot;Degrees between hands: &quot; &lt;&lt; totalDegrees &lt;&lt; endl;</p>
<p>  return 0;</p>
<p>}<br />
[/code]
</p></div>
</div>
<p>Question 2: How would you efficiently implement "Best Selling Items" on Amazon's main page?</p>
<ul>
<li>There was a lot of detail that went into this question since I tied like 3 different data structures together. I know that I had a Heap tied to a Binary Tree but other than that I don't remember what I did.</li>
</ul>
<hr />
<h3>Luna Innovations Incorporated - Accepted Offer (May 2011 - August 2012)</h3>
<p>Pretty easy interview overall, I was expecting something tougher. Only a few technical questions.</p>
<p>Question 1: What is a D Flip-flop and what is it used for?</p>
<ul>
<li>Data input and clock input that flips the data when a certain clock edge is encountered (high or low). Used as an elementary memory gate.</li>
</ul>
<p>Question 2: In a graph, what is the difference between a Hamiltonian Path and Hamiltonian Cycle?</p>
<ul>
<li>A Hamiltonian path is a path on a graph that touches every vertex only once. A Hamiltonian cycle is a Hamiltonian path that also creates a cycle.</li>
</ul>
<p>Question 3: Given an item and 2 iterators, write a function to tell if the item is contained between the two iterators.</p>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;<br />
#include &lt;vector&gt;</p>
<p>using namespace std;</p>
<p>template &lt;typename S, typename T&gt;<br />
T find(S data, T start, T end)<br />
{</p>
<p>  while (start != end)<br />
  {</p>
<p>    if (*start == data)<br />
    {<br />
      return start;<br />
    }   </p>
<p>    start++;</p>
<p>  }</p>
<p>  // Return end if not found:<br />
  return end;</p>
<p>};</p>
<p>int main()<br />
{</p>
<p>  // Data to find:<br />
  int findMe = 6;</p>
<p>  vector&lt;int&gt; myData;</p>
<p>  for (int i=0; i&lt;10; ++i)<br />
  {<br />
    myData.push_back(i);<br />
  }<br />
  auto iter = find(findMe, myData.begin(), myData.end());</p>
<p>  if (iter == myData.end())<br />
  {<br />
    cout &lt;&lt; &quot;Data not found!&quot; &lt;&lt; endl;<br />
  }<br />
  else<br />
  {<br />
    cout &lt;&lt; &quot;Data found!&quot; &lt;&lt; endl;<br />
  }</p>
<p>  return 0;</p>
<p>}<br />
[/code]
</p></div>
</div>
<hr />
<h3>Virginia Tech - Accepted Offer (August 2012 - May 2014)</h3>
<p>I did not know what to think going into this interview. I thought it was going to be somewhat technical but it turned out to not be technical at all. Just a lot of questions about working with people and projects I had worked on. I only had an onsite interview since they were looking locally.</p>
<hr />
<h3>Virginia Tech Transportation Institute - Declined Offer</h3>
<p>I had a phone interview where I was asked a lot of questions about my project background. I also had an onsite interview and was asked the same questions again basically. I only really got one technical question which is below.</p>
<p>Question 1: What is the difference between a Vector and a Linked List and when would you use one over the other?</p>
<ul>
<li>Vector: contiguous, better for smaller number of items so that items can be accessed quickly (especially with a prefetcher). If you have an index value, look-up is O(1) constant time.</li>
<li>Linked List: non-contiguous, better for large number of items that don't need to be contiguous. Access to items in the middle is slow since you have to traverse through the list to get to them.</li>
</ul>
<p>Question 2: What type of version control do you use?</p>
<ul>
<li>Git/Perforce/SVN/etc. I'm a pragmatic Software Engineer so I use whatever tool is best for the job. However, I do prefer Git over the others.</li>
</ul>
<p>Question 3: What collaborative tools do you use?</p>
<ul>
<li>Version Control (Git/Perforce/SVN/etc), Bug Tracking (Trac/BugZilla/GitHub Issues), Wikis (Confluence, Trac, GitHub), etc. Again, as above, I'm a pragmatic Software Engineer so I use whatever tool is best for the job so I'm always open to new tools and processes!</li>
</ul>
<hr />
<h3>Georgia Tech Research Institute - Accepted Offer (June 2014 - May 2015)</h3>
<p>I just had my interview with GTRI on March 31st, 2014. This was definitely the longest and most technical interview I have ever done and I think it went really well. I interviewed with about 8 people throughout the day and was asked a wide variety of questions. Here are most of them. </p>
<p>Question 1: Write a function that reverses a C-style character string.</p>
<ul>
<li>I could not for the life of me remember how to deal with c-style arrays when I was asked this question! Seriously, I felt embarrassed. It took me a few seconds to even realized how I should do it.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;cstring&gt;<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>void reverse(char* str)<br />
{<br />
  size_t size = strlen(str);<br />
  char temp = ' ';</p>
<p>  for(int i=0; i &lt; size/2; ++i)<br />
  {<br />
    temp = str[i];<br />
    str[i] = str[size-1-i];<br />
    str[size-1-i] = temp;<br />
  }<br />
}</p>
<p>int main()<br />
{</p>
<p>  char str[] = &quot;Hello&quot;;</p>
<p>  cout &lt;&lt; &quot;String: &quot; &lt;&lt; str &lt;&lt; endl;<br />
  reverse(str);<br />
  cout &lt;&lt; &quot;Reversed: &quot; &lt;&lt; str &lt;&lt; endl;</p>
<p>  return 0;<br />
}<br />
[/code]
</p></div>
</div>
<p>Question 2: What IDE do you use and why?</p>
<ul>
<li>Vim (when I said that the interviewer threw his hands in the air and said 'YES!', haha). I use it because I love Vim and it is the first IDE that I learned on. I'm not a Vim ninja but find it soothing to use and have started using it with tmux which is pretty sweet.</li>
</ul>
<p>Question 3: What is your primary programming language (compiled and interpreted) and why?</p>
<ul>
<li>C++ and Python/Bash. C++ because it was the first language I learned and because I reeeally like it. Python because I can easily create cross-platform scripts that do just about anything scripting I need. When I'm specifically on Linux and just a quick script, I usually write Bash scripts.</li>
</ul>
<p>Question 4: How do you swap the values of 2 integers in C++ without using any additional space?</p>
<ul>
<li>I have seen this question a hundred times on the internet and interview forums but could not for the life of me remember the order in which to do the operations. I remembered you needed to use the exclusive-or and 3 steps. Turns out it is just the variables swapped after each line like below.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>int main()<br />
{<br />
  int a = 5,<br />
      b = 10; </p>
<p>  cout &lt;&lt; &quot;Before swap: a=&quot; &lt;&lt; a &lt;&lt; &quot; b=&quot; &lt;&lt; b &lt;&lt; endl;</p>
<p>  // Using exclusive-or trick:<br />
  a ^= b;<br />
  b ^= a;<br />
  a ^= b;</p>
<p>  cout &lt;&lt; &quot;After swap : a=&quot; &lt;&lt; a &lt;&lt; &quot; b=&quot; &lt;&lt; b &lt;&lt; endl;</p>
<p>  return 0;<br />
}<br />
[/code]
</p></div>
</div>
<p>Question 5: What are some issues you could run into when using the Singleton Design Pattern in a concurrent environment?</p>
<ul>
<li>The Singleton Design Pattern is a design pattern that guarantees only a single instance of a class is ever created at once. In a concurrent environment, if the instantiation is not protected against multiple thread accesses, then the class could be instantiated multiple times. This immediately breaks the Singleton Design Pattern. To remedy this problem you have to use locks/CAS operations/other concurrent primitives around the instantiation factory to make sure only 1 instance is ever created at a time.</li>
</ul>
<p>Question 6: What are some important things to think about when writing a hash function?</p>
<ul>
<li>Speed and how good the hashing is (low key collisions). There is a balance between these two things but the most important of the 2 is speed since hashing is used in performance critical sections of software.</li>
</ul>
<p>Question 7: What functional programming concepts have you used in C++11?</p>
<ul>
<li>Lambda functions but not extensively.</li>
</ul>
<p>Question 8: What is a functor?</p>
<ul>
<li>Function object, which allows for the object to be called like a function.</li>
</ul>
<p>Question 9: When would you ever want/need to declare a variable volatile and const in C++?</p>
<ul>
<li>I didn't know this one and didn't have a good guess. The best answer (and really only one that makes sense) is when you are dealing with a register. The const makes it so that you cannot edit that value of the register in your program and the volatile means an external program might modify the value. This tells the compiler not to optimize the value outside of loops and any other areas it tries to optimize.</li>
</ul>
<p>Question 10: What are the two most important design decisions that went into engineering Linux?</p>
<ul>
<li>I had no idea about this one and the interviewer said it was kind of a bad question since it was purely subjective. He eventually said that his two favorite things are that everything in Linux is based on files (config files, system files, etc) and the ability to pipe commands together.</li>
</ul>
<p>Question 11: What is stored in a when this code is compiled?</p>
<p>[code language="cpp"]<br />
int main()<br />
{<br />
  int &amp;a; </p>
<p>  return 0;<br />
}<br />
[/code]</p>
<ul>
<li>At first I didn't really understand what was being asked of me. When I realized what it was, I was somewhat confused because I was pretty sure it was undefined behavior. Well, it's a trick question a little bit because you can't do it, the compiler won't let you. Which makes complete sense since it is a reference and it can't be defined without actually referencing anything.</li>
</ul>
<p>Question 12: What is the output of the following code?</p>
<p>[code language="cpp"]<br />
#include &lt;stdint.h&gt;<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>struct MyStruct<br />
{<br />
  uint16_t a;<br />
  uint8_t b;<br />
  uint64_t c;<br />
};</p>
<p>int main()<br />
{<br />
  cout &lt;&lt; &quot;Number of bytes: &quot; &lt;&lt; sizeof(MyStruct) &lt;&lt; endl;</p>
<p>  return 0;<br />
}<br />
[/code]</p>
<ul>
<li>This question seemed too straightforward to answer right out but I went ahead and said "I would be inclined to say 11 bytes but I assume that's not the one you want." This question is actually tricky and depends highly on the system you are compiling the code on and if you are potentially sending information between systems. This was what they wanted me to talk about I think. I talked briefly about optimizations that compilers could do that would pack the first 2 integers into the same integer. On the current system I am compiling the code on above (Chromebook with arm processor) I get an answer of 16 byes. Each int takes up a 32-bit int and the 64-bit one takes up 2. Therefore you get (64+32+32)/8=16 Bytes. Also, if you were sending this struct across a network and also using the output of sizeof to do processing (or just to keep track of packets), you could run into trouble. So the moral of the  story is understand that structs without padding can potentially try and optimize things in such a way that they could be different in different settings.</li>
</ul>
<p>Question 13: What is the difference between a struct and a class in C++?</p>
<ul>
<li>The only difference (besides the keywords themselves) is that a struct's members are public by default and in classes they are private by default.</li>
</ul>
<p>Question 14: Are there issues with this macro definition?</p>
<p>[code language="cpp"]<br />
#define MULT(a,b) a*b<br />
[/code]</p>
<ul>
<li>This takes some knowledge of the preprocessor and how #defines are inlined by the preprocessor. The preprocessor does a direct replacement of all occurrences of the macro in the file. The biggest issue with the above code is that the order of operations can get messed up since there are no parentheses around the arguments. The code below shows some examples of this. And to be completely correct, you should always encase the entire return value in parentheses as well, in case it is used in a more complicated expression.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;</p>
<p>// Original function:<br />
#define MULT(a,b) a*b</p>
<p>// Modified and correct for most cases:<br />
#define MULT2(a,b) (a)*(b)</p>
<p>// Modified again and technically the most correct:<br />
#define MULT3(a,b) ((a)*(b))</p>
<p>using namespace std;</p>
<p>int main()<br />
{</p>
<p>  cout &lt;&lt; &quot;MULT(3, 4) = &quot; &lt;&lt; MULT(3,4) &lt;&lt; &quot; - Correct!&quot; &lt;&lt; endl;<br />
  cout &lt;&lt; &quot;MULT(3+4, 2) = &quot; &lt;&lt; MULT(3+4,2) &lt;&lt; &quot; - Incorrect&quot; &lt;&lt; endl;<br />
  cout &lt;&lt; &quot;MULT2(3+4, 2) = &quot; &lt;&lt; MULT2(3+4,2) &lt;&lt; &quot; - Correct!&quot; &lt;&lt; endl;</p>
<p>  return 0;</p>
<p>}<br />
[/code]
</p></div>
</div>
<p>Question 15: What are some issues that you could run into when summing a large list of numbers? How would you solve these issues?</p>
<ul>
<li>If the orders of magnitudes are very different, then there will most likely be round off errors since adding numbers that are very different in magnitude tend to be hard for compilers and processors. To add numbers, the ALU shifts the numbers and that can cause parts of the number to be lost. Therefore, I would sort the list of items and sum them starting from the smallest element so that the orders of magnitudes are always similar.</li>
</ul>
<p>Question 15.b: What about if the list of numbers is all the same numbers?</p>
<ul>
<li>I had to think for a second to realize what to do in this situation. All you have to do is use a divide and conquer method and roll-up the values based on pair-wise sums of the elements. It's like the recombination step of Merge Sort, that way the magnitudes of the sums are always the same.</li>
</ul>
<p>Question 16: What is the virtual keyword used for in C++? Can you accomplish the same thing in C?</p>
<ul>
<li>The virtual keyword in C++ is used for inheritance and overriding of methods between Derived and Base classes. This way Derived classes can have more detailed/specific implementations of common methods.</li>
<li>I did not have an answer for the second part, I didn't even really know where to start. He said that you could if you were smart with function pointers but I can't exactly remember what he said. I also can't remember if he was talking about C or C++ cause he kept saying "most derived function" so I'm pretty sure he was jumping back and forth between C and C++ but I can't really remember...</li>
</ul>
<p>Question 17: In C++, how can you tell if the stack grows up or down?</p>
<ul>
<li>This was a toughie and apparently it is used by Google a lot these days for their interviews. I went through a few different answers dealing with volatile variables, memory barriers, and mutexes/locks. However, none of these guarantee that the compiler will order the locations sequentially, only that they keep program order. I knew I had to test the values of 2 different pointers to get the answer but I just didn't know where the first pointer should be created. Eventually he guided me to the only place I could do anything: the argument list. I'm still not entirely convinced that this works. He gave some reason why it does but I still think it is highly dependent on the system. I'm almost positive this will give undefined results on most systems and compilers.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="cpp"]<br />
#include &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p>void myFunc(int* a)<br />
{<br />
  int b = 1;</p>
<p>  if (a &lt; &amp;b)<br />
  {<br />
    cout &lt;&lt; &quot;The stack grows up!&quot; &lt;&lt; endl;<br />
  }<br />
  else<br />
  {<br />
    cout &lt;&lt; &quot;The stack grows down!&quot; &lt;&lt; endl;<br />
  }</p>
<p>}</p>
<p>int main()<br />
{</p>
<p>  int a = 1;</p>
<p>  myFunc(&amp;a);</p>
<p>  return 0;<br />
}<br />
[/code]
</p></div>
</div>
<p>Question 18: Given a graph, a start node, and a list of stop nodes, return a subgraph containing paths from the start node to the stop nodes.</p>
<ul>
<li>Not too hard of question if you understand graphs. All you do is this: starting at the start node, fan out to all connected edges to the neighbor nodes keeping track of the visited edges (and mark the edge as visited). If the node is a stop node then mark it as a stop node. Do this until you have reached all nodes. To get the subgraph, go through all the nodes and delete the ones that are not marked as stop nodes and the edges that are connected to them. You will then be left with a subgraph containing the paths from the start node to all the stop nodes.</li>
</ul>
<p>Question 19: Given a file containing a repeating sequence, how would you get this data out of the file? How about remove duplicates?</p>
<ul>
<li>This question is very similar to my IBM Question 3 above so I won't go into any of the details since it uses the same exact same mechanisms for the searching. However, the second part is a little more tricky. The first thing I said was I would pipe my grep results into awk and the interviewer immediately said "Okay, I'll give it to you. I said if you were going to use awk and not sed I'd just give it to you." I thought that was pretty funny! So I didn't have to do the implementation. And it's actually a good thing because I'm not sure I would have been able to come up with the answer. Here is a one-liner that I just came up with (I pulled the awk part from a forum). It first finds the occurrences, then removes the spaces, and then uses awk to create an array that keeps track of the input data. Therefore, if there are multiple lines that match, it will only show the first occurrence.</li>
</ul>
<div class="accordion">
<h6>Click for Code</h6>
<div>
[code language="shell"]<br />
$ grep -o '([0-9]\{3\})\s*[0-9]\{3\}\s*-\s*[0-9]\{4\}' filename | sed 's/ \+//g' | awk '!x[$0]++'<br />
[/code]
</div>
</div>
<p>Question 20: What do you use to do performance testing on your code?</p>
<ul>
<li>For basic timing, I use things like utime in Linux to get timing results. The resolution is pretty fine so I can get some decent rough results. In Python there are built in libraries that have millisecond-nanosecond resolution which is pretty awesome. In C++, I would use the new chrono library which has high resolution. I also use gperftools to profile CPU usage and valgrind to do memory performance.</li>
</ul>
<p>Question 21: What do you think of Travis-CI?</p>
<ul>
<li>Love it! I use it on all my new repos, keeps me honest with running my tests and keeping my build clean and healthy. I hope that it is enhanced to include multiple platforms eventually.</li>
</ul>
<hr />
<h3>Nexidia, Inc. - Accepted Offer (Starting March 2015)</h3>
<p>This job interview came out of left field for me. I wasn't looking for a new job but this just popped up and was a great fit so I applied! As I am writing this I am in my final week of being a Research Scientist at Georgia Tech Research Institute. I like it at GTRI, it's a good work environment but there are a number of small things that bother me. One of the biggest reasons is the security aspect of my job. I work mainly on classified DoD projects so I am locked away in a closed room all the time which, frankly, sucks. Also, software is always an after thought in the group I work in. Even when software is said to be the focus, it always suffers once crunch times comes along. </p>
<p>Anyways, I accepted the job at Nexidia as a Senior Software Engineer! I had an interesting interview process which consisted of 4 parts (not including recruiter talks). I will detail each part below.</p>
<p><u>Part 1: Pre-Screening Questions</u></p>
<p>This was just a set of questions sent by the recruiter that they then forwarded to Nexidia to make sure it was worth having a phone interview. I'll just copy/paste them here with my answers:</p>
<p>Question 1: Experience designing SDKs in C++?</p>
<ul>
<li>I have designed and engineered C++ Template libraries that provide efficient and simple APIs to interface with. I have extensive experience in both writing libraries and the applications to interface with the libraries.
  </li>
</ul>
<p>Question 2: Cross-platform experience (Linux & Windows most important)?</p>
<ul>
<li>Cross-platform development is very important to me. I have developed applications on Windows and Linux and with the coming of the new(ish) standardizations of C++, I can now accomplish this task much easier in the C++ realm. I use the newest standard (C++14) in my projects to compile against and do continuous integration and nightly regression testing across multiple compilers (GCC, clang, MSVC) and also across multiple platforms (Windows 7, Ubuntu 14.04 LTS, Mac OS X Yosemite).
  </li>
<li>On all of my C++ projects I also use CMake as my build system setup. This provides extreme flexibility and lets me easily compile my projects on multiple platforms.
  </li>
<li>As for scripting. I use Python exclusively these days since it is readily available (or can be easily gotten) on most systems. It provides a scripting language that can be used across all systems that support it. I love having a one-step build process so I always have a top-level python script that will take care of doing everything you need: creating new out-of-source build folder, running CMake, running whatever generator CMake created (typically Make for me), then running the compilation process (make, make check), then other items (make doc [doxygen]), and then finally doing the install. This allows for a one way entry into the code base by having the entire process encapsulated and makes it super simple to do nightly, continuous, and regression testing.
  </li>
</ul>
<p>Question 3: Experience with gcc + gdb?</p>
<ul>
<li>GCC is my main C++ compiler at the moment. We are using 4.9.2 and plan to upgrade to 5.0 when it is released (which provides more C++17 support). I am very familiar with using GCC, its compiler flags, and also using/comparing it against other compilers (clang, MSVC, etc). I personally hope that they catch up with Clang in pretty print error messages and template errors which they are promising for 5.0!
  </li>
<li>I almost exclusively use GDB to do all of my debugging currently. I use Vim so I have a tight development integration between the GDB CLI, Vim, and CMake so that I can quickly step through code and track down issues.
  </li>
<li>On a similar note, I am also very fond of static and dynamic analysis tools (Clang Static Analyzer, Valgrind etc). These type of tools are vital to creating efficient and correct programs and I have them integrated into my testing tool chain when need be.
  </li>
</ul>
<p>Question 4: Experience working with scientific computing applications?</p>
<ul>
<li>I consider myself a Scientific Software Engineer. I have always been interested in physics, mathematics, chemistry, etc and have built my career around providing solid software engineering skills to the scientific world. I have worked along side physicists (quantum computing, astrophysics), mathematicians (abstract algebra, number theory), and engineers (FPGA analysis) and have tried to streamline their processes by introducing tools that will increase productivity (source code versioning [git], Wikis, bug tracking, etc) and also contribute to research along the way by developing new methods and/or providing algorithmic speedups.
  </li>
</ul>
<p>Question 5: Single process concurrency experience in C++?</p>
<ul>
<li>One of the first things I think about when sitting down to design a new C++ app/library is if I can exploit concurrency and/or parallelism. If you have something that is embarrassingly parallel, why waste computation time by not parallelizing it? I have previously used third-party libraries such as OpenMP to accomplish concurrent designs because it is feature rich and less of a nightmare than coding pthreads by hand. However, lately, since I am using C++11/14, I have been using the new Standard Threads since it is mandated by the standard and any compiler that supports it should work fine. There is less tuning at this level but it is still a great solution that does not require a third-party library dependency. For parallelism, I have used MPI for communications between multiple node setups.
  </li>
</ul>
<p>Question 6: Experience with STL?</p>
<ul>
<li>I use STL on a daily basis for my C++ projects. This includes the typical template containers (vectors, maps, unordered_maps, etc) and also the extremely handy algorithms which are based on the iterator design pattern (among others). I also extensively use the Boost library which is historically the sandbox for new Standard C++ features (Boost Graph, File System, SmartPointers [before they became part of the standard], etc). STL is a vital part of my C++ development, especially in terms of not reinventing the wheel.
  </li>
</ul>
<p><u>Part 2: Phone Interview</u></p>
<p>I didn't know what to expect when I had this interview. The job was for a Senior position which I had never done before. I enjoyed it and I think the questions gauged my basic understanding of C++ and multithreading programming. In the end, the interviewer immediately set me up for the coding assignment so I think it went well.</p>
<p>Question 1: What are the differences/similarities between threads and processes on Windows and Linux?</p>
<ul>
<li>This was a good question that I didn't have a good, complete answer to. I am not that familiar with threads/processes on Windows so I didn't have an answer for that half. However, on Linux, threads and processes are similar. Threads have less overhead than processes so spinning them up takes less time. Threads share the same memory space so one has to take special care when modifying shared memory spaces. Processes on linux can have shared memory but by default that is not the case. Processes have their own ID and have their own system handlers. There are other differences but those are about the only ones that I came up with.</li>
</ul>
<p>Question 2: What is the difference between an interface and an abstract base class?</p>
<ul>
<li>Interfaces contain no implementation details at all whereas abstract base classes <em>can</em> contain implementation details. In C++, interfaces are created by making all functions pure virtual and having no member variables. I had to point out that in C++, interfaces are just an idea, not an actual keyword like they are in Java.</li>
</ul>
<p>Question 3: Given a directory with 50,000 html files on Linux, how would you find all occurrences of a single item (ex: phone number, name etc)?</p>
<ul>
<li>My knee jerk answer was use grep. However, he quickly said "What happens with the expansion of '*' with grep?" I didn't think about it initially but on some versions of linux, there is a limit to the size of the command line, usually like 4K characters or so. So, you can't easily search with grep for that many files. At this point, I blew right past using find (?!) and said that I would write a quick python script to search all files. He quickly said "...which is what find does." Ha, it sure is! However, something I didn't point out at the time was that my solution is cross-platform and using find is not.</li>
</ul>
<p>Question 4: When writing cross-platform C++, what are some issues that you would come across and how would you deal with them?</p>
<ul>
<li>
  There are many things to think about when writing cross-platform C++. These are the ones I came up with:</p>
<ul>
<li>32-bit vs. 64-bit: use standard int variables, not int: uint32_t, int64_t, size_t, etc. Non-standard types can be different sizes on different architectures.</li>
<li>Endian-ness: Little/big endian can be an issue when going between systems, especially over networks. If serializing objects, writing out primitives should be done in a manner so that reading them back in won't be ambiguous because of endian-ness.</li>
<li>strings: normal vs wide character widths. Windows default is wchar_t whereas linux is char_t. Solution to this is most likely to use Unicode everywhere, although I have not really ran into this issue before so I wasn't sure about how to solve it universally.</li>
</ul>
</li>
</ul>
<p>Question 5: In OpenMP, how do you deal with IO in parallelized blocks of code?</p>
<ul>
<li>I couldn't remember the actual command to serialize commands but I said use some sort of mutex to wrap around what you want to protect or something else that provides a memory barrier. This is indeed correct but the command is called a "synchronize" block, I had just forgotten it.</li>
</ul>
<p>Question 6: What C++ compilers have you used?</p>
<ul>
<li>GCC, Clang, MSVC, MinGW.</li>
</ul>
<p>Question 7: What debuggers/profilers have you used?</p>
<ul>
<li>GDB for debugging. Valgrind for memory tests although it's hard to use Valgrind all the time, especially on memory intensive applications since Valgrind runs your code in a VM. Distilling your application down to manageable memory test cases is not an easy thing to do so running Valgrind constantly just isn't practical. I have also used things like Google's tcmalloc to speed up and test memory allocations and also cppcheck to do static code analysis.</li>
</ul>
<p>Question 8: What IDEs have you used?</p>
<ul>
<li>I use VIM on a daily basis. Have some familiarity with Eclipse and Visual Studio too.</li>
</ul>
<p>Question 9: What Linux distros have you used?</p>
<ul>
<li>Ubuntu and Debian mostly. Some RedHat.</li>
</ul>
<p>Question 10: Are you familiar with design patterns? If so, what kinds and how do you use them?</p>
<ul>
<li>Some design patterns I use: Singleton class, Visitor pattern, and Iterator pattern. I use the Visitor pattern on all data structures, especially graphs. It allows me to separate the data structure from the algorithms. The same goes for the iterator pattern which STL uses heavily. I don't use the Singleton class much but it is useful for certain scenarios.</li>
</ul>
<p>Question 11: What does making a member function const in C++ mean? What restrictions are imposed?</p>
<ul>
<li>Const member functions can only be called on const objects and cannot modify member variables. Another restriction that I had forgotten about is that they can only call other const member functions. Also, something that I should have said but forgot (and the interviewer didn't catch it either): the statement about "cannot modify any member variables" is actually not correct. Const functions can modify mutable member variables although it is usually frowned upon.</li>
</ul>
<p>Question 12: Why are you leaving your current job?</p>
<ul>
<li>Tired of working on DoD projects and don't like being in classified settings.</li>
</ul>
<p><u>Part 3: Coding Assignment</u></p>
<p>The coding assignment was a pretty basic problem but the devil is always in the details. I was given 24 hours to complete it and it was basically this: "Given a list of integers in a file, write a C++ command line application that reads in the file and prints out the prime factors of each number. Write unit tests, use Visual Studio, and provide a solution that you feel is production quality."</p>
<p>I hadn't used VS in about 5 years so that was fun. I downloaded VS 2013 and used their native code unit test framework. I won't go into details about it here but I have a repo with the code in it: <a href="https://github.com/calebwherry/prime-factors" target="_blank">Prime Factors</a>. I also have continuous integration setup for it on <a href="https://travis-ci.org/calebwherry/prime-factors" target="_blank">Travis-CI</a> (I used my CMake + Python build system to run this on Travis-CI's linux systems, not the VS project files). I testing on Windows 7, Ubuntu 14.04, Debian Wheezy, and Mac OSX Mavericks using GCC 4.9, MSVC, and Clang (and CMake 3 and Python 3).</p>
<p><u>Part 4: On-site Interview</u></p>
<p>For the on-site interview, I had the same feeling I had going into the phone interview: I didn't really know what ti expect. It was actually really laid back and I enjoyed it very much! I had 4 sessions each with 2 people (except the last one who was just the Senior VP of Software Engineering). Each session is below:</p>
<p>- <em><u>Session 1:</u></em></p>
<p>I really enjoyed this session! The two men that interviewed me were great and asked me a lot of good questions. I feel like we really clicked and it was a great start to the day.</p>
<p>Question 1: How many bits does the type long have in C++? Does it ever change?</p>
<ul>
<li>The number of bits the variable long has depends on the architecture. On a 32-bit OS, I would assume that long is 32-bits. However, this is typically a bad assumption and we should use the standard types like size_t, uint32_t, and others instead of int, long, etc. That way we are guaranteed the size of the variable.</li>
</ul>
<p>Question 2: You reviewed a concurrency book on your blog, what was your take away from it?</p>
<ul>
<li>I liked the book. It was part of the Multiprocessor class I took at VaTech and I loved learning about the low level aspects of cache coherence and lock free algorithms and data structures.</li>
</ul>
<p>Question 3: What are your thoughts on the new C++ threading model?</p>
<ul>
<li>I love that the standard is finally including these in the language. However, everything is still somewhat primitive in my mind. For example, without a solid library/implementation for Thread Pools, bringing up and down threads is expensive. I did a few benchmarks for Concurrent GAs and lost all speedup because of the overhead of creating/destroying threads. More utility libraries need to be created that make working with threads with performance in mind.</li>
</ul>
<p>Question 4: Explain the Linux boot process in as much detail as you can.</p>
<ul>
<li>...</li>
</ul>
<p>Question 5: Say I am a C programmer but I really like C++ classes. What parts of a C++ class can I implement in C? How would you go about implementing those?</p>
<ul>
<li>...</li>
</ul>
<p>Question 6: What can you tell me about Linux inode?</p>
<ul>
<li>Nothing.</li>
</ul>
<p>Question 7: What is the difference between a system level call and a standard C library call?</p>
<ul>
<li>...</li>
</ul>
<p>- <em><u>Session 2:</u></em></p>
<p>This session was also fun. One of the guys was the main tester for the C++ libraries I would developing on so he asked some really cool testing questions that I had never been asked before.</p>
<p>Question 1: Given a coke machine, what types of tests would you perform so that it could be shipped to customers?</p>
<ul>
<li>...</li>
</ul>
<p>Question 2: What is a good interview question and why?</p>
<ul>
<li>...</li>
</ul>
<p>Question 3: How do you feel about const-ness in C++? Specifically the mentality of casting away object's cont-ness?</p>
<ul>
<li>...</li>
</ul>
<p>Question 4: What are your thoughts on C++ memory allocation on the stack versus the heap?</p>
<ul>
<li>...</li>
</ul>
<p>Question 5: Given a game of tic-tac-toe and the current state of the board, how would you go about testing if there was a winner or not?</p>
<ul>
<li>...</li>
</ul>
<p>Question 6: What are you thoughts on Python3?</p>
<ul>
<li>...</li>
</ul>
<p>Question 7: What do you do when you aren't working?</p>
<ul>
<li>...</li>
</ul>
<p>- <em><u>Session 3:</u></em></p>
<p>This session was super laid-back and involved me talking most of the time. It was with the head of the R&D department, one of their researchers, and the man who interviewed me on the phone. They were mostly interested in hearing about my research ideas and how I fit software into that.</p>
<p>Question 1: What is your experience with profiling tools? Valgrind, Intel VTune, etc?</p>
<ul>
<li>...</li>
</ul>
<p>- <em><u>Session 4:</u></em></p>
<p>Last session of the half day was with the Senior Vice President of Software Engineering. He was super nice and we had a good chat. Towards the end he asked me some general questions that I thought were very good and made for some good discussion.</p>
<p>Question 1: What is your experience in designing APIs?</p>
<ul>
<li>...</li>
</ul>
<p>Question 2: What are your thoughts about refactoring?</p>
<ul>
<li>...</li>
</ul>
<p>Question 3: What are your thoughts about optimizing code?</p>
<ul>
<li>...</li>
</ul>
