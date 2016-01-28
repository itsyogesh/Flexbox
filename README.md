# Understanding Flexbox

### What is Flexbox?

When dealing with page layouts in CSS the normal document flow sees elements layouts either horizontally (in-line flow) or vertically (in-block flow).

A majority of the layout is handled with block like elements and the box-model properties (width, height, border, etc.) to control the sizing and the spacing of the different elements.

Flexbox (Flexible box layout module) is an entire [layout module ](https://www.w3.org/TR/css-flexbox-1/) with properties that form a new approach to layouts. The major difference between traditional layouts and flexbox is that it does not conform to the typical block and inline flow directions, instead the are said to be in **flex flow**.

>Its now supported by all major browsers (including IE).

To build a layout with flexbox, we need two things, **flex-container** and **flex-items**.

The **flex-container** is a parent element that effectively turns on flexbox and makes all of its child elements **flex-items**.

Let's create a **flex-container** and add a few **flex-items** inside it.

```
<div class="flex-container">
  <div class="box">1</div>
  <div class="box">2</div>
  <div class="box">3</div>
  <div class="box">4</div>
  <div class="box">5</div>
  <div class="box">6</div>
</div>
```
To convert a block level element into a **flex-container**, we have to set the `display` property on the element to `flex`.

```
.flex-container {
  display:flex;
}
```
>You can create any number of flex containers on a page, and even nest them inside each other.

The **flex-items** will flow according to the properties set on them or on their parent element.

```
.flex-container {
  display: flex;
}

.box {
  height: 100px;
  padding-top: 50px;
  color: #fff;
  font-weight: bold;
  font-size: 2.2em;
  text-align: center;
  flex-grow: 1;
}

.box:first-child {background: #c2d775;}
.box:nth-child(2) {background: #007278}
.box:nth-child(3) {background: #c7b600;}
.box:nth-child(4) {background: #a90077;}
.box:nth-child(5) {background: #00a378;}
.box:last-child {background: #00ea72;}
```

Check out the code on [codepen](http://codepen.io/yogeshkumar180592/pen/JGvmxd).

### Flexbox Properties

#### flex-grow

`flex-grow` property allows the flex-items to grow to the full width of the flex-container. The value of this property determines the ratio in which this space has to be divided amongst the child flex-items. For eg: `flex-grow:1;` would divide all the child flex-items into equal spaces.

```
.flex-container {
  flex-grow: 1;
}
```
To specify a **custom ratio** inside a child flex-item, you can add the `flex-grow` property inside that element.

```
.box:first-child {
  background: #c2d775;
  flex-grow: 2;
}
```

Checkout the example code [here](http://codepen.io/yogeshkumar180592/pen/yejQvL).

#### order

`order` allows you to specify the order in which flex-items are displayed inside the flex-container.
By default, when the order is not specified, the order is dictated by the order in which the html was written.

```
.box:nth-child(2){
  background: #c2d775;
  order: 2;
}
```
//Todo
flex-wrap
flex-direction
justify-content
align-items
align-self
