---
layout: post
title: JQuery & New Website Widgets
date: 2014-01-12
status: publish
comments: true
share: true
categories:
- Programming
- Technology
tags:
- CSS
- JQuery
- WebDev
image:
  feature: main-banner-2.jpg
---

Recently at work I was tasked with using JavaScript to enhance some of our Workflow/forms that we have created using <a href="http://www.ellucian.com/workflow-management-software/" target="_blank">Ellucian's Banner Workflow</a>.

Instead of going down the old school route of writing pure JavaScript, I went with using the <a href="http://jquery.com/" target="_blank">JQuery</a> and <a href="http://jqueryui.com/" target="_blank">JQuery-UI</a> libraries. Going into it all I really didn't know much about JQuery, AJAX, or JavaScript. But in a short amount of time, I have been able to accomplish quite a bit of work with very little effort. Here are just a few easy steps to get you set up and running using JQuery and JQuery-UI to make some cool enhancements to your site!

First, you need to link against the JQuery libraries. There are 2 main ways to do this: link against them from the JQuery website OR download them and link against them locally. I think the best option is to download and host them yourself. This makes modifications easy (if needed) and in case the developers of JQuery decide to modify what they host online, you don't get screwed (hopefully this should never happen but you never know). Also, you are relying on their website to be up all the time and sometimes this is not a good thing to rely on. So, host your own! Below is how to link against the JQuery library (I have all my scripts under a "libs" folder):

{% highlight html linenos %}
<script type="text/javascript" src="/libs/jquery/jquery-1.9.1.js"></script>
{% endhighlight %}

Another library that is extremely useful is the JQuery-UI libraries. They provide a ton of useful widgets and styles to use on your website. If you download them locally you can link against them as you see below. I have also shown a custom style sheet that can be used:

{% highlight html linenos %}
<link rel="stylesheet" href="/libs/jquery-ui-1.10.3/css/smoothness/jquery-ui-1.10.3.custom.min.css" />
<script type="text/javascript" src="/libs/jquery-ui-1.10.3/js/jquery-1.9.1.js"></script>
<script type="text/javascript" src="/libs/jquery-ui-1.10.3/js/jquery-ui-1.10.3.custom.min.js"></script>
{% endhighlight %}

Note: when you download the JQuery-UI libraries, you also get a version of the JQuery libraries.

The last script that I include here contains all the custom JavaScript/JQuery code that I write myself:

{% highlight html linenos %}
<script type="text/javascript" src="/libs/jcw-custom.js"></script>
{% endhighlight %}

All of these linkings are usually put in the head tag of the html document like so:

{% highlight html linenos %}
<html>
<head>
<title>Test Page</title>

<!-- JQuery Items -->
<link rel="stylesheet" href="/libs/jquery-ui-1.10.3/css/smoothness/jquery-ui-1.10.3.custom.min.css" />
<script type="text/javascript" src="/libs/jquery-ui-1.10.3/js/jquery-1.9.1.js"></script>
<script type="text/javascript" src="/libs/jquery-ui-1.10.3/js/jquery-ui-1.10.3.custom.min.js"></script>
<script type="text/javascript" src="/libs/jcw-custom.js"></script>

</head>
<body>
Some awesome content goes here.
</body>
</html>
{% endhighlight %}

And now we can use our awesome new libraries! For this example, we are going to have a bunch of different html h2 tags that separate sections of content on a webpage (I used to do this for my research page). However, now we want to put all that content into an accordion widget so that all the content is not visible at once. Let's set up the html first. Here is some example html for the content:

{% highlight html linenos %}
<h2>Section 1</h2>
  <div>Some content.</div>

<h2>Section 2</h2>
  <div>Some more content.</div>

<h2>Section 3</h2>
  <div>Even more content.</div>
{% endhighlight %}

Here is a <a href="http://jsfiddle.net/4fD5r/" target="_blank">JSFiddle</a> of the above html. We will begin to build this JSFiddle as we add more code.

To make this content an accordion, wrap the whole thing in a div tag with an accordion id:

{% highlight html linenos %}
<div id="accordion">
<h2>Section 1</h2>
  <div>Some content.</div>
<h2>Section 2</h2>
  <div>Some more content.</div>
<h2>Section 3</h2>
  <div>Even more content.</div>
</div>
{% endhighlight %}

<a href="http://jsfiddle.net/4fD5r/1/" target="_blank">Updated JSFiddle</a>. Now that we have the html, all we need to do is write the JQuery code and put it in our custom JS file. Here is the code that we will use:

{% highlight js linenos %}
$(document).ready(function() {
  $("#accordion").accordion({
    collapsible: true,
    heightStyle: "content"
  });
});
{% endhighlight %}

And the <a href="http://jsfiddle.net/4fD5r/2/" target="_blank">updated fiddle</a> for that. I have added in a few configuration details for how I like my accordions to behave. Some people like their accordions to have a static height but I like mine to match the content.

But why isn't the content shown in an accordion now? That is because we have not yet specified a JS library to use! On the left-hand side of the JSFiddle, you can select which libraries you want to use. Let's pick the libraries we have listed above and see what happens!

Bam, the <a href="http://jsfiddle.net/4fD5r/3/" target="_blank">new JSFiddle</a>! And it works nicely! What is going on here is that after the <a href="http://en.wikipedia.org/wiki/Document_Object_Model" target="_blank">DOM</a> (Document Object Model) is fully loaded, the JQuery gets executed (read up on the $(document).ready() function). All of the elements with the id "accordion" will get turned into an accordion widget ("#' here means id, "." would mean class). Since ids are supposed to be unique, this will only apply to one element in our case. However, we could have easily used a wildcard attribute selector to search ids to match multiple elements or use a class attribute on multiple elements.

And just to throw in some CSS, if you wanted to change any of the CSS properties of the accordion then you can easily do it like so:

{% highlight css linenos %}
#accordion {
  font-weight: bold;
  background-color: Red;
}
{% endhighlight %}

And the last <a href="http://jsfiddle.net/4fD5r/6/" target="_blank">updated JSFiddle</a>!

That's about it! There are lots of awesome things that can be done with JQuery and this is just a very very basic intro. I have been able to do some cool stuff at work with it and am looking forward to working with it more!
