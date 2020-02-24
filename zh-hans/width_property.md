TOPICS: width property

# CSS 属性: `width`

**`width`** 属性指定了元素内容区的宽度. 内容区在元素`padding`，`border`和`margin`里面。

`min-width` 和 `max-width` 属性覆盖 `width`.

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| `length` | 可能的长度单位见 `<length>` |
| `percentage` | 指定为包含块宽度的 `<percentage>` |
| `auto` | 浏览器将会为指定的元素计算并选择一个宽度. |
| `max-content` | 固有的首选宽度. |
| `min-content` | 固有的最小宽度. |

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
