---
layout: post
title: "Accessibility of web site"
date: 2016-08-26 14:45:05
image: '/assets/img/images/2016-08-27-accessibility-of-web-site'
description: "This page will introduce the accessibility feather of web site"
main-class: 'other'
color: '#7D669E'
tags:
- other
categories:
twitter_text:
introduction: "Web accessibility"
---
## Introduction to accessibility
Accessibility is one of the important feathers of web design. For most of us, it's really hard to recognise why we need to include this feather when we build a site. But as W3C says,  `'access to information and communications technologies, including the Web, as a basic human right'`.

Make our web site accessible provide the convenience for these situations:

- Accessibility supports social inclusion for people with **disabilities as well as others**, such as older people, people in rural areas, and people in developing countries.
- **There is also a strong business case for accessibility**. Accessibility overlaps with other best practices such as mobile web design, device independence, multi-modal interaction, usability, design for older users, and search engine optimization (SEO). Case studies show that accessible websites have better search results, reduced maintenance costs, and increased audience reach, among other benefits. Developing a Web Accessibility Business Case for Your Organization details the social, technical, financial, and legal benefits of web accessibility.

## How to test accessibility

- The best way to test accessibility is `Human Testing (使用者测试)`, that is to invite blind person to test the site.
- Manual Testing with Screen Reader.
  [NVDA](http://www.nvaccess.org/) or [JAWS](http://www.freedomscientific.com/Products/Blindness/JAWS)
- Code Review (编码检查)
  - WAVE. which is a chrome extension. search `WAVE Evaluation Tool` for it.

## Criteria of accessibility

 Here we will introduce the judging criteria of accessibility put forward by Hong Kong government. The criteria has two different levels, called Silver Criteria and Gold Criteria. The Former one consist of 13 judging criteria, used as a basic requirement of accessibility. While the latter one is more strict, which has another 11 criteria besides the former 13.
 We will mainly introduce the silver criteria.

- `W01.	Provide meaningful text alternative for non-text contents.<br>`
  Non-text contents, such as icons, photos, pictures, images, banners and maps, should have a text alternative.
  {% highlight html %}
  <!-- For element <img>, add 'alt' attribute -->
  <img src="/i/eg_tulip.jpg"  alt="Flower"/>
  <!-- For element <icon> or <i>, add 'title' attribute -->
  <i class="fa fa-car" aria-hidden="true" title="Time to destination by car"></i>
  {% endhighlight %}
  ***
- `W02.	Provide accessible Flash/Animated contents or allow to skip`
  Provide accessible Flash/Animated content or allow skip function.
  Sometimes, flash content blocks the user from getting to main content. Under this situation, when we use a flash/animate, we should include accessible “Skip” option allow user to skip Flash content.
  ![skip of flash](/assets/img/images/2016-08-27-accessibility-of-web-site/skip of flash.jpg)

  ***
- `W03.	Allow to perform all operations through a keyboard interface`
  When we provide an 'onClick' to a button or image or other elements, we should also provide an 'onkeypress'  and 'tabindex' (tab switch) attributes as well.
  ![skip of flash](/assets/img/images/2016-08-27-accessibility-of-web-site/keyboard press.jpg)
  {% highlight html %}
  <img src="example.gif" alt="example" onClick="run();" onkeypress="run();" tabindex="1">
  {% endhighlight %}
  In this example. 'onkeypress' will reply to keyboard press, and 'tabindex' signs the index of tab switch.

  ***
- `W04.	Easy to turn off background sound or set as user-initiated only`
  If any audio on a webpage plays automatically for more than 3 seconds, either a function is available to pause or stop the audio, or a function is available to control audio volume independently for that specific audio.
  ![Background sound](/assets/img/images/2016-08-27-accessibility-of-web-site/background sound.jpg)
  ![Background sound2](/assets/img/images/2016-08-27-accessibility-of-web-site/background sound2.jpg)

  ***
- `W05.	Provide means to close popup windows`
  If there is a popup window, a close button shall be included to allow closing the popup window through keyboard interfaces.
  ![Popup window](/assets/img/images/2016-08-27-accessibility-of-web-site/popup  window.png)
  (From [www.gov.hk](www.gov.hk))

  ***
- `W06.	Provide clear and informative links`
  If there is a link, either the link text alone or the text preceding the link is clear and meaningful in order to help users navigate.
  ![links](/assets/img/images/2016-08-27-accessibility-of-web-site/links.jpg)

  ***
- `W07.	Provide accurate and appropriate headings/labels`
  To help users understand what information is contained in the webpage and how information is organized, use clear and appropriate headings and labels to describe a topic or purpose.
  ![headers and labels](/assets/img/images/2016-08-27-accessibility-of-web-site/headers and labels.jpg)

  ***
- `W08.	Make website content easy to be used with assistive technologies`
  Use heading mark-up (`h1..h6`) to identify headings in the content. Heading mark-up allows assistive technologies to present the heading status of text to users.
  ![heading makeup](/assets/img/images/2016-08-27-accessibility-of-web-site/heading makeup.jpg)  
  ![heading makeup2](/assets/img/images/2016-08-27-accessibility-of-web-site/heading makeup2.jpg)

  ***
- `W09.	Make website structure in a consistent navigation mechanism`
  Navigational mechanism should be consistent
  ![consistent navigation](/assets/img/images/2016-08-27-accessibility-of-web-site/consistent navigation.jpg)

  ***
- `W10.	Make website content in meaningful sequence`
  - If webpage content needs to be read in a certain order to make sense, webpage shall be written/coded in a way which indicates this order
  - Webpage, especially web form, shall be coded in a logical manner when read by assistive technologies.
  ![read sequence](/assets/img/images/2016-08-27-accessibility-of-web-site/read sequence.jpg)
  ![read sequence2](/assets/img/images/2016-08-27-accessibility-of-web-site/read sequence2.jpg)

  ***
- `W11.	Provide input assistance such as proper labels for user input and error identification and description etc.`
  - If an input error is automatically detected, the error shall be identified and described to users.
  - Labels or instructions are provided when prompting user input.
  ![input error](/assets/img/images/2016-08-27-accessibility-of-web-site/input error.jpg)

  ***
- `W12.	Text can be resized up to 200 percent without loss of content`
  Text resize is necessary, and correct.
  ![font resize](/assets/img/images/2016-08-27-accessibility-of-web-site/font resize.jpg)

  ***
- `W13.	Provide an accessibility statement with contact points for the website`
  Provide an accessibility statement with contact points for users when they encounter accessibility problems
  ![accessibility statement](/assets/img/images/2016-08-27-accessibility-of-web-site/accessibility statement.jpg)

  ## Reference
  - [W3C accessibility standard](https://www.w3.org/standards/webdesign/accessibility)
  - [W3C Web Content Accessibility Guidelines (WCAG) 2.0](https://www.w3.org/TR/WCAG20/#visual-audio-contrast)
  - [W3C accessibility standard](https://www.w3.org/standards/webdesign/accessibility)
