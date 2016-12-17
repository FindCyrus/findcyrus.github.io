---
layout: post
title: "HTML DOM Elements"
date: 2016-11-02 17:03:52
image: '/assets/img/'
description: 'HTML DOM element'
main-class: 'html'
color:
tags:
- HTML
- JavaScript
categories:
introduction: 'List all basic grammar of HTML Dom element'
---
The Document Object Model (DOM) is a cross-platform and language-independent application programming interface that treats an HTML, XHTML, or XML document as a tree structure wherein each node is an object representing a part of the document. The objects can be manipulated programmatically and any visible changes occurring as a result may then be reflected in the display of the document. From [Wiki](https://en.wikipedia.org/wiki/Document_Object_Model)

## 1. Finding HTML Elements

```javascript
document.getElementById(id);
document.getElementsByTagName('p');
//find by class name
document.getElementsByClassName('table-sort');
document.querySelectorAll("p.intro");
```

## 2. Changing Values of HTML Elements

```javascript
ele.innerHTML = value; //content
ele.attribute = attr;
ele.style.property = prop; //css prop
```

## 3. CRUD

```javascript
ele.createElement(element);
ele.removeChild(element);
ele.appendChild(element);
ele.insertBefore(para,child);
ele.replaceChild(element)
```

## 4. Events and Event listeners

``` html
<body onload="checkcookies()" onunload="clearcookies()">
  <input onchange="upperCase()">
  <button onclick="function()"></button>
  <label onmouseover="" onmouseout="" onmousedown="" onmouseup="">Click me</label>
</body>
```

Tips: all event names are lower case.
We can also add event listeners using javascript.

```javascript
//element.addEventListener(event, function, useCapture);
document.getElementById("myBtn").addEventListener("click", displayDate);
```
Here is the explaination for [useCapture](http://www.w3schools.com/js/js_htmldom_eventlistener.asp)

> It's better to use addEvnetListener instead of addding event to elements
> The addEventListener() method attaches an event handler to the specified element.
> The addEventListener() method attaches an event handler to an element without overwriting > existing event handlers.
> You can add many event handlers to one element.
> You can add many event handlers of the same type to one element, i.e two "click" events.
> You can add event listeners to any DOM object not only HTML elements. i.e the window object.
> The addEventListener() method makes it easier to control how the event reacts to bubbling.
> When using the addEventListener() method, the JavaScript is separated from the HTML markup.
> for better readability and allows you to add event listeners even when you do not control the HTML markup.
> You can easily remove an event listener by using the removeEventListener() method.

So there comes a question, what is useCapture:

> There are two ways of event propagation in the HTML DOM, bubbling and capturing.
Event propagation is a way of defining the element order when an event occurs. If you have a <p> element inside a <div> element, and the user clicks on the <p> element, which element's "click" event should be handled first?
In bubbling the inner most element's event is handled first and then the outer: the <p> element's click event is handled first, then the <div> element's click event.
In capturing the outer most element's event is handled first and then the inner: the <div> element's click event will be handled first, then the <p> element's click event.
With the addEventListener() method you can specify the propagation type by using the "useCapture" parameter(set it `true` or `false`).


## Reference
1. [W3School HTML DOM](http://www.w3schools.com/js/js_htmldom.asp)

2. [Wiki DOM Introduction](https://en.wikipedia.org/wiki/Document_Object_Model)

3. [W3C Recommendation](https://www.w3.org/TR/DOM-Level-2-Core/introduction.html)
