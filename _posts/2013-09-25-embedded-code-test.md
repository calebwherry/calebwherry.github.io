---
layout: post
title: Embedded Code Test
date: 2013-09-25
status: publish
comments: true
share: true
categories:
- Programming
tags: []
image:
  feature: main-banner-2.jpg
---

I just installed a new plugin for embedding code into my posts. I had to do some edits to my custom Wordpress theme so here goes nothing:

{% highlight cpp linenos %}
// Here are some comments.
// They are pretty awesome, right?
// And some nice whitespace above, let's see how that comes out.
// Also, what about a reeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaallly long line.
// Alright, looks good. Let's do some syntax highlighting, should be C++ since I used the cpp tags...
namespace matrix {
  class Matrix {
    private:
      int rowSize;
      int colSize;
    public:
      Matrix(): rowSize(0), colSize(0)
      {
         // Do some stuff...
      }
      int getRowSize() { return rowSize; };
      int getColSize() { return colSize; };
      virtual ~Matrix();
  };
} // End matrix namespace
{% endhighlight %}

And that about sums it up! Looks pretty good I think. I highlighted lines 9, 23, and 24 which is neat. On ChromeOS, as I add more and more lines, there is some weird offset that gets worse and worse SO that after about 30 lines, the numbering is off by a whole line. Might work on that at some point but not now.
