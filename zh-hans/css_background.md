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

| 属性 | 描述 | 语法 |
| :--- | :--- | :--- |
| **`background`** | **简写属性**，用于一次性**集中定义各种背景属性** 。| `background:bg-color bg-image position/bg-sizebg-repeat bg-origin bg-clip bg-attachment initial|inherit;`(可根据情况选择性省略)|
| **`background-clip`** | 设置元素的**背景图片或颜色是否延伸到边框下面**。 | `background-clip: border-box|padding-box|content-box;`|
| **`background-color`** | 设置**元素的背景色**, 属性的值为 **颜色值** 或 **关键字 `transparent`**（*默认属性值*。指定背景颜色应该是**透明的**。） 二者选其一。 |`background-color: color/transparent|inherit;`|
| **`background-image`** | 设置要使用的**一个**或**多个背景图像** 。|`border-image: url（'URL'）;`（多背景用逗号隔开)|
| **`background-origin`** | 设置**背景图像的定位区域** 。 |`background-origin: padding-box(相对于内边距框来定位。)|border-box(相对于边框盒来定位。)|content-box(相对于内容框来定位。);`|
| **`background-position`** | 为每一个背景图片**设置初始位置**。这个位置是相对于由 *`background-origin`* 定义的位置图层的 。| `background-position:position;`(详情请看下文）|
| **`background-repeat`** | 定义**背景图像的重复方式**。背景图像可以沿着**水平轴**，**垂直轴**，**两个轴重复**，或者**根本不重复** 。|`background-repeat:repeat(默认值，垂直水平两个方向重复)|repeat-x（只水平位置会重复）|repeat-y（只垂直位置会重复）|no-repeat（不会重复）|inherit（从父元素继承）；`|
| **`background-size`** | 设置**背景图片大小**。图片可以保有其原有的尺寸，或者拉伸到新的尺寸，或者在保持其原有比例的同时缩放到元素的可用空间的尺寸。 |`background-size: length|percentage|cover|contain;`(详情请看下文）|
| **`background-attachment`** | 决定背景图像的位置是在视口内固定，还是随着包含它的区块滚动。|`background-attachment:scroll(默认值，背景图片随页面的其余部分滚动而移动）|fixed（背景图像是固定的）|inherit;`|
| **`background-blend-mode`** | 设置元素的**背景图像如何相互融合以及元素的背景色**。 |`background-blend-mode: normal|multiply|screen|overlay|darken|lighten|color-dodge|saturation|color|luminosity;`(详情请看下文）|

## `background-clip` 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`border-box`** | 默认值。背景延伸至边框外沿（但是在边框下层）。|
| **`padding-box`** | 背景延伸至内边距外沿。不会绘制到边框处。 |
| **`content-box`** | 背景被裁剪至内容区外沿。|

## `background-image` 属性值

| 属性值 |  描述 |
| :--- | :--- |
| **url('URL')** | **图像的URL** |
| **`none`** | **不会显示图像背景**。这是默认 |
| `linear-gradient()` | 函数用于创建一个线性渐变的 "图像"。语法：`background-image: linear-gradient(direction(角度), color-stop1, color-stop2, ...);`|
| `radial-gradient()` |径向渐变创建 "图像"。值：<br> *`shape`* 圆的类型。 `ellipse` (默认): 指定椭圆形的径向渐变。`circle` ：指定圆形的径向渐变。<br> *`size`* 定义渐变的大小，可能值：`farthest-corner` (默认): 指定径向渐变的半径长度为从圆心到离圆心最远的角。`closest-side`：指定径向渐变的半径长度为从圆心到离圆心最近的边。`closest-corner`：指定径向渐变的半径长度为从圆心到离圆心最近的角。`farthest-side`指定径向渐变的半径长度为从圆心到离圆心最远的边。<br> `position` 定义渐变的位置。可能值：`center`（默认）：设置中间为径向渐变圆心的纵坐标值。`top`：设置顶部为径向渐变圆心的纵坐标值。`bottom`：设置底部为径向渐变圆心的纵坐标值。<br>`start-color, ..., last-color`用于指定渐变的起止颜色。|
| `repeating-radial-gradient()` | 函数用于创建重复的径向渐变 "图像"。它的可能的值与`radial-gradient()`一样。|
| `repeating-linear-gradient()`| 函数用于创建重复的线性渐变 "图像"。值：<br>`angle` 定义渐变的角度方向。从 0deg 到 360deg，默认为 180deg。<br> `side-or-corner` 指定线性渐变的起始位置。由两个关键字组成：第一个为指定水平位置(`left` 或 `right`)，第二个为指定垂直位置（`top` 或`bottom`）。顺序是随意的，每个关键字都是可选的。<br>`start-color, ..., last-color` 指定渐变的起止颜色，由颜色值、停止位置（可选，使用百分比指定）组成。|
 `inherit` | 指定背景颜色，应该从父元素继承。(很少使用)|

## `background-position` 属性值

| 属性值 |  描述 |
| :--- | :--- |
| **`left`**,**`top`**<br>**`left`**,**`center`**<br>**`left`**,**`bottom`**<br>**`right`**, **`top`**<br>**`right`**,**`center`**<br>**`right`**,**`bottom`**<br>**`center`**,**`top`**<br>**`center`**,**`center`**<br>**`center`**,**`bottom`** | 如果仅指定一个关键字，其他值将会是 **`center`**; <br>比如: `background-position:top;` 将等同于 `background-position:top center;`|
| `x%`,`y%` | 第一个值是**水平**位置，第二个值是**垂直**。左上角是`0％ 0％`。右下角是`100％ 100％`。如果仅指定了一个值，其他值将是`50％`。默认值为：`0％ 0％` |
| `xpos`,`ypos` | 第一个值是**水平**位置，第二个值是**垂直**。左上角是`0`。单位可以是像素（`0px 0px`）或任何其他[CSS单位](/zh-hans/webfrontend/css_length_unit)。如果仅指定了一个值，其他值将是`50％`。你可以混合使用`％`和`positions` |
| **`inherit`** | 从父元素继承。 |

## `background-size` 属性值

| 属性值 |  描述 |
| :--- | :--- |
| length | 设置背景图片**高度**和**宽度**。**第一个**值设置**宽度**，**第二个**值设置的**高度**。如果只给出一个值，第二个是设置为 **`auto`**(自动) |
| **`%`** | 将计算相对于背景定位区域的**百分比**。**第一个**值设置**宽度**，**第二个**值设置的**高度**。如果只给出一个值，第二个是设置为 **`auto`**(自动) |
| **`cover`** | 此时会保持图像的**纵横比**并将图像缩放成将**完全覆盖背景定位区域**的**最小大小** |
| **`contain`** | 此时会保持图像的**纵横比**并将图像缩放成将**适合背景定位区域**的**最大大小** |

## `background-blend-mode` 属性值

| 属性值 |  描述 |
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
