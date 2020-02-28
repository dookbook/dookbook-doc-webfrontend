TOPICS: width property

# CSS 属性: `width`

**`width`** 属性设置**元素的宽度**。 默认情况下，它设置**内容区域的宽度**，但是如果 **`box-sizing`** 设置为 **`border-box`**，它则是**边框区域的宽度**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 使用 **`px`**、**`rem`**、**`em`** 等单位定义宽度 |
| **`%`** | 定义基于包含块（父元素）宽度的百分比宽度 |
| **`auto`** | 默认值。浏览器可计算出实际的宽度 |
| **`inherit`** | 规定应该从父元素继承 `width` 属性的值 |

## 示例：默认宽度

```css
p.goldie {
  background: gold;
}
```

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

## 示例：`px` 和 `em`

```css
.px_length {
  width: 200px;
  background-color: red;
  color: white;
  border: 1px solid black;
}

.em_length {
  width: 20em;
  background-color: white;
  color: red;
  border: 1px solid black;
}
```

```html
<div class="px_length">以 px 度量的宽度</div>
<div class="em_length">以 em 度量的宽度</div>
```

## 示例：百分比

```css
.percent {
  width: 20%;
  background-color: silver;
  border: 1px solid red;
}
```

```html
<div class="percent">按照百分比度量的宽度</div>
```

## 示例：`max-content`

```css
p.maxgreen {
  background: lightgreen;
  width: intrinsic;           /* Safari/WebKit 使用了非标准的名称 */
  width: -moz-max-content;    /* Firefox/Gecko */
  width: -webkit-max-content; /* Chrome */
}
```

```html
<p class="maxgreen">The Mozilla community produces a lot of great software.</p>
```

## 示例：`min-content`

```css
p.minblue {
  background: lightblue;
  width: -moz-min-content;    /* Firefox */
  width: -webkit-min-content; /* Chrome */
}
```

```html
<p class="minblue">The Mozilla community produces a lot of great software.</p>
```
