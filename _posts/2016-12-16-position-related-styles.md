---
layout: post
title: "Position related styles"
date: 2016-12-16 16:29:24
image: '/assets/img/'
description: 'No bootstrap, no flexbox, how to use basic on layout'
main-class: 'css'
tags:
- css
categories:
introduction: 'Mainly focus on float and position'
---

## 1. Introduction

During my current project, we use pure css to build the project's framework. Facing the requirements of responsive and multiple devices supporting, most of the times we will use float and absolute position to build the framework of the poject. It will be very difficult to use these styles without knowing the principles. So I collect the principles and definition of these position related styles.

## 2. position

### 2.1 position: relative <br>
  <s>This keyword lays out all elements as though the element were not positioned, and then adjust the element's position, without changing layout (and thus leaving a gap for the element where it would have been had it not been positioned).</s>
  In a word, `relative` won't change the position of the element, mostly we use this to locate the position of absolutely positioned children elements.<br>

### 2.2 position: absolute <br>
  Position it at a specified position relative to its closest positioned ancestor if any, or otherwise relative to the initial containing block. Absolutely positioned boxes can have margins, and they do not collapse with any other margins.<br>
  This is a most widely used value, will move the element away from its current position. We can use it to build covered element, transplacement element and some complex styles. <br>
  Most of the times, we use position:relative to locate the ancestor it will float to.

### 2.3 postion: fixed <br>
  Position it at a specified position relative to the screen's viewport and don't move it when scrolled. <br>
  We will find this usage on ads of some portals like sohu, sina....

## 3. direction offset (top, right, bottom, left)
The four properties have same usage, I will use top as an example.

  - The top CSS property specifies part of the position of positioned elements. It has no effect on non-positioned elements.
  - For absolutely positioned elements (those with position: absolute or position: fixed), it specifies the distance between `the top margin edge of the element` and `the top edge of its containing block`.
  - For relatively positioned elements (those with position: relative), it specifies `the amount the element is moved below its normal position`.
  - When both top and bottom are specified, as long as height is unspecified, auto or 100%, both top and bottom distances will be respected. Otherwise, if height is constrained in any way, the top property takes precedence and the bottom property is ignored.

## 4. float
The float CSS property specifies that an element should be taken from the normal flow and placed along the left or right side of its container, where text and inline elements will wrap around it.

values：<br>
  - float: left<br>
  - float: right

## 5. clear
 - The clear CSS property specifies whether an element can be next to floating elements that precede it or must be moved down (cleared) below them. The clear property applies to both floating and non-floating elements.
 - When applied to `non-floating` blocks, it moves the border edge of the element down until it is below the margin edge of all relevant floats. This movement (when it happens) causes margin collapsing not to occur.<br>
  当应用于非float的元素，会将该元素移到所有与他关联的float元素的下面。注意这里是该元素的border与关联元素的margin对齐，所以`该元素的margin会被（关联元素的margin）覆盖掉` 。
 - When applied to floating elements, it moves the margin edge of the element below the margin edge of all relevant floats. This affects the position of later floats, since later floats cannot be positioned higher than earlier ones.<br>
 当应用于float元素，也会将该元素移到所有与他关联的float元素下面，在他后面的float元素也会被移到后面。此时该元素的margin不会被覆盖掉。
 - The floats that are relevant to be cleared are the earlier floats within the same block formatting context.<br>
 关联的float元素：在该元素之前出现的，在同一个block中的float元素

value:<br>
  - clear: left<br>
  - clear: right<br>
  - clear: both

## 6.Ref
[MDN]!(https://developer.mozilla.org/en-US/docs/Web/CSS/clear)
