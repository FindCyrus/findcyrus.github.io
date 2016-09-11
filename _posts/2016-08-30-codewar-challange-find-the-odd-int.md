---
layout: post
title: "[Codewars Challange] <br> Find the odd int"
date: 2016-08-29 17:27:55
image: '/assets/img/'
description: "Given an array, find the int that appears an odd number of times.
There will always be only one integer that appears an odd number of times."
main-class: 'codewars'
color:
tags:
- codewars
- grammar-array
categories:
twitter_text:
introduction: "Given an array, find the int that appears an odd number of times.
There will always be only one integer that appears an odd number of times."
---
## Challenge

```
Given an array, find the int that appears an odd number of times.

There will always be only one integer that appears an odd number of times.
```

## Challenge Analysis

这道题主要考察的JS中Array方法的掌握，基于不同人对Array方法的理解，这道题的解法多种多样，不过最佳解法仍然很巧妙，值得学习。

## My Solution

{% highlight javascript %}
function findOdd(A) {
  return A.find((element,index,array)=>{
    let count = array.filter((item)=>{
        return item == element;
      }).length;
    return count % 2 !== 0;
  })
}
{% endhighlight %}

在我的解法中，主要用到了array中的`find`和`filter`两个方法，其中`find`方法用来找到满足题目条件的数字，`filter`方法在`find`的遍历中使用，用来对每个数组项的出现次数计数。我的解法比较低效，需要O(n*n)的时间复杂度。<br>
这里`find`的参数是一个callback funcion， 该function的参数如下：

  - `element`
    The current element being processed in the array.
  - `index`
    The index of the current element being processed in the array.
  - `array`
    The array find was called upon.

## Best Practices

{% highlight javascript %}
  const findOdd = (xs) => xs.reduce((a, b) => a ^ b);
{% endhighlight %}

这个方法结合了array的`reduce`方法和`逐位(bitwise)运算`,逐位运算一直是我的软肋，平时也不会想着用的。。。

逐位运算的方法主要是下面三个:
- Bitwise AND assignment: x&y
- Bitwise XOR assignment: x^y
- Bitwise OR assignment: x|y

## Further Reading
- [Array.find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
- [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
