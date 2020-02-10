TOPICS: :active

# `:active`

**`:active`** CSS伪类匹配被用户激活的元素。它让页面能在浏览器监测到激活时给出反馈。当用鼠标交互时，它代表的是用户按下按键和松开按键之间的时间。`:active` 伪类通常用来匹配!!!tab!!!键交互。

```css
/* Selects any <a> that is being activated */
a:active {
  color: red;
}
```

`:active`伪类通常用于[`<a>`](/zh-hans/webfrontend/<a>) 和 [`<button>`](/zh-hans/webfrontend/<button>)元素。此伪类的其他常见目标包括包含已激活元素的元素，以及通过其关联的[`<label>`](/zh-hans/webfrontend/<label>)被激活的元素。

由`:active`伪类定义的样式将被具有至少相同特异性的任何后续链接相关的伪类（`:link`，`:hover`或`:visited`）覆盖。为了适当地设置链接样式，
请将`:active`规则放在所有其他与链接相关的规则之后，如LVHA-order所定义: `:link` — `:visited` — `:hover` — `:active`

!!! warn "注意"
    在具有多按键鼠标的系统上，CSS3 规定`:active`伪类必须仅应用于主按键；对于右手操作鼠标来说这是左键。

## 活动链接

```html
<p>本段包含一个链接：
  <a href="#">单击该链接时，它将变为红色。</a>
  单击该段落或链接时，该段落将显示为灰色背景。
</p>
```

```css
a:link { color: blue; }          /* Unvisited links */
a:visited { color: purple; }     /* Visited links */
a:hover { background: yellow; }  /* Hovered links */
a:active { color: red; }         /* Active links */

p:active { background: #eee; }   /* Active paragraphs */
```

## 活动表格元素

```html
<form>
  <label for="my-button">我的按钮：</label>
  <button id="my-button" type="button">尝试单击我或我的标签！</button>
</form>
```

```css
form :active {
  color: red;
}

form button {
  background: white;
}
```
