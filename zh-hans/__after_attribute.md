TOPICS: ::after (:after)
AUTHORS: Florian Scholz; fscholz@mozilla.net; mdn:fscholz
         xgqfrms; xgqfrms@github.com; github:xgqfrms
         水货; shuihuo@mozilla.net; mdn:shuihuo
         Dong WEI; FredWe@mozilla.net; mdn:FredWe
         Fan Sai Kuok; fskuok@mozilla.net; mdn:fskuok
         Teoli; teoli@mozilla.net; mdn:teoli
         紫云飞; ziyunfei@mozilla.net; mdn:ziyunfei

# CSS 属性: `::after` (`:after`)

CSS伪元素 **`::after`** 用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合`content`属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。

```css
/* Add an arrow after links */
a::after {
  content: "→";
}
```

!!! warn "注意"
    `::before`和`::after`生成的伪元素包含在元素的格式框中，因此不适用于[`<img>`](/zh-hans/webfrontend/<img>)之类的替换元素或[`<br>`](/zh-hans/webfrontend/<br>)元素。。

## 语法

```css
element:after  { style properties }  /* CSS2 语法 */

element::after { style properties }  /* CSS3 语法 */
```

!!! warn "注意"
     `::after`表示法是在CSS3中引入的，`::`符号是用来区分伪类和伪元素的。支持CSS3的浏览器同时也都支持CSS2中引入的表示法`:after`。

## 简单用法

让我们创建两个类：一个无趣的和一个有趣的。我们可以在每个段尾添加伪元素来标记他们。

```html
<p class="boring-text">这是些无聊的文字</p>
<p>这是不无聊也不有趣的文字</p>
<p class="exciting-text">在MDN上做贡献简单又轻松。
按右上角的编辑按钮添加新示例或改进旧示例！</p>
```

```css
.exciting-text::after {
  content: "<- 让人兴兴兴奋!";
  color: green;
}

.boring-text::after {
   content:    "<- 无聊!";
   color:      red;
}
```

## 装饰用法

我们几乎可以用想要的任何方法给 `content` 属性里的文字和图片的加上样式.

```html
<span class="ribbon">Notice where the orange box is.</span>
```

```css
.ribbon {
  background-color: #5BC8F7;
}

.ribbon::after {
  content: "Look at this orange box.";
  background-color: #FFBA10;
  border-color: black;
  border-style: dotted;
}
```

## 提示用法

接下来的示例展示了用`::after`伪元素，`attr()`CSS表达式和一个自定义数据属性 `data-descr` 创建一个纯CSS, 词汇表提示工具.

```html
<p>这是上面代码的实现<br />
  我们有一些 <span data-descr="collection of words and punctuation">文字</span> 有一些
  <span data-descr="small popups which also hide again">提示</span>。<br />
  把鼠标放上去<span data-descr="not to be taken literally">看看</span>.
</p>
```

```css
span[data-descr] {
  position: relative;
  text-decoration: underline;
  color: #00F;
  cursor: help;
}

span[data-descr]:hover::after {
  content: attr(data-descr);
  position: absolute;
  left: 0;
  top: 24px;
  min-width: 200px;
  border: 1px #aaaaaa solid;
  border-radius: 10px;
  background-color: #ffffcc;
  padding: 12px;
  color: #000000;
  font-size: 14px;
  z-index: 1;
}
```
