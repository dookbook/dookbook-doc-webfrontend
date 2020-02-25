TOPICS: letter-spacing property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `letter-spacing`

CSS 属性 **`letter-spacing`** 设置**文本字符之间的间距**行为。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 此间距是按照当前字体的正常间距确定的。和 `0` 不同的是，用户代理根据此属性来确定文字的默认对齐方式。 |
| length | 指定文字间的间距以替代默认间距。可以是负值，但有可能会出现 `implementation` 限制。用户代理不会在此基础上进一步增加或缩减间距来对齐文字。|

## 示例

```css
.normal   { letter-spacing: normal; }
.em-wide  { letter-spacing: 0.4em; }
.em-wider { letter-spacing: 1em; }
.em-tight { letter-spacing: -0.05em; }
.px-wide  { letter-spacing: 6px; }
```

```html
<p class="normal">letter spacing</p>
<p class="em-wide">letter spacing</p>
<p class="em-wider">letter spacing</p>
<p class="em-tight">letter spacing</p>
<p class="px-wide">letter spacing</p>
```
