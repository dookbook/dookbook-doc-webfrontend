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

# CSS 盒模型

**CSS 盒模型**本质上是一个盒子，封装周围的HTML元素，它包括：**边距**，**边框**，**填充**，和**实际内容**。

盒模型允许我们在其它元素和周围元素边框之间的空间放置元素

下面的图片说明了盒子模型(Box Model)：

![CSS 盒模型](/media/webfrontend__css-box-model.png)

不同部分的说明：

- **Margin（外边距）** - 清除边框区域。Margin没有背景颜色，它是完全透明
- **Border（边框）** - 边框周围的填充和内容。边框是受到盒子的背景颜色影响
- **Padding（内边距）** - 清除内容周围的区域。会受到框中填充的背景颜色影响
- **Content（内容）** - 盒子的内容，显示文本和图像

为了在所有浏览器中的元素的宽度和高度设置正确的话，你需要知道的盒模型是如何工作的。

例如：当您指定一个CSS元素的宽度和高度属性时，你只是设置内容区域的宽度和高度。要知道，完全大小的元素，你还必须添加填充，边框和边距。

下面的例子中的元素的宽实际大小为280px, 实际占据的尺寸为300px

```css
div {
  width:250px;
  padding:10px;
  border:5px solid gray;
  margin:10px;
}
```

## 盒子的实际大小为

- 宽度 = content.width + padding.left + padding.right + border.left + border.right

- 高度 = content.height + padding.top + padding.bottom + border.top + border.bottom

## 而盒子需要占据的尺寸为

- 宽度 = content.width + padding.left + padding.right + border.left + border.right + margin.left + margin.right

- 高度 = content.height + padding.top + padding.bottom + border.top + border.bottom + margin.top + margin.bottom

# CSS 盒模型属性列表

| 属性 | 描述 |
| :--- | :--- |
| **`margin`** | 所有四个（**上下左右**）方向的**元素的外边距**。这是四个外边距属性的简写。可以为负值 |
| **`margin-top`** | 元素的**顶部外边距** |
| **`margin-right`** | 元素的**右外边距** |
| **`margin-bottom`** | 元素的**底部外边距** |
| **`margin-left`** | 元素的**左侧区域** |
| **`padding`** | 所有四个（**上下左右**）方向的**元素的内边距**，内边距区域指一个**元素的内容**和**其边界之间的空间**，该属性**不能为负值** |
| **`padding-top`** | 元素的**上方内边距** |
| **`padding-right`** | 元素的**右内边距** |
| **`padding-bottom`** | 元素的**下方内边距** |
| **`padding-left`** | 元素的**左内边距** |
| **`border`** | 设置各种**单独的边界**的简写属性 |
| **`border-width`** | 设置盒子模型的**边框宽度**。 |
| **`border-style`** | 用来设定元素所有**边框样式** |
| **`border-color`** | 是一个用于设置元素**四个边框颜色** |
| **`border-top`** | 描述一个元素的**上方的边框**，是 `border-top-color`, `border-top-style`, 和 `border-top-width` 的三个属性的缩写 |
| **`border-right`** | 描述一个元素的**右边的边框**，是 `border-right-color`, `border-right-style`, 和 `border-right-width`的三个属性的缩写 |
| **`border-bottom`** | 描述了元素的**下边框样式**，是`border-bottom-color`，`border-bottom-style` 和 `border-bottom-width` 的三个属性的缩写 |
| **`border-left`** | 描述一个元素的**左边的边框**，是 `border-left-color`, `border-left-style`, 和`border-left-width`的三个属性的缩写 |

## `margin` 和 `padding` 属性值

接受1~4个可选属性值，每个属性值取值如下：

- **只有一个** 值时，这个值会被指定给全部的 **四个边**.
- **两个** 值时，第一个值被匹配给 **上和下**, 第二个值被匹配给 **左和右**.
- **三个** 值时，第一个值被匹配给 **上**, 第二个值被匹配给 **左和右**, 第三个值被匹配给 **下**.
- **四个** 值时，会依次按 **上、右、下、左** 的顺序匹配 (即顺时针顺序).

### 共有属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 指定一个固定的填充值。|
| **`%`** | 基于父元素值的百分比填充。|

!!! warn "`margin` 和 `padding` 属性值的不同"
    **`margin`** 的 **length** 和 **`%`** 属性值可以为负值; **`padding`** 的 **length** 和 **`%`** 不能为负值。

### `margin` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 浏览器会自动选择一个合适的`margin`来应用。它可以用于将一个块居中。|

## `border` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| *border-width* | 指定边框的**宽度** |
| *border-style* | 指定边框的**样式** |
| *border-color* | 指定边框的**颜色** |
| **`inherit`** | 指定应该从父元素继承`border`属性值 |

### `border-width` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`thin`** | **细的边框** |
| **`medium`** | 默认。**中等的边框** |
| **`thick`** | **粗的边框** |
| length | **自定义**边框的宽度 |
| **`inherit`** | 规定应该从父元素继承边框宽度 |

### `border-style` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 定义无边框 |
| **`hidden`** | 与 **`none`** 相同。不过应用于表时除外，对于表，`hidden` 用于解决边框冲突。|
| **`dotted`** | **点状边框** |
| **`dashed`** | **虚线** |
| **`solid`** | **实线** |
| **`double`** | **双线** |
| **`groove`** | 显示为有**雕刻效果的边框** |
| **`ridge`** | 显示为有**浮雕效果的边框** |
| **`inset`** | 显示为有**陷入效果的边框** |
| **`outset`** | 显示为有**突出效果的边框** |
| **`inherit`** | 规定应该从父元素继承边框样式。|

### `border-color` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| color | 边框的颜色, 在 [CSS 颜色](/zh-hans/webfrontend/css_color) 查找颜色值的完整列表 |
| **`transparent`** | 指定边框的颜色是**透明的**。这是默认 |
| **`inherit`** | 从父元素继承 |

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
