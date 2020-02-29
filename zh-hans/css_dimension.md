TOPICS: CSS Dimension
        width property
        min-width property
        max-width property
        height property
        min-height property
        max-height property

# CSS 尺寸

**CSS 尺寸** 属性允许你控制元素的**高度**和**宽度**。

## CSS 属性: `width`

**`width`** 属性设置**元素的宽度**。 默认情况下，它设置**内容区域的宽度**，但是如果 **`box-sizing`** 设置为 **`border-box`**，它则是**边框区域的宽度**。

| 属性值 | 说明 |
| :--- | :--- |
| length | 使用 **`px`**、**`rem`**、**`em`** 等单位定义宽度 |
| **`%`** | 定义基于包含块（父元素）宽度的百分比宽度 |
| **`auto`** | 默认值。浏览器可计算出实际的宽度 |
| **`inherit`** | 规定应该从父元素继承 `width` 属性的值 |

示例

```css
p.goldie {
  background: gold;
}
```

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

## CSS 属性: `min-width`

**`min-width`** 属性为给定**元素设置最小宽度**。它可以阻止 [**`width`**](/zh-hans/webfrontend/width) 属性的应用值小于
`min-width` 的值。

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最小宽度值。默认值：取决于浏览器。|
| `%` | 定义基于包含它的块级对象的百分比最小宽度。|

示例

```css
p {
  min-width:150px;
  background-color:yellow;
  width: 10px
}
```

```html
<!-- 这个段落的最小宽度设置为 150px -->
<p>min-width</p>
```

## CSS 属性: `max-width`

**`max-width`** 属性用来给**元素设置最大宽度值**. 如果 [**`width`**](/zh-hans/webfrontend/width)
属性的值比 `max-width` 属性的值还大, 则 [**`width`**](/zh-hans/webfrontend/width) 属性会失效.

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最大宽度值。|
| **`%`** | 定义基于包含它的块级对象的百分比最大宽度。|

在下面的例子里, `id` 为 `"child"` 的 [`<div>`](/zh-hans/webfrontend/<div>) 元素设置了 `width` 值, 使它的宽度与父元素
`"parent"` 相等(`100%`),但是 `max-width` 值限制了它最大宽度只能到`150px`.

```html
<div id="parent">
  <div id="child">
    The Mozilla community produces a lot of great software.
  </div>
</div>
```

```css
#parent { width: 300px; }

#child  {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```

## # CSS 属性: `height`

**`height`** CSS 属性指定了一个**元素的高度**。默认情况下，这个属性决定的是**内容区的高度**，但是，如果将 **`box-sizing`** 设置为
**`border-box`**, 这个属性决定的将是**边框区域的高度**。

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 默认。浏览器会计算出实际的高度。|
| length | 使用 `px`、`em` 等单位定义高度。|
| **`%`** | 基于包含它的块级对象的百分比高度。|

示例

```html
<div id="taller">I'm 50 pixels tall.</div>
<div id="shorter">I'm 25 pixels tall.</div>
<div id="parent">
  <div id="child">
    I'm half the height of my parent.
  </div>
</div>
```

```css
div {
  width: 250px;
  margin-bottom: 5px;
  border: 2px solid blue;
}

#taller {
  height: 50px;
}

#shorter {
  height: 25px;
}

#parent {
  height: 100px;
}

#child {
  height: 50%;
  width: 75%;
}
```

# CSS 属性: `min-height`

CSS属性 **`min-height`** 通常用来设置**一个元素的最小高度**。这个属性 `min-height` 不允许一个元素的高度
[**`height`**](/zh-hans/webfrontend/height_property) 小于这个元素指定的最小高度 `min-height`。

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最小高度。默认值是 `0`。|
| `%` | 定义基于包含它的块级对象的百分比最小高度。|

示例

```css
p {
  min-height:100px;
  background-color:yellow;
}
```

```html
<p>这段的最小高度设置为100 px。</p>
```

## CSS 属性: `max-height`

**`max-height`** 属性用来设置给定**元素的最大高度**. 如果 [**`height`**](/zh-hans/webfrontend/height)
属性的值比 `max-height` 属性的值还大, 则 [**`height`**](/zh-hans/webfrontend/height) 属性会失效.

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义元素的最大高度值。|
| **`%`** | 定义基于包含它的块级对象的百分比最大高度。|

示例

```css
p{
  height: 150px;
  max-height:50px;
  background-color:yellow;
}
```

```html
<p>这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。这一段的最大高度设置为50 px。</p>
```
