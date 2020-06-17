TOPICS: flex property
        flex-grow property
        flex-shrink property
        flex-basis property

# CSS Property: `flex`

The CSS **`flex`** property specifies how the flex element **stretches** or **shortens** to fit the
**free space** in the flex container. This is a shorthand property used to set **`flex-grow`**,
**`flex-shrink`** and **`flex-basis`**.

In most cases, developers need to set **`flex`** to **`auto`**, **`initial`**, **`none`** or a
unitless positive number.

By default, the element will not be shortened to less than the size of the content box, if you want
to change this situation, please set the element's [**`min-width`**](/en/webfrontend/min-width_property)
and [** `min-height`**](/en/webfrontend/min-height_property) property.

The **`flex`** property can specify **1**, **2**, or **3** values.

**Single value syntax**: The value must be one of the following:

- A unitless number (**number**): It will be treated as the value of **flex-grow**.
- A valid width (**width**) value: it will be treated as the value of **flex-basis**.
- The keywords **`none`**, **`auto`** or **`initial`**.

**Double value syntax**: The first value must be a **unitless number**, and it will be treated as a
**flex-grow** value. The second value must be one of the following:

- A unitless number: it will be treated as the value of **flex-shrink**.
- A valid width value: it will be treated as the value of **flex-basis**.

**Three-valued syntax**:

- The first value must be a **unitless number**, and it will be treated as a **flex-grow** value.
- The second value must be a **unitless number**, and it will be treated as a **flex-shrink** value.
- The third value must be a **valid width value**, and it will be treated as the **flex-basis** value.

## Property value

| Property value | Description |
| :--- | :--- |
| **flex-grow** | A number that specifies the amount by which the project will be expanded relative to other flexible projects. |
| **flex-shrink** | A number that specifies the amount by which the project will contract relative to other flexible projects. |
| **flex-basis** | The length of the item. Legal values: "`auto`", "`inherit`" or a number followed by "`%`", "`px`", "`em`" or any other unit of length. |
| **`auto`** | Same as `1` `1` `auto`. |
| **`none`** | Same as `0` `0` `auto`. |
| **`initial`** | Set this property to its default value, which is `0` `1` `auto`. |

When using one or two unitless numbers, **`flex-basis`** will change from `auto` to `0`.

## CSS Property: `flex-grow`

The CSS **`flex-grow`** property defines the stretch factor of the flex item.

| Property value | Description |
| :--- | :--- |
| **number** | A number that specifies the amount by which the project will be expanded relative to other flexible projects. The default value is `0`. |
| **`initial`** | Set this property to its default value. |
| **`inherit`** | Inherit this property from the parent element. |

## CSS Property: `flex-shrink`

The CSS **`flex-shrink`** property specifies the shrinking rules for `flex` elements. The `flex`
element shrinks only when the sum of the default widths is greater than the container, and the
contracted size is based on the value of `flex-shrink`.

| Property value | Description |
| :--- | :--- |
| **number** | A number that specifies the amount by which the project will be expanded relative to other flexible projects. The default value is `0`. |
| **`initial`** | Set this property to its default value. |
| **`inherit`** | Inherit this property from the parent element. |

## CSS Property: `flex-basis`

The CSS property **`flex-basis`** specifies the initial size of the `flex` element in the major axis
direction. If you do not use `box-sizing` to change the box model, then this property determines the
width or height (depending on the direction of the main axis) of the content-box of the `flex` element.

| Property value | Description |
| :--- | :--- |
| **number** | A number that specifies the amount by which the project will be expanded relative to other flexible projects. The default value is `0`. |
| **`auto`** | Defaults. The length is equal to the length of the flexible item. If the item does not specify a length, the length will be determined according to the content. |
| **width** | **width** value can be a number followed by absolute units such as `px`, `mm`, `pt`; the value can also be a percentage, then this percentage is relative to the width or height of its parent flexible box container (Depending on the spindle direction). Negative values are not allowed.|
| **`content`** | The content of elements based on **flex** is automatically resized. |
| **`initial`** | Set this property to its default value. |
| **`inherit`** | Inherit this property from the parent element. |

## Simple example

```css
#main {
  width: 220px;
  height: 300px;
  border: 1px solid black;
  display: flex;
}

#main div {
  flex: 1;
}
```

```html
<div id="main">
  <div style="background-color:coral;">红色</div>
  <div style="background-color:lightblue;">蓝色</div>  
  <div style="background-color:lightgreen;">带有更多内容的绿色 div</div>
</div>
```

## Use `flex-grow` property

```css
#main {
  width: 350px;
  height: 100px;
  border: 1px solid #c3c3c3;
  display: flex;
}

#main div:nth-of-type(1) { flex-grow: 1; }
#main div:nth-of-type(2) { flex-grow: 3; }
#main div:nth-of-type(3) { flex-grow: 1; }
#main div:nth-of-type(4) { flex-grow: 1; }
#main div:nth-of-type(5) { flex-grow: 1; }
```

```html
<div id="main">
  <div style="background-color:coral;"></div>
  <div style="background-color:lightblue;"></div>
  <div style="background-color:khaki;"></div>
  <div style="background-color:pink;"></div>
  <div style="background-color:lightgrey;"></div>
</div>
```

## Use the `flex-shrink` property

```css
#content {
  display: flex;
  width: 500px;
}

#content div {
  flex-basis: 120px;
  border: 3px solid rgba(0, 0, 0, 0.2);
}

.box {
  flex-shrink: 1;
}

.box1 {
  flex-shrink: 3;
}
```

```html
<p>div 总宽度为 500px, flex-basic 为 120px。</p>
<p>A, B, C 设置 flex-shrink:1。 D , E 设置为 flex-shrink:3</p>
<p>D , E 宽度与 A, B, C 不同</p>
<div id="content">
  <div class="box" style="background-color:red;">A</div>
  <div class="box" style="background-color:lightblue;">B</div>
  <div class="box" style="background-color:yellow;">C</div>
  <div class="box1" style="background-color:brown;">D</div>
  <div class="box1" style="background-color:lightgreen;">E</div>
</div>
```

## 使用`flex-basis`属性

```css
#main {
  width: 350px;
  height: 100px;
  border: 1px solid #c3c3c3;
  display: flex;
}

#main div {
  flex-basis: 40px;
}

#main div:nth-of-type(2) {
  flex-basis: 120px;
}
```

```html
<div id="main">
  <div style="background-color:coral;"></div>
  <div style="background-color:lightblue;"></div>
  <div style="background-color:khaki;"></div>
  <div style="background-color:pink;"></div>
  <div style="background-color:lightgrey;"></div>
</div>
```
