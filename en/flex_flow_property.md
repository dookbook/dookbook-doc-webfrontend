TOPICS: flex-flow property
        flex-direction property
        flex-wrap property

# CSS Property: `flex-flow`

CSS **`flex-flow`** property is shorthand for **`flex-direction`** and **`flex-wrap`**.

## CSS Property: flex-direction

The CSS **`flex-direction`** property specifies how the internal elements are laid out in the
**flex** container and defines the direction of the main axis (forward or reverse direction)**.

Please note that the values **`row`** and **`row-reverse`** are affected by the directionality of
the **flex** container. If its **`dir`** property is **`ltr`**, **`row`** means a horizontal axis
oriented from left to right, and **`row-reverse`** means from right To left; if the **`dir`** property
is **`rtl`**, **`row`** means axis oriented from right to left, and **`row-reverse`** means from
left To the right.

| Property value | Description |
| :--- | :--- |
| **`row`** | The main axis of the flex container is defined to be the same as the text direction. The spindle start point and spindle end point are the same as the content direction. |
| **`row-reverse`** | Same as **`row`**, but in reverse order. |
| **`column`** | Flexible items will be displayed vertically, just like a column. |
| **`column-reverse`** | Same as **`column`**, but in reverse order. |
| **`initial`** | Set this property to its default value. |
| **`inherit`** | Inherit this property from the parent element. |

## CSS Property: flex-wrap

CSS **`flex-wrap`** property specifies **flex** element **single line display** or **multiline display**.
If line breaks are allowed, this property allows you to control the stacking direction of the lines.

| Property value | Description |
| :--- | :--- |
| **`nowrap`** | Defaults. It is stipulated that flexible projects are not to be separated from rows or columns. |
| **`wrap`** | It is stipulated that flexible projects are to be de-rowed or de-listed when necessary. |
| **`wrap-reverse`** | It is stipulated that flexible items are to be row or column removed when necessary, but in the reverse order. |
| **`initial`** | Set this property to its default value. |
| **`inherit`** | Inherit this property from the parent element. |

## Simple example

```css
#main {
  width: 200px;
  height: 200px;
  border: 1px solid #c3c3c3;
  display: flex;
  flex-flow: row-reverse wrap;
}

#main div {
  width: 50px;
  height: 50px;
}
```

```html
<div id="main">
  <div style="background-color:coral;">A</div>
  <div style="background-color:lightblue;">B</div>
  <div style="background-color:khaki;">C</div>
  <div style="background-color:pink;">D</div>
  <div style="background-color:lightgrey;">E</div>
  <div style="background-color:lightgreen;">F</div>
</div>
```

## Use the `flex-direction` property

```css
#content {
  width: 200px;
  height: 200px;
  border: 1px solid #c3c3c3;
  display: flex;
  flex-direction: column-reverse;
}

#box {
  width: 50px;
  height: 50px;
}

#content1 {
  width: 200px;
  height: 200px;
  border: 1px solid #c3c3c3;
  display: flex;
  flex-direction: row-reverse;
}

#box1 {
  width: 50px;
  height: 50px;
}
```

```html
<h4>This is a Column-Reverse</h4>
<div id="content">
    <div id="box" style="background-color:red;">A</div>
    <div id="box" style="background-color:lightblue;">B</div>
    <div id="box" style="background-color:yellow;">C</div>
</div>
<h4>This is a Row-Reverse</h4>
<div id="content1">
    <div id="box1" style="background-color:red;">A</div>
    <div id="box1" style="background-color:lightblue;">B</div>
    <div id="box1" style="background-color:yellow;">C</div>
</div>
```

## Use the `flex-wrap` property

```css
#main {
  width: 200px;
  height: 200px;
  border: 1px solid #c3c3c3;
  display: flex;
  flex-wrap: wrap;
}

#main div {
  width: 50px;
  height: 50px;
}
```

```html
<div id="main">
  <div style="background-color:coral;">A</div>
  <div style="background-color:lightblue;">B</div>
  <div style="background-color:khaki;">C</div>
  <div style="background-color:pink;">D</div>
  <div style="background-color:lightgrey;">E</div>
  <div style="background-color:lightgreen;">F</div>
</div>
```
