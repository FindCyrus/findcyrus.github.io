---
layout: post
title: "Basic CSS Styles #1"
date: 2016-09-09 14:25:54
image: '/assets/img/'
description: 'List basic css attributes classified by html element'
main-class: 'css'
color:
tags:
- css
categories:
- CSS foundation
twitter_text:
introduction: 'For each html element, list as much as css attributes that would be used'
---

## 1. Font

There are several widely used styles for font.

{% highlight css %}
  font-family: FSElliotPro;
  font-size:  13rem;
  font-weight: 400;
  color: black;
  letter-spacing: 0.5px;
  font-style: normal;
  line-height: 2;
  text-transform: uppercase;
{% endhighlight %}
Details:

- font-family<br>
  Visit [this site](http://www.cssfontstack.com/) for font stack.
- font-size<br>
  When talking about font-size, the diff between unit px, rem, rm is really confusing. I will use another post to introduce the diff between this three unit.
- font-weight<br>
  The font-weight property sets how thick or thin characters in text should be displayed.
  There are two kinds of value we can use.
    - normal \| bold \| bolder \| lighter
    - 100 \| 200 \| …… \| 900
- text-transform:
  - capitalize: transform the first character of `each` word to uppercase
  - uppercase
  - lowercase

## 2. Background

{% highlight css %}
  background: $white url('../images/wl-newsletter-bg.png') no-repeat right center;
  background-size: cover; // let the background img covers the whole component
  float: left; // will make all component lay on left side one by one
  width: 100%;
{% endhighlight %}

**2.1 background = background-color background-image background-repeat background-position**

2.2 background-position

 - right center
 - percentage: 50% 50%
 - length: 100px 100px

2.3 background-size

 - length: 100px 100px \| 100px
 - percentage: 50% 50%
 - cover (set the image to the container's max size)
 - contain (set the image to its max size)

## 3. ?
