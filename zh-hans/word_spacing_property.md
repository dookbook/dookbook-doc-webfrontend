TOPICS: word-spacing property
AUTHORS: Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         Teoli; teoli@mozilla.net; mdn:teoli

# CSS 属性: `word-spacing`

CSS 属性 **`word-spacing`** 用于**声明标签和单词直接的间距行为**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`normal`** | 正常的单词间距，由当前字体和/或浏览器定义。|
| length | 通过指定具体的额外间距来增加字体的单词间距。|
| **`%`** | 通过指定受影响字符的宽度的百分比的方式来增加的间距。|

## 示例

```css
#mozdiv1 {
  word-spacing: 15px;
}

#mozdiv2 {
  word-spacing: 5em;
}
```

```html
<div id="mozdiv1">Here are many words...</div>
<div id="mozdiv2">...and many more!</div>
```
