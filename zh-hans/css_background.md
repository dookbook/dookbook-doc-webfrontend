TOPICS: background property
        background-clip property
        background-color property
        background-image property
        background-origin property
        background-position property
        background-repeat property
        background-size property
        background-attachment property
        background-blend-mode property

# CSS 背景 (`background`)

CSS 允许应用**纯色作为背景**，也允许使用**背景图像创建相当复杂的效果**。

CSS 在这方面的能力远远在 HTML 之上。

## CSS 背景属性

| 属性 | 描述 |
| :--- | :--- |
| **`background`** | **简写属性**，用于一次性**集中定义各种背景属性** |
| **`background-clip`** | 设置元素的**背景图片或颜色是否延伸到边框下面** |
| **`background-color`** | 设置**元素的背景色**, 属性的值为 **颜色值** 或 **关键字 `transparent`** 二者选其一 |
| **`background-image`** | 设置要使用的**一个**或**多个背景图像** |
| **`background-origin`** | 设置**背景图像的定位区域** |
| **`background-position`** | 为每一个背景图片**设置初始位置**。这个位置是相对于由 *`background-origin`* 定义的位置图层的 |
| **`background-repeat`** | 定义**背景图像的重复方式**。背景图像可以沿着**水平轴**，**垂直轴**，**两个轴重复**，或者**根本不重复** |
| **`background-size`** | 设置**背景图片大小**。图片可以保有其原有的尺寸，或者拉伸到新的尺寸，或者在保持其原有比例的同时缩放到元素的可用空间的尺寸 |
| **`background-attachment`** | 决定背景图像的位置是在视口内固定，还是随着包含它的区块滚动 |
| **`background-blend-mode`** | 设置元素的**背景图像如何相互融合以及元素的背景色**。 |

## `background-clip` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`border-box`** | 默认值。背景延伸至边框外沿（但是在边框下层）。|
| **`padding-box`** | 背景延伸至内边距外沿。不会绘制到边框处。 |
| **`content-box`** | 背景被裁剪至内容区外沿。|

## `background-color` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| color | 指定**背景颜色**。详见[CSS 颜色](/zh-hans/webfrontend/css_color)。|
| **`transparent`** | 指定背景颜色应该是**透明的**。这是默认 |

## `background-image` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **url('URL')** | **图像的URL** |
| **`none`** | **不会显示图像背景**。这是默认 |

## `background-origin` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`padding-box`** | 背景图片的摆放以 **`border`** 区域为参考 |
| **`border-box`** | 背景图片的摆放以 **`padding`** 区域为参考 |
| **`content-box`** | 背景图片的摆放以 **`content`** 区域为参考 |

## `background-position` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`left`**,**`top`**<br>**`left`**,**`center`**<br>**`left`**,**`bottom`**<br>**`right`**, **`top`**<br>**`right`**,**`center`**<br>**`right`**,**`bottom`**<br>**`center`**,**`top`**<br>**`center`**,**`center`**<br>**`center`**,**`bottom`** | 如果仅指定一个关键字，其他值将会是 **`center`**; <br>比如: `background-position:top;` 将等同于 `background-position:top center;`|
| `x%`,`y%` | 第一个值是**水平**位置，第二个值是**垂直**。左上角是`0％ 0％`。右下角是`100％ 100％`。如果仅指定了一个值，其他值将是`50％`。默认值为：`0％ 0％` |
| `xpos`,`ypos` | 第一个值是**水平**位置，第二个值是**垂直**。左上角是`0`。单位可以是像素（`0px 0px`）或任何其他[CSS单位](/zh-hans/webfrontend/css_length_unit)。如果仅指定了一个值，其他值将是`50％`。你可以混合使用`％`和`positions` |
| **`inherit`** | 从父元素继承 |

## `background-repeat` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`repeat`** | 背景图像将向**垂直**和**水平方向重复**。这是默认 |
| **`repeat-x`** | 只有**水平位置会重复**背景图像 |
| **`repeat-y`** | 只有**垂直位置会重复**背景图像 |
| **`no-repeat`** | 不会重复 |
| **`inherit`** | 从父元素继承 |

## `background-size` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 设置背景图片**高度**和**宽度**。**第一个**值设置**宽度**，**第二个**值设置的**高度**。如果只给出一个值，第二个是设置为 **`auto`**(自动) |
| **`%`** | 将计算相对于背景定位区域的**百分比**。**第一个**值设置**宽度**，**第二个**值设置的**高度**。如果只给出一个值，第二个是设置为 **`auto`**(自动) |
| **`cover`** | 此时会保持图像的**纵横比**并将图像缩放成将**完全覆盖背景定位区域**的**最小大小** |
| **`contain`** | 此时会保持图像的**纵横比**并将图像缩放成将**适合背景定位区域**的**最大大小** |

## `background-attachment` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`scroll`** | 背景图片随页面的**其余部分滚动**。这是默认 |
| **`fixed`** | 背景图像是**固定的** |
| **`inherit`** | 从父元素继承 |

## `background-blend-mode` 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 默认值。设置**正常的混合**模式。|
| **`multiply`** | **正片叠底**模式。|
| **`screen`** | **滤色**模式。|
| **`overlay`** | **叠加**模式。|
| **`darken`** | **变暗**模式。|
| **`lighten`** | **变亮**模式。|
| **`color-dodge`** | **颜色减淡**模式。|
| **`saturation`** | **饱和度**模式。|
| **color** | **颜色**模式。|
| **`luminosity`** | **亮度**模式。|

## 示例

```css
div {
  border:1px solid black;
  padding: 30px;
  height: 200px;
  background-image: url('sealing.png'); /* 给div加上面背景图片 */
  background-repeat: no-repeat; /* 图片不平铺 */
  background-position: left top; /* 图片位于左上方 */
  background-origin: content-box; /* 规定图片在内容区域 */
  background-clip: padding-box; /* 裁剪背景在 */
  background-attachment: fixed; /* 图片将不会跟着内容滚动, 使用该属性时 background-origin 属性则没有效果 */
  background-size: 100px; /* 设置图片大小为100px */
  background-color:rgb(255, 0, 0); /* 设置背景颜色 */
  background-blend-mode: multiply; /* 设置图片正片叠底 */
}
```

```html
<div>Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.</div>
```
