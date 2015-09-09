---
layout: post
title: Choosing a CSS grid system
modified:
categories: posts
description:
tags: [CSS, HTML]
image:
  feature:
  credit:
  creditlink:
comments:
share:
date: 2015-09-09T23:51:30+12:00
---

So what is a grid in terms of a web page? And what good is it? Simply put a grid system is a structure of columns and rows used to arrange content. The grid systems have been used for a long time in print, so why don’t use it in web design as well? In fact, for the last few years (since we despensed with tables for formatting) we've been busy twisting CSS to create grid frameworks.

The advantage of using a grid system is that it allows us to achieve great consistency. This results in a flexible sytem that allows your page to be more readable, easy to navigate and brings great support for creating a website that fits all devices. At [WebKea](http://webkea.co.nz) we're quite passionate about responsive design and mobile-first attention.

A grid system is not just advantageous when you code your page, but also it helps to architect your design in the early stages when you want to show your idea to your clients.

For several project I’ve used one of the most popular framework out there: Zurb Foundation which was released as open-source in 2012. Another popular grid system is Bootstrap, originally named Twitter Blueprint, released in 2011. As you may guess it was architected by some Twitter developers to document and share common design patterns and assets within the company.

![image]({{ site.url }}/images/grids.jpg)

<small>An example of how valuable grids have become to layouts.</small>

After using Foundation for sometime, I felt like I wanted a little bit more freedom and control. After some research I found a lighter grid system called [Jeet](http://jeet.gs/). As the developers describe it, it is a grid system for humans. But what enticed me to use it, was the fact that Jeet isn’t using the rigid twelve column rules. It allows to create your own columns using pixel, ems or percentage. I also love the idea of writting my custom grids right in the css on any selector I desire rather than having to add to pre-defined classes to my HTML(the current method of Foundation and Bootstrap).

Let's take a look at how I might have approached a 3 column grid in Foudation:

{% highlight html %}
<div class='columns medium-4'>lorem ipsum content...</div>
<div class='columns medium-4'>lorem ipsum content...</div>
<div class='columns medium-4'>lorem ipsum content...</div>
{% endhighlight %}

and the difference with jeet being, I can design my own layout system as classes as needed in my CSS:

{% highlight css %}
.col-action-3 {
  @include column(1/3);
  @include breakpoint($small-max) {
    @include stack();
    margin-bottom: 1rem;
  }
}
{% endhighlight %}

You might notice I'm also in-lining media queireis here with the sass plugin Breakpoint, but that is best left for another post.  In the meanwhile, have a look at [wikipedia](http://en.wikipedia.org/wiki/CSS_frameworks) for a comprehensive list of all CSS grid frameworks.
