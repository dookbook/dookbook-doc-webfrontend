TOPICS: transform property
        transform-style property
        transform-origin property
        transform-box property
        perspective property
        perspective-origin property
        backface-visibility property
        translate property

# CSS 2D/3D 转换属性 (`transform`)

## CSS 属性 `transform`

CSS **`transform`** 属性允许你**旋转**，**缩放**，**倾斜**或**平移**给定元素。这是通过修改CSS视觉格式化模型的坐标空间来实现的。

!!! warn "注意"
    只能转换由盒子模型定位的元素。根据经验，如果元素具有`display: block`，则由盒模型定位元素。

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 不应用任何变换 |
| **`matrix(n,n,n,...)`** | 定义 2D 转换，使用六个值的矩阵 |
| **`matrix3d(n,n,n,...)`** | 定义 3D 转换，使用 16 个值的 4x4 矩阵 |
| **`translate(x,y)`** | 定义 2D 转换 |
| **`translate3d(x,y,z)`** | 定义 3D 转换 |
| **`translateX(x)`** | 定义转换，只是用 X 轴的值 |
| **`translateY(y)`** | 定义转换，只是用 Y 轴的值 |
| **`translateZ(z)`** | 定义 3D 转换，只是用 Z 轴的值 |
| **`scale(x[,y]?)`** | 定义 2D 缩放转换 |
| **`scale3d(x,y,z)`** | 定义 3D 缩放转换 |
| **`scaleX(x)`** | 通过设置 X 轴的值来定义缩放转换 |
| **`scaleY(y)`** | 通过设置 Y 轴的值来定义缩放转换 |
| **`scaleZ(z)`** | 通过设置 Z 轴的值来定义 3D 缩放转换 |
| **`rotate(angle)`** | 定义 2D 旋转，在参数中规定角度 |
| **`rotate3d(x,y,z,angle)`** | 定义 3D 旋转 |
| **`rotateX(angle)`** | 定义沿着 X 轴的 3D 旋转 |
| **`rotateY(angle)`** | 定义沿着 Y 轴的 3D 旋转 |
| **`rotateZ(angle)`** | 定义沿着 Z 轴的 3D 旋转 |
| **`skew(x-angle,y-angle)`** | 定义沿着 X 和 Y 轴的 2D 倾斜转换 |
| **`skewX(angle)`** | 定义沿着 X 轴的 2D 倾斜转换 |
| **`skewY(angle)`** | 定义沿着 Y 轴的 2D 倾斜转换 |
| **`perspective(n)`** | 为 3D 转换元素定义透视视图 |

## CSS 属性: `transform-style`

CSS 属性 **`transform-style`** 设置元素的子元素是位于**3D空间中**还是**平面中**。

如果选择平面，元素的子元素将不会有 3D 的遮挡关系。

由于这个属性**不会被继承**，因此必须为元素的所有非叶子子元素设置它。

| 属性值 | 描述 |
| :--- | :--- |
| **`flat`** | 设置元素的子元素位于该元素的**平面中** |
| **`preserve-3d`** | 指示元素的子元素应位于**3D空间中** |

## CSS 属性: `transform-origin`

**`transform-origin`** CSS属性让你更改一个元素**变形的原点**。

转换起点是应用转换的点。例如，*`rotate()`*函数的转换原点是旋转中心。（这个属性的应用原理是先用这个属性的赋值转换该元素，进行变形，然后再用这个属性的值把元素转换回去）

`transform-origin`属性可以使用一个，两个或三个值来指定，其中每个值都表示一个偏移量。 没有明确定义的偏移将重置为其对应的初始值。

如果定义了两个或更多值并且没有值的关键字，或者唯一使用的关键字是`center`，则第一个值表示**水平偏移量**，第二个值表示**垂直偏移量**。

- 一个值：
    - 必须是长度，百分比或 `left`, `center`, `right`, `top`, `bottom`关键字中的一个。
- 两个值：
    - 其中一个必须是长度，百分比或`left`, `center`, `right`关键字中的一个。
    - 另一个必须是长度，百分比或`top`, `center`, `bottom`关键字中的一个。
- 三个值：
    - 前两个值和只有两个值时的用法相同。
    - 第三个值必须是长度。它始终代表Z轴偏移量。

| 属性值 | 描述 |
| :--- | :--- |
| **x-offset** | 定义变形中心距离盒模型的左侧的长度或百分比偏移值 |
| **offset-keyword** | `left`，`right`，`top`，`bottom`或`center`中之一，定义相对应的变形中心偏移 |
| **y-offset** | 定义变形中心距离盒模型的顶的长度或百分比偏移值 |
| **x-offset-keyword** | `left`，`right`或`center`中之一，定义相对应的变形中心偏移 |
| **y-offset-keyword** | `top`，`bottom`或`center`中之一，定义相对应的变形中心偏移 |
| **z-offset** | 定义变形中心距离用户视线（`z=0`处）的长度（不能是百分比）偏移值 |

关键字是方便的简写方法，等同于以下百分比值：

| 关键字 | 值 |
| --- | --- |
| `left` | `0%` |
| `center` | `50%` |
| `right` | `100%` |
| `top` | `0%` |
| `bottom` | `100%` |

# CSS 属性: `transform-box`

**`transform-box`** 属性定义了与 *`transform`*、*`transform-origin`* 这两个属性有关联的布局框。

