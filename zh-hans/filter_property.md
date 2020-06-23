TOPICS: filter property

# CSS 属性: `filter`

CSS **`filter`** 属性将**模糊**或**颜色偏移**等图形效果应用于元素。滤镜通常用于调整图像，背景和边框的渲染。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认值，没有效果。 |
| **`blur(px)`** | 给图像设置高斯模糊。"radius"一值设定高斯函数的标准差，或者是屏幕上以多少像素融在一起，所以值越大越模糊；<br>如果没有设定值，则默认是`0`；这个参数可设置CSS长度值，但不接受百分比值。|
| **`brightness(%)`** | 给图片应用一种线性乘法，使其看起来更亮或更暗。如果值是`0%`，图像会全黑。值是`100%`，则图像无变化。其他的值对应线性乘数效果。值超过`100%`也是可以的，图像会比原来更亮。如果没有设定值，默认是`1`。|
| **`contrast(%)`** | 调整图像的对比度。值是0%的话，图像会全黑。值是`100%`，图像不变。值可以超过`100%`，意味着会运用更低的对比。若没有设置值，默认是`1`。|
| **`drop-shadow(h-shadow v-shadow blur spread color)`** | 给图像设置一个阴影效果。阴影是合成在图像下面，可以有模糊度的，可以以特定颜色画出的遮罩图的偏移版本。函数接受**shadow**(在CSS3背景中定义)类型的值，除了"inset"关键字是不允许的。该函数与已有的 **`box-shadow`** 属性很相似；不同之处在于，通过滤镜，一些浏览器为了更好的性能会提供硬件加速。**shadow**参数如下：<br><br>**offset-x** **offset-y** (必须)<br>这是设置阴影偏移量的两个 **length** 值。**offset-x** 设定水平方向距离。负值会使阴影出现在元素左边。 **offset-y** 设定垂直距离。负值会使阴影出现在元素上方。<br>如果两个值都是 `0`, 则阴影出现在元素正后面 (如果设置了 **blur-radius** 和/或 **spread-radius**，会有模糊效果)。<br><br>**blur-radius** (可选)<br>这是第三个**length**值。值越大，越模糊，则阴影会变得更大更淡。不允许负值 若未设定，默认是`0` (则阴影的边界很锐利)。<br><br>**spread-radius** (可选)<br>这是第四个**length**值。正值会使阴影扩张和变大，负值会是阴影缩小。若未设定，默认是`0` (阴影会与元素一样大小)。 <br>注意: WebKit, 以及一些其他浏览器 不支持第四个长度，如果加了也不会渲染。<br><br> **color** (可选)<br>若未设定，颜色值基于浏览器。在Gecko (Firefox), Presto (Opera)和Trident (Internet Explorer)中， 会应用`color`属性的值。另外, 如果颜色值省略，WebKit中阴影是透明的。|
| **`grayscale(%)`** | 将图像转换为灰度图像。值定义转换的比例。值为`100%`则完全转为灰度图像，值为`0%`图像无变化。值在`0%`到`100%`之间，则是效果的线性乘子。若未设置，值默认是`0`。|
| **`hue-rotate(deg)`** | 给图像应用色相旋转。"angle"一值设定图像会被调整的色环角度值。值为`0deg`，则图像无变化。若值未设置，默认值是`0deg`。该值虽然没有最大值，超过`360deg`的值相当于又绕一圈。|
| **`invert(%)`** | 反转输入图像。值定义转换的比例。`100%`的价值是完全反转。值为`0%`则图像无变化。值在`0%`和`100%`之间，则是效果的线性乘子。若值未设置，值默认是`0`。|
| **`opacity(%)`** | 转化图像的透明程度。值定义转换的比例。值为`0%`则是完全透明，值为`100%`则图像无变化。值在`0%`和`100%`之间，则是效果的线性乘子，也相当于图像样本乘以数量。 若值未设置，值默认是`1`。该函数与已有的 **`opacity`** 属性很相似，不同之处在于通过`filter`，一些浏览器为了提升性能会提供硬件加速。|
| **`saturate(%)`** | 转换图像饱和度。值定义转换的比例。值为`0%`则是完全不饱和，值为`100%`则图像无变化。其他值，则是效果的线性乘子。超过`100%`的值是允许的，则有更高的饱和度。 若值未设置，值默认是`1`。|
| **`sepia(%)`** | 将图像转换为深褐色。值定义转换的比例。值为`100%`则完全是深褐色的，值为`0%`图像无变化。值在`0%`到`100%`之间，则是效果的线性乘子。若未设置，值默认是`0`。|
| **`url()`** | URL函数接受一个XML文件，该文件设置了 一个SVG滤镜，且可以包含一个锚点来指定一个具体的滤镜元素。<br>例如：`filter: url(SVG-url#element-id)`。 |
| **`initial`** | 设置属性为默认值。|
| **`inherit`** | 从父元素继承该属性。|

## 示例

```html
<img src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="blur" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="brightness" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="contrast" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="grayscale" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="huerotate" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="invert" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="opacity" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="saturate" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="sepia" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
<img class="shadow" src="pineapple.jpg" alt="Pineapple" width="300" height="300">
```

```css
img {
  width: 33%;
  height: auto;
  float: left;
}

.blur {
  -webkit-filter: blur(4px);
  filter: blur(4px);
}

.brightness {
  -webkit-filter: brightness(0.30);
  filter: brightness(0.30);
}

.contrast {
  -webkit-filter: contrast(180%);
  filter: contrast(180%);
}

.grayscale {
  -webkit-filter: grayscale(100%);
  filter: grayscale(100%);
}

.huerotate {
  -webkit-filter: hue-rotate(180deg);
  filter: hue-rotate(180deg);
}

.invert {
  -webkit-filter: invert(100%);
  filter: invert(100%);
}

.opacity {
  -webkit-filter: opacity(50%);
  filter: opacity(50%);
}

.saturate {
  -webkit-filter: saturate(7);
  filter: saturate(7);
}

.sepia {
  -webkit-filter: sepia(100%);
  filter: sepia(100%);
}

.shadow {
  -webkit-filter: drop-shadow(8px 8px 10px green);
  filter: drop-shadow(8px 8px 10px green);
}
```
