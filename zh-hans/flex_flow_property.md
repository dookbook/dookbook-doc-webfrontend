TOPICS: flex-flow property
        flex-direction property
        flex-wrap property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `flex-flow`

CSS **`flex-flow`** 属性是 **`flex-direction`** 和 **`flex-wrap`** 的简写。

## CSS 属性: flex-direction

CSS **`flex-direction`** 属性指定了内部元素是如何在 **flex** 容器中布局的，定义了**主轴的方向(正方向或反方向)**。

请注意，值 **`row`** 和 **`row-reverse`** 受 **flex** 容器的方向性的影响。 如果它的 **`dir`** 属性是 **`ltr`**，**`row`** 表示从左到右定向的水平轴，而
**`row-reverse`** 表示从右到左; 如果 **`dir`** 属性是 **`rtl`**，**`row`** 表示从右到左定向的轴，而 **`row-reverse`** 表示从左到右。

| 属性值 | 说明 |
| :--- | :--- |
| **`row`** | flex容器的主轴被定义为与文本方向相同。主轴起点和主轴终点与内容方向相同。 |
| **`row-reverse`** | 与 **`row`** 相同，但是以相反的顺序。 |
| **`column`** | 灵活的项目将垂直显示，正如一个列一样。 |
| **`column-reverse`** | 与 **`column`** 相同，但是以相反的顺序。 |
| **`initial`** | 设置该属性为它的默认值。 |
| **`inherit`** | 从父元素继承该属性。 |

## CSS 属性: flex-wrap

CSS **`flex-wrap`** 属性指定 **flex** 元素**单行显示**还是**多行显示**。如果允许换行，这个属性允许你控制行的堆叠方向。

| 属性值 | 说明 |
| :--- | :--- |
| **`nowrap`** | 默认值。规定灵活的项目不拆行或不拆列。|
| **`wrap`** | 规定灵活的项目在必要的时候拆行或拆列。|
| **`wrap-reverse`** | 规定灵活的项目在必要的时候拆行或拆列，但是以相反的顺序。|
| **`initial`** | 设置该属性为它的默认值。 |
| **`inherit`** | 从父元素继承该属性。 |

## 简单示例

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

## 使用`flex-direction`属性

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

## 使用`flex-wrap`属性

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