| 属性值 | 描述 |
| :--- | :--- |
| `border-box` | 边框是用作引用框，一个表格的`border-box`是表格包装盒的边框，而不是表的边框 |
| `fill-box` | 使用对象包围框作为引用框 |
| `view-box` | 使用最近的SVG视图作为参考框。如果为SVG视口创建元素指定了`viewBox`属性，则将引用框定位在`viewBox`属性建立的坐标系的原点，并将引用框的维数设置为`viewBox`属性的宽度和高度值 |

## CSS 属性: `perspective`

CSS 属性 **`perspective`** 指定了3D元素是如何查看透视图

| 属性值 | 描述 |
| :--- | :--- |
| **number** | 元素距离视图的距离，以像素计 |
| **`none`** | 默认值。与 `0` 相同。不设置透视 |

## CSS 属性: `perspective-origin`

CSS 属性 **`perspective-origin`** 指定 3D 元素所基于的**X轴**和**Y轴**。该属性允许您改变 3D 元素的底部位置。

| 属性值 | 描述 |
| :--- | :--- |
| **x-position** | 指定消失点的**横坐标** |
| **y-position** | 指定消失点的**纵坐标** |

## CSS 属性: `backface-visibility`

CSS 属性 **`backface-visibility`** 指定当元素**背面朝向观察者时是否可见**。

元素的背面是**其正面的镜像**。虽然在 2D 中不可见，但是当变换导致元素在 3D 空间中旋转时，背面可以变得可见。（此属性对 2D 变换没有影响，它没有透视。）

| 属性值 | 说明 |
| :--- | :--- |
| **`visible`** | 背面朝向用户时**可见** |
| **`hidden`** | 背面朝向用户时**不可见** |

## CSS 属性: `translate`

CSS 属性 **`translate`** 允许你单独指定 *`transforms`* 中的平移，并独立于 *`transform`* 属性。这可以更好地反映到典型的用户界面用法，并节省了在指定`transform`
值时必须记住的转换函数的确切顺序。

!!! warn "注意"
    目前只有火狐支持该属性

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 表示平移效果没有被应用 |
| 一个长度/百分比值 | 一个长度值或百分比**表示X轴**和**Y轴**使用一样的值进行**二维上的平移**。等同于 `translate()`（2D 平移）函数指定单个值 |
| 两个长度/百分比值 | 两个长度值或百分比表示在**二维上**分别按照指定**X轴**和**Y轴**的值**进行的平移**。等同于 `translate()`（2D 平移）函数指定两个值 |
| 三个长度/百分比值 | 三个长度值或百分比表示在**三维上**分别按照指定**X轴**、**Y轴**、**Z轴**的值**进行的平移**。等同于 `translate3d()`（3D 平移）函数 |

## 示例

```css
.showbf div {
  backface-visibility: visible; /* 指定背面朝向为可见 */
}

.container {
  width: 150px;
  height: 150px;
  margin: 75px 0 0 75px;
  border: none;
}

.cube {
  width: 100%;
  height: 100%;
  perspective: 550px; /* 指定透视效果为550px */
  perspective-origin: 150% 150%; /* 指定观察的X轴和Y轴各为150%的位置 */
  transform-style: preserve-3d; /* 指定子元素位于3D空间中 */
}

.face {
  display: block;
  position: absolute;
  width: 100px;
  height: 100px;
  border: none;
  line-height: 100px;
  font-family: sans-serif;
  font-size: 60px;
  color: white;
  text-align: center;
}

.front {
  background: rgba(0, 0, 0, 0.3);
  transform: translateZ(50px); /* 定义3D转换，Z轴为50px */
}

.back {
  background: rgba(0, 255, 0, 1);
  color: black;
  transform: rotateY(180deg) translateZ(50px); /* 定义3D转换，Y轴为180度，Z轴为50px */
}

.right {
  background: rgba(196, 0, 0, 0.7);
  transform: rotateY(90deg) translateZ(50px); /* 定义3D转换，Y轴为90度，Z轴为50px */
}

.left {
  background: rgba(0, 0, 196, 0.7);
  transform: rotateY(-90deg) translateZ(50px); /* 定义3D转换，Y轴为-90度，Z轴为50px */
}

.top {
  background: rgba(196, 196, 0, 0.7);
  transform: rotateX(90deg) translateZ(50px); /* 定义3D转换，X轴为90度，Z轴为50px */
}

.bottom {
  background: rgba(196, 0, 196, 0.7);
  transform: rotateX(-90deg) translateZ(50px); /* 定义3D转换，X轴为-90度，Z轴为50px */
}
```

```html
<div class="container">
  <div class="cube showbf">
    <div class="face front">1</div>
    <div class="face back">2</div>
    <div class="face right">3</div>
    <div class="face left">4</div>
    <div class="face top">5</div>
    <div class="face bottom">6</div>
  </div>
</div>
```

### 示例: 使用 `translate` 属性

```css
div {
  width: 150px;
  margin: 0 auto;
  background:#ff0;
}

p {
  padding: 10px 5px;
  border: 3px solid black;
  border-radius: 20px;
  font-size: 1.2rem;
  text-align: center;
}

.translate {
  transition: translate 1s;
}

div:hover .translate {
  translate: 200px 50px;
}
```

```html
<div>
  <p class="translate">Translation</p>
</div>
```
