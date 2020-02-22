TOPICS: letter-spacing property

# CSS 属性: `letter-spacing`

CSS 的 `letter-spacing` 属性明确了**文字的间距**行为。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| `normal` | 默认。规定字符间没有额外的空间。|
| `length` | 定义字符间的固定空间（允许使用负值）。|
| `inherit` | 规定应该从父元素继承的值。|

## 示例

```html
<p class="first-example"> letter spacing </p>
<p class="second-example"> letter spacing </p>
<p class="third-example"> letter spacing </p>
<p class="fourth-example"> letter spacing </p>
```

```css
.first-example { letter-spacing: 0.4em; }
.second-example { letter-spacing: 1em; }
.third-example { letter-spacing: -0.05em; }
.fourth-example { letter-spacing: 6px; }
```
