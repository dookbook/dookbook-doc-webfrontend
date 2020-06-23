TOPICS: opacity property

# CSS 透明度属性: `opacity`

CSS **`opacity`** 属性指定了**一个元素的透明度**。

当 **`opacity`** 属性的值应用于某个元素上时，是把这个元素（包括它的内容）当成一个整体看待，即使这个值没有被子元素继承。因此，一个元素和它包含的子元素都会具有和元素背景相同的透明度，
哪怕这个元素和它的子元素有不同的 **`opacity`** 属性值。

使用 **`opacity`** 属性，当属性值不为 **`1`** 时，会把元素放置在一个新的层叠上下文中。

## 属性值

**number** 是一个 **`0.0`** 到 **`1.0`** 范围内的数字值，这个数值既包含也代表通道的透明度，也就是alpha通道的值。任何一个溢出这个取值区间的值，尽管有效，但会被解析为在取值范围内最靠近它的值。

| 属性值 | 说明 |
| :--- | :--- |
| **`0`** | 元素完全透明 (即元素不可见)。任何一个位于`0.0`-`1.0`之间的数值。 |
| **`1`** | 元素完全不透明(即元素后面的背景不可见)。 |

## 基本示例

```css
div { background-color: yellow; }

.light {
  opacity: 0.2;
}
.medium {
  opacity: 0.5;
}
.heavy {
  opacity: 0.9;
}
```

```html
<div class="light">You can barely see this.</div>
<div class="medium">This is easier to see.</div>
<div class="heavy">This is very easy to see.</div>
```

## `:hover` 时 `opacity` 的不同

```css
img.opacity {
  opacity: 1;
  filter: alpha(opacity=100); /* IE8和更低的 */
  zoom: 1; /* 触发“hasLayout”在ie7和更低 */
}

img.opacity:hover {
  opacity: 0.5;
  filter: alpha(opacity=50);
  zoom: 1;
}
```

```html
<img src="//developer.mozilla.org/media/img/mdn-logo.png"
     alt="MDN logo" width="128" height="146"
     class="opacity">
```
