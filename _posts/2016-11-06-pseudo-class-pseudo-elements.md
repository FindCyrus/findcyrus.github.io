---
layout: post
title: "pseudo-class and pseudo-elements"
date: 2016-11-05 16:07:08
image: '/assets/img/'
description:
main-class: 'css'
tags:
- css
categories:
introduction: 'An introduction to pseudo-class and pseudo-elements'
---

## 1. Pseudo-class (伪类)

Pseudo-classes select regular elements but under certain conditions, like when their position relative to siblings or when they’re under a particular state.

### 1.1 Different kind of pseudo-class
- Dynamic pseudo-classes
  - a:link
  - a:visited
  - a:hover
  - a:active
- UI element states pseudo-classes
  - :enabled    //like btn
  - :disabled   //like btn
  - :checked    //checkbox or radio
- Structural pseudo-classes
  - :first-child
  - :last-child
  - :nth-child(n)
  - :nth-last-child(n)
  - :only-child
  - :first-of-type
  - :last-of-type
  - :nth-of-type(n)
  - :nth-last-of-type(n)
  - :only-of-type
  - :empty  //Selects elements which contain no text and no child elements.
- Other pseudo-classes
  - :not(x)   //e.g. ':not(:checked)'

### 1.2 Different between nth-child(n) && nth-of-type(n)
During our last project, we never use styles like nth-of-type. When we want to set styles to some children, we will choose :nth-child. But after some research on these two types, I find we'd better choose the second type ('type') instead of 'child'.

The Difference is : <br>
p:nth-child(1) will set styles to the 1st child of p's container, and it type `must be p`.  `If the 1st child is not of type p, no one will be affected.`<br>
p:nth-of-type(1) will set styles to the 1st p child element of p's container.

For example:

<div class="pseudo-nth">
   <span>Test 1</span>
   <p>Test 2</p>
   <p>Test 3</p>
   <p>Test 4</p>
 </div>

```html
<div class="pseudo-nth">
   <span>Test 1</span>
   <p>Test 2</p>
   <p>Test 3</p>
   <p>Test 4</p>
 </div>
```
And styles are

```css
p:nth-child(2) {
  color: blue;
}

p:nth-of-type(2) {
  background-color: red;
}
```

The formar one sets 'Test 2' to color blue, and the later one set background of 'Test 3' to red. Because 'Test 2' is the second element of container <div>, and it's type is 'p'. But 'Test 3 ' is the second 'p' element of container <div>.

When elements at the same level are of same types, it makes no diff whether we use nth-child or nth-of-type, but if they are of diff types, we should pay attention to choose the correct one.


If this is not clear enough to you, Chinese guys may have a further look at [this](http://www.zhangxinxu.com/wordpress/2011/06/css3%E9%80%89%E6%8B%A9%E5%99%A8nth-child%E5%92%8Cnth-of-type%E4%B9%8B%E9%97%B4%E7%9A%84%E5%B7%AE%E5%BC%82/).

### 1.3 An example of pseudo-class (<a>)
<div>
  <a href="#" class="pseudo-class">This is an example</a>
</div>

```css
a:link {color: #FF0000}		/* Unvisited hyperlink */
a:visited {color: #00FF00}	/* visited hyperlink */
a:hover {color: #FF00FF}	/* hyperlink with mouse on */
a:active {color: #0000FF}	/* Selects the link while it is being activated (being clicked on or otherwise activated). */

/*Defining hover styles for links is great, but it doesn't help out
those who used keyboard navigation to get to the link. :focus will
select links that are the current focus of the keyboard. This is not
limited to links, but can be used (and really should be used) on inputs
 and textareas as well. Some would tell you to define a :focus style
 for anything that has a :hover style.*/
a:focus {color: #000000}
```

Tips:
- a:hover must be put `after` a:link and a:visited
- a:active must be put `after` a:hover
- pseudo-class is case no-sensitive

## 2. Pseudo-elements (伪元素)

Pseudo-elements effectively create new elements that are not specified in the markup of the document and can be manipulated much like a regular element. This introduces huge benefits for creating cool effects with minimal markup, also aiding significantly in keeping the presentation of the document out of the HTML and in CSS where it belongs.

### 2.1 Different kind of Pseudo-elements

- :first-line //set specific styles to 1st line
- :first-letter
- :before && :after

## 3. Difference between pseudo-class and pseudo-elements

Basically a pseudo-class is a selector that assists in the selection of something that cannot be expressed by a simple selector, for example `:hover`.

 `Pseudo-classes are like ‘fake’ classes that are applied to elements under certain conditions, much like how you would manipulate (操纵) the classes of elements using JavaScript`.

A pseudo-element however allows us to create items that do not normally exist in the document tree, for example :after.

 `A pseudo-element is a ‘fake’ element, it isn’t really in the document with the ‘real’ ones. `

If we use pseudo-class, we'd better use ':'. For pseudo-element, choose '::'. It's just a coding habit.

## 4. Reference

- [W3School Pseudo-class](http://www.w3schools.com/css/css_pseudo_classes.asp)
- [W3School Pseudo-element](http://www.w3schools.com/css/css_pseudo_elements.asp)
- [Pseudo-classes vs pseudo-elements](http://www.growingwiththeweb.com/2012/08/pseudo-classes-vs-pseudo-elements.html)
- [Meet the Pseudo Class Selectors](https://css-tricks.com/pseudo-class-selectors/)
