TOPICS: outline property
        outline-style property
        outline-width property
        outline-color property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `outline`

CSS **`outline`** 属性是用来设置**一个**或**多个单独的轮廓**属性的简写属性，例如 **`outline-style`**、**`outline-width`** 和 **`outline-color`**。多数情况下，简写属性更加可取和便捷。

轮廓与边框在以下几个方面存在不同：

- 轮廓不占据空间，它们被描绘于内容之上。
- 轮廓可以是非矩形的。在Gecko/Firefox中，轮廓是矩形的，但是Opera则会围绕元素结构绘制非矩形的形状。

## CSS 属性: `outline-style`

CSS **`outline-style`** 属性被用于设置一个元素**轮廓的样式**。

元素轮廓是绘制于元素周围的一条线，位于`border`的外围，使元素突出。

大多时候使用 **`outline`** 简写属性会更方便，而不是 **`outline-style`**, **`outline-width`** 和 **`outline-color`**。

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认。定义**无轮廓**。|
| **`dotted`** | 定义**点状的轮廓**。|
| **`dashed`** | 定义**虚线轮廓**。|
| **`solid`** | 定义**实线轮廓**。|
| **`double`** | 定义**双线轮廓**。双线的宽度等同于 **`outline-width`** 的值。|
| **`groove`** | 定义 3D 凹槽轮廓。此效果取决于 **`outline-color`** 值。|
| **`ridge`** | 定义 3D 凸槽轮廓。此效果取决于 **`outline-color`** 值。|
| **`inset`** | 定义 3D 凹边轮廓。此效果取决于 **`outline-color`** 值。|
| **`outset`** | 定义 3D 凸边轮廓。此效果取决于 **`outline-color`** 值。|
| **`inherit`** | 规定应该从父元素继承轮廓样式的设置。|

## CSS 属性: `outline-width`

CSS **`outline-width`** 属性用于设置一个元素的**轮廓的宽度**。元素轮廓是绘制于元素周围的一条线，位于 **`border`** 的外围。

!!! warn "注意"
    请始终在 **`outline-width`** 属性之前声明 **`outline-style`** 属性。元素只有获得轮廓以后才能改变其轮廓的宽度。

| 属性值 | 说明 |
| :--- | :--- |
| **`thin`** | 规定**细轮廓**。|
| **`medium`** | 默认。规定**中等的轮廓**。|
| **`thick`** | 规定**粗的轮廓**。|
| **length** | 允许您规定**轮廓粗细的值**。|
| **`inherit`** | 规定应该从父元素继承轮廓宽度的设置。|

## CSS 属性: `outline-color`

CSS **`outline-color`** 属性 被用于设置一个元素轮廓的颜色.

| 属性值 | 说明 |
| :--- | :--- |
| **color** | 指定轮廓颜色。在[CSS颜色值](/zh-hans/webfrontend/CSS_color)寻找颜色值的完整列表。|
| **`invert`** | 默认。执行颜色反转（逆向的颜色）。可使轮廓在不同的背景颜色中都是可见。|
| **`inherit`** | 规定应该从父元素继承轮廓颜色的设置。|

## 简写示例

```css
/* 两个相同的声明 */
:link:hover { outline: 1px solid #000; }
:link:hover { outline: solid black 1px; }
```

## 使用 `outline-color` 属性

```html
<p>My outline is blue, as you can see.</p>
```

```css
p {
  outline: 2px solid;      /* 设置大纲宽度和样式 */
  outline-color: #0000FF;  /* 把轮廓画成蓝色 */
  margin: 5px;
}
```

### 使用 `outline-width` 属性

```css
span {
  outline-style: solid;
  display: inline-block;
  margin: 20px;
}

#thin {
  outline-width: thin;
}

#medium {
  outline-width: medium;
}

#thick {
  outline-width: thick;
}

#twopixels {
  outline-width: 2px;
}

#oneex {
  outline-width: 1ex;
}

#em {
  outline-width: 1.2em;
}
```

```html
<span id="thin">thin</span>
<span id="medium">medium</span>
<span id="thick">thick</span>
<span id="twopixels">2px</span>
<span id="oneex">1ex</span>
<span id="em">1.2em</span>
```
