TOPICS: CSS Box Model
        margin property
        margin-top property
        margin-right property
        margin-bottom property
        margin-left property
        padding property
        padding-top property
        padding-right property
        padding-bottom property
        padding-left property
        border property
        border-width property
        border-style property
        border-color property
        border-top property
        border-top-color property
        border-top-style property
        border-top-width property
        border-right property
        border-right-color property
        border-right-style property
        border-right-width property
        border-bottom property
        border-bottom-color property
        border-bottom-style property
        border-bottom-width property
        border-left property
        border-left-color property
        border-left-style property
        border-left-width property

# CSS 盒模型 (`margin`, `padding`, `border`)

**CSS 盒模型** (**Box Model**) 是一个用来设计和*布局*时使用的术语。本质上将HTML元素封装在一个盒子里，它包括：**外边距**，**边框**，**填充**（**内边距**），和**实际内容**。

下图说明了盒子模型(Box Model)：

![CSS 盒模型](/media/webfrontend__css-box-model.png)

不同部分的说明：

| 部分 | 说明 | 涉及的CSS属性 |
| :--: | :-- | :-- |
| **Margin** （**外边距**）| 边框外的区域。外边距没有背景颜色，它是完全透明的。 | [*`margin`*](#margin) 等相关属性。 |
| **Border**（**边框**）| 边框。可有颜色填充。| [*`border`*](#border) 等相关属性。 |
| **Padding**（**内边距**）| 边框内、内容外的区域。有颜色填充。| [*`padding`*](#padding) 等相关属性。|
| **Content**（**内容**）| 盒子的内容，显示文本或图像。| *`width`*, *`height`*。详见 [CSS 尺寸](/zh-hans/webfrontend/CSS_dimension) |

## 盒模型的尺寸计算

当您指定一个元素的`width`和`height`属性时，你只是设置内容区域的宽度和高度。要知道整个元素的盒模型尺寸大小，你还必须添加*填充*，*边框*和*外边距*。

下面的例子中的元素的宽实际大小为`280px`, 实际占据的尺寸为`300px`。

```css
div {
  width: 250px;
  padding: 10px;
  border: 5px solid gray;
  margin: 10px;
}
```

元素的实际宽度为`280px`，尺寸计算如下：

- 宽度 = `width`(`250px`) + `padding-left`(`10px`)+`padding-right` (`10px`) + `border-left`(`5px`) + `border-right`(`5px`)
- 高度 = `height` + `padding-top` + `padding-bottom` + `border-top` + `border-bottom`

而盒子需要占据的区域宽度为`300px`，尺寸计算如下：

- 盒子宽度 = 元素宽度 (`280px`) + `margin-left` (`10px`) + `margin-right` (`10px`)
- 盒子高度 = 元素高度 + `margin-top` + `margin-bottom`

## 外边距 (Margin) 和内边距 (Padding)

### 外边距属性 (Margin)

| 属性 | 描述 |
| :--: | :--- |
| **`margin`** | 元素**上下左右**四个方向的*外边距*的**简写**。可以为负值。|
| **`margin-top`** | 元素的**上或顶部**外边距。 |
| **`margin-right`** | 元素的**右**外边距。 |
| **`margin-bottom`** | 元素的**下或底部**外边距。 |
| **`margin-left`** | 元素的**左**外边距。 |

### 内边距属性 (Padding)

| 属性 | 描述 |
| :--: | :--- |
| **`padding`** | 元素**上下左右**四个方向的*内边距*的简写。**不能为负值**。 |
| **`padding-top`** | 元素的**上或顶部**内边距。 |
| **`padding-right`** | 元素的**右**内边距。 |
| **`padding-bottom`** | 元素的**下或底部**内边距。 |
| **`padding-left`** | 元素的**左**内边距。 |

### `margin` 和 `padding` 属性值

它们都共同含有如下属性值

| 属性值 | 说明 |
| :--: | :--- |
| **length** | 指定一个固定的长度单位。参见 [CSS 长度单位](/zh-hans/webfrontend/CSS_length_unit) |
| **`%`** | 基于父元素的百分比。|

!!! warn ""
    `margin`的 *length* 和 *`%`* 属性值可以为**负值**; 而`padding`的 *length* 和 *`%`* **不能为负值**。

而 `margin` 另有属性值 **`auto`** 让浏览器自动选择。

### `margin`和`padding`属性简写形式

`margin`, `padding` 简写属性在一个声明中设置四个方向的属性。该属性可以有1到4个值。

以`margin`为例：

```css
/* 四个值: 上 右 下 左 (顺时针顺序) */
margin: 10px 5px 15px 20px;

/* 以上等同于 */
margin-top: 10px;     /* 上边距 */
margin-right: 5px;    /* 右边距 */
margin-bottom: 15px;  /* 下边距 */
margin-left: 20px;    /* 左边距 */
```

```css
/* 三个值：上 左右 下 */
margin: 10px 5px 15px;

/* 以上等同于 */
margin-top: 10px;     /* 上边距 */
margin-left: 5px;     /* 左边距 */
margin-right: 5px;    /* 右边距 */
margin-bottom: 15px;  /* 下边距 */
```

```css
/* 两个值：上下 左右 */
/* 上下边距 10px, 左右边距 5px */
margin: 10px 5px;

/* 以上等同于 */
margin-top: 10px;
margin-bottom: 10px;
margin-left: 5px;
margin-right: 5px;
```

```css
/* 一个值: 上下左右 */
/* 上、下、左、右边距均为 10px */
margin: 10px;

/* 以上等同于 */
margin-top: 10px;
margin-bottom: 10px;
margin-left: 10px;
margin-right: 10px;
```

## 边框 (Border)

| 属性 | 描述 |
| :--: | :--- |
| **`border`** | 元素*边框*属性的**简写**。|
| **`border-width`** | 元素边框的**宽度**。四个方向可有 *`border-top-width`*, *`border-right-width`*, *`border-bottom-width`*, *`border-left-width`*。|
| **`border-style`** | 元素边框的**样式**。四个方向可有 *`border-top-style`*, *`border-right-style`*, *`border-bottom-style`*, *`border-left-style`*。|
| **`border-color`** | 元素边框的**颜色**。四个方向可有 *`border-top-color`*, *`border-right-color`*, *`border-bottom-color`*, *`border-left-color`*。|
| **`border-top`** | 元素的**上边框**或**顶部边框**，是 *`border-top-color`*, *`border-top-style`*, 和 *`border-top-width`* 三个属性的缩写。|
| **`border-right`** | 元素的**右边框**，是 *`border-right-color`*, *`border-right-style`*, 和 *`border-right-width`* 三个属性的缩写。 |
| **`border-bottom`** | 元素的**下边框**，是 *`border-bottom-color`*，*`border-bottom-style`* 和 *`border-bottom-width`* 三个属性的缩写。 |
| **`border-left`** | 元素的**左边框**，是 *`border-left-color`*, *`border-left-style`*, 和 *`border-left-width`* 三个属性的缩写。 |

### 边框宽度 `border-width`

| `border-width`属性值 | 说明 |
| :--: | :--- |
| **`thin`** | **细**的边框。|
| **`medium`** | *默认*。**中等粗细**的边框。|
| **`thick`** | **粗**的边框。|
| **length** | **自定义**边框的宽度。可使用[CSS 长度单位](/zh-hans/webfrontend/CSS_length_unit) |
| **`inherit`** | 从父元素继承边框宽度。|

`border-width`属性设置一个元素的四个边框的宽度。此属性可以有一到四个值。

```css
/* 四个值: 上 右 下 左 (顺时针顺序) */
border-width: thin medium thick 10px;

/* 以上等同于 */
border-top-width: thin;      /* 上边框 */
border-right-width: medium;  /* 右边框 */
border-bottom-width: thick;  /* 下边框 */
border-left-width: 10px;     /* 左边框 */
```

```css
/* 三个值：上 左右 下 */
border-width: thin medium thick;

/* 以上等同于 */
border-top-width: thin;
border-left-width: medium;
border-right-width: medium;
border-bottom-width: thick;
```

```css
/* 两个值：上下 左右 */
border-width: thin thick;

/* 以上等同于 */
border-top-width: thin;
border-bottom-width: thin;
border-left-width: thick;
border-right-width: thick;
```

```css
/* 一个值: 上下左右 */
/* 上、下、左、右边框宽度均为 thin */
border-width: thin;

/* 以上等同于 */
border-top-width: thin;
border-bottom-width: thin;
border-left-width: thin;
border-right-width: thin;
```

### 边框样式 `border-style`

| `border-style`属性值 | 说明 |
| :--: | :--- |
| **`none`** | 定义无边框 |
| **`hidden`** | 与 **`none`** 相同。但是，当应用于表格时，`hidden`用于解决边框冲突。|
| **`dotted`** | **点状** |
| **`dashed`** | **虚线** |
| **`solid`** | **实线** |
| **`double`** | **双线** |
| **`groove`** | **雕刻效果** |
| **`ridge`** | **浮雕效果** |
| **`inset`** | **内嵌效果** |
| **`outset`** | **外凸效果** |
| **`inherit`** | 从父元素继承边框样式。|

`border-style`属性设置一个元素的四个边框的样式。此属性可以有一到四个值。

```css
/* 四个值: 上 右 下 左 (顺时针顺序) */
border-style: dotted solid double dashed;

/* 以上等同于 */
border-top-style: dotted;     /* 上边框 */
border-right-style: solid;    /* 右边框 */
border-bottom-style: double;  /* 下边框 */
border-left-style: dashed;    /* 左边框 */
```

```css
/* 三个值：上 左右 下 */
border-style: dotted solid double;

/* 以上等同于 */
border-top-style: dotted;
border-left-style: solid;
border-right-style: solid;
border-bottom-style: double;
```

```css
/* 两个值：上下 左右 */
border-style: dotted solid;

/* 以上等同于 */
border-top-style: dotted;
border-bottom-style: dotted;
border-left-style: solid;
border-right-style: solid;
```

```css
/* 一个值: 上下左右 */
/* 上、下、左、右边框样式均为 dotted */
border-style: dotted;

/* 以上等同于 */
border-top-style: dotted;
border-bottom-style: dotted;
border-left-style: dotted;
border-right-style: dotted;
```

### 边框颜色 `border-color`

| `border-color`属性值 | 说明 |
| :--: | :--- |
| **color** | 边框的颜色, 在 [CSS 颜色](/zh-hans/webfrontend/css_color) 查找颜色值的完整列表 |
| **`transparent`** | 指定边框的颜色是**透明的**。这是*默认*的。|
| **`inherit`** | 从父元素继承。|

`border-color`属性设置一个元素的四个边框的颜色。此属性可以有一到四个值。

```css
/* 四个值: 上 右 下 左 (顺时针顺序) */
border-color: #111 #222 #333 #444;

/* 以上等同于 */
border-top-color: #111;     /* 上边框 */
border-right-color: #222;   /* 右边框 */
border-bottom-color: #333;  /* 下边框 */
border-left-color: #444;    /* 左边框 */
```

```css
/* 三个值：上 左右 下 */
border-color: #111 #222 #333;

/* 以上等同于 */
border-top-color: #111;
border-left-color: #222;
border-right-color: #222;
border-bottom-color: #333;
```

```css
/* 两个值：上下 左右 */
border-color: #111 #222;

/* 以上等同于 */
border-top-color: #111;
border-bottom-color: #111;
border-left-color: #222;
border-right-color: #222;
```

```css
/* 一个值: 上下左右 */
/* 上、下、左、右边框颜色均为 #111 */
border-color: #111;

/* 以上等同于 */
border-top-color: #111;
border-bottom-color: #111;
border-left-color: #111;
border-right-color: #111;
```

### `border` 属性简写

| 属性值 | 说明 |
| :--: | :--- |
| **border-width** | 指定边框的**宽度** |
| **border-style** | 指定边框的**样式** |
| **border-color** | 指定边框的**颜色** |
| **`inherit`** | 指定从父元素继承`border`属性值 |

```css
border: 10px solid #111;
```

## 示例

```html
<div>
  <p class="a">这是一段路内容A</p>
  <p class="b">这是一段路内容b</p>
</div>
```

```css
* { margin: 0; padding: 0;}

div {
  border: 1px solid #333; /* 给该元素定义1px实线颜色为红色的边框 */
  margin: 10px; /* 给该元素定义距离四个边框外上右下左为10px的外边距 */
  padding: 10px 20px; /* 给该元素定义距离边框内上下为10px、左右为20px的内边距 */
}

div p.a {
  background: red;
  padding: 10px 20px 5px 30px; /* 定义内边距上10px、右20px、下5px、左30px */
  margin-bottom: 20px; /* 定义外边距下20px*/
}

div p.b {
  background: red;
  padding: 10px 20px 5px; /* 定义内边距上为10px，左右各为20px、下为5px */
}
```

## 参考

- [W3C CSS 2.2规范 - 盒模型](https://www.w3.org/TR/CSS22/box.html)
