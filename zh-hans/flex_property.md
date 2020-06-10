TOPICS: flex property
        flex-grow property
        flex-shrink property
        flex-basis property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `flex`

CSS属性 **`flex`** 规定了弹性元素如何**伸长**或**缩短**以适应 **flex** 容器中的**可用空间**。这是一个简写属性，用来设置
**`flex-grow`**、**`flex-shrink`** 与 **`flex-basis`**。

大多数情况下，开发者需要将 **`flex`** 设置为 **`auto`**，**`initial`**，**`none`**或一个无单位正数。

默认情况下，元素不会缩短至小于内容框尺寸，若想改变这一状况，请设置元素的 [**`min-width`**](/zh-hans/webfrontend/min-width) 与 [**`min-height`**](/zh-hans/webfrontend/min-height)属性。

`flex` 属性可以指定1个，2个或3个值。

**单值语法**: 值必须为以下其中之一:

- 一个无单位数(**number**): 它会被当作**flex-grow**的值。
- 一个有效的宽度(**width**)值: 它会被当作**flex-basis**的值。
- 关键字 **`none`**，**`auto`**或 **`initial`**.

**双值语法**: 第一个值必须为一个**无单位数**，并且它会被当作 **flex-grow** 的值。第二个值必须为以下之一：

- 一个无单位数：它会被当作 **flex-shrink** 的值。
- 一个有效的宽度值: 它会被当作 **flex-basis** 的值。

**三值语法**:

- 第一个值必须为一个**无单位数**，并且它会被当作 **flex-grow** 的值。
- 第二个值必须为一个**无单位数**，并且它会被当作 **flex-shrink** 的值。
- 第三个值必须为一个**有效的宽度值**， 并且它会被当作 **flex-basis** 的值。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **flex-grow** | 一个数字，规定项目将相对于其他灵活的项目进行扩展的量。 |
| **flex-shrink** |一个数字，规定项目将相对于其他灵活的项目进行收缩的量。 |
| **flex-basis** | 项目的长度。合法值："`auto`"、"`inherit`" 或一个后跟 "`%`"、"`px`"、"`em`" 或任何其他长度单位的数字。 |
| **`auto`** | 与 `1` `1` `auto` 相同。 |
| **`none`** | 与 `0` `0` `auto` 相同。 |
| **`initial`** | 设置该属性为它的默认值，即为 `0` `1` `auto`。 |

当使用一个或两个无单位数时, `flex-basis` 会从 `auto` 变为 `0`。

## CSS 属性：`flex-grow`

CSS **`flex-grow`** 属性定义弹性盒子项（flex item）的拉伸因子。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 一个数字，规定项目将相对于其他灵活的项目进行扩展的量。默认值是 `0`。|
| **`initial`** | 设置该属性为它的默认值。 |
| **`inherit`** | 从父元素继承该属性。 |

## CSS 属性：`flex-shrink`

CSS **`flex-shrink`** 属性指定了 `flex` 元素的收缩规则。`flex` 元素仅在默认宽度之和大于容器的时候才会发生收缩，其收缩的大小是依据 `flex-shrink` 的值。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 一个数字，规定项目将相对于其他灵活的项目进行扩展的量。默认值是 `0`。|
| **`initial`** | 设置该属性为它的默认值。 |
| **`inherit`** | 从父元素继承该属性。 |

## CSS 属性：`flex-basis`

CSS 属性 **`flex-basis`** 指定了 `flex` 元素在主轴方向上的初始大小。如果不使用 `box-sizing` 来改变盒模型的话，那么这个属性就决定了 `flex` 元素的内容盒（content-box）的宽或者高（取决于主轴的方向）的尺寸大小。

| 属性值 | 说明 |
| :--- | :--- |
| **number** | 一个数字，规定项目将相对于其他灵活的项目进行扩展的量。默认值是 `0`。|
| **`auto`** | 默认值。长度等于灵活项目的长度。如果该项目未指定长度，则长度将根据内容决定。|
| **width** | **width** 值可以是一个数字后面跟着绝对单位例如 `px`、`mm`、`pt`; 该值也可以是一个百分数，那么这个百分数就是相对于其父弹性盒容器的宽或者高（取决于主轴方向）。负值是不被允许的。|
| **`content`** | 基于 **flex** 的元素的内容自动调整大小。 |
| **`initial`** | 设置该属性为它的默认值。 |
| **`inherit`** | 从父元素继承该属性。 |

## 简单示例

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

## 使用`flex-grow`属性

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

## 使用`flex-shrink`属性

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
