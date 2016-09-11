---
layout: post
title: "[Basic CSS Styles] <br> #2  Transform Functions"
date: 2016-09-10 15:09:45
image: '/assets/img/'
description: 'Introduce some basic transform functions'
main-class: 'css'
color:
tags:
- css
categories:
- CSS foundation
twitter_text:
introduction: 'Introduce some basic transform functions, and how to use transform to vertical center some items'
---

## 1. Transform functions

### 1.1 What are they?
The <transform-function> CSS data type denotes a function applied to an element's representation in order to modify it. These functions will `change the relative position of the element`, `rotate` or `stretch` them.

### 1.2 When to use them?
Most of the times, they are not needed to implement our sites. But for some situations, such as we need to create some items ourselves and need to add some animations to them, or we need to move them, these functions may help.

## 2. Functions defining transformations
Several functions are available to describe transformations in CSS. Each one applies a geometric operation, in 2D or 3D:

### 2.0  persperctive (视点设置)
The perspective() CSS function defines the distance between the z=0 plane and the user in order to give to the 3D-positioned element some perspective. Each 3D element with z>0 becomes larger; each 3D-element with z<0 becomes smaller. The strength of the effect is determined by the value of this property.

- syntax:  `perspective(length)`

```
Tips:
 - 什么是视点：即我们看东西时眼睛所在的位置
 - perspective一般和3D一起使用，具体怎么用我也不知道
```

### 2.1 rotate (定点旋转)
The rotate() CSS function defines a transformation that moves the element around a fixed point (as specified by the transform-origin property) without deforming it. The amount of movement is defined by the specified angle; if positive, the movement will be clockwise, if negative, it will be counter-clockwise. A rotation by 180° is called point reflection.

- syntax:  `rotate(a) === rotatez(a)`

a: Is an [angle](https://developer.mozilla.org/en-US/docs/Web/CSS/angle) representing the angle of the rotation. A positive angle denotes a clockwise rotation, a negative angle a counter-clockwise one.

- relative functions
  - rotate3d(x,y,z,a)
  - rotatex(a) (旋转x轴)
  - rotatey(a) (旋转y轴)

### 2.2 scale (缩放)
The scale() CSS function modifies the `size` of the element. It can either augment or decrease its size and as the amount of scaling is defined by a vector, it can do so more in one direction than in another one.

- syntax: `scale(sx)` or `scale(sx, sy)`
- relative functions
  - scale3d(x,y,z)
  - scalex(s)
  - scaley(s)
  - scalez(s)

### 2.3 skew (拉伸)
The skew() CSS function is a shear mapping, or transvection, distorting each point of an element by a certain angle in each direction. It is done by increasing each coordinate by a value proportionate to the specified angle and to the distance to the origin. The more far from the origin, the more away the point is, the greater will be the value added to it.

- syntax: `skew(sx)` or `skew(sx, sy)`
- relative functions
  - skewx(s)
  - skewy(s)

### 2.4 translate (位移)
The translate() CSS function moves the position of the element on the plane. This transformation is characterized by a vector whose coordinates define how much it moves in each direction.

- syntax: `translate(tx)` or `translate(tx, ty)`
- relative functions
  - translate3d(t)
  - translatex(t)
  - translatey(t)
  - translatez(t)

## 3.0 Example

HTML Codes
{% highlight html %}
<div>
    <p>foo</p>
    <p class="rotate">rotate</p>
    <p class="scale">scale</p>
    <p class="skew">skew</p>
    <p class="translate">skew</p>
</div>
{% endhighlight %}

CSS codes

```css
.rotate{
  /* identical to rotateZ(45deg); */
  transform: rotate(45deg);
  background-color: green;
}

.scale {
  /* the same as transform: scaleX(2) scaleY(2);*/
  transform: scale(2);
  background-color: blue;
}

.skew {
 /* the same as skewX(10deg); */
  transform: skew(10deg);
  background-color: gray;
}

.translate {
  /* equivalent to translateX(10px)*/
  transform: translate(10px);
  background-color: yellow;
}
```

Result
![Result](/assets/img/images/2016-09-11-css-basic-styles-2-transform-function/2016-09-11_164836.jpg)


## 3.1 Reference
- [MDN links](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function)
- [How to set vertical center](http://zerosixthree.se/vertical-align-anything-with-just-3-lines-of-css/)
- [详细解释transform方法含义(中文配图)](http://www.zhangxinxu.com/wordpress/2012/09/css3-3d-transform-perspective-animate-transition/)
