TOPICS: ::before
AUTHORS: 彼術向; Mookiepiece@github.com; github:Mookiepiece
         Leon WuV; wuxiaolong802@163.com; github:LeonWuV
         nDos; yokees@vip.qq.com; github:yokees
         胡凌皓; AutumnFish@mozilla.net; mdn:AutumnFish
         John Cido; johncido@mozilla.net; mdn:johncido
         Dong WEI; FredWe@mozilla.net; mdn:FredWe

# CSS 伪元素: `::before`

**`::before`** CSS 伪元素向选定的**元素前插入内容**。使用 `content` 属性来为一个元素添加修饰性的内容。

!!! warn "注意"
    由 `::before` 和 [`::after`](zh-hans/webfrontend/::after) 生成的伪元素 包含在元素格式框内，因此不能应用在替换元素上，比如[**`<img>`**](/zh-hans/webfrontend/<img>)或[**`<br>`**](/zh-hans/webfrontend/<br>)元素。

## 示例: 加入引用标记

使用 `::before` 伪元素的一个简单示例就是用于加入引号。此处同时使用了 `::before` 和 [`::after`](zh-hans/webfrontend/::after) 来插入引用性文本。

```html
<q>一些引用</q>, 他说, <q>比没有好。</q>.
```

```css
q::before {
  content: "«";
  color: blue;
}

q::after {
  content: "»";
  color: red;
}
```

## 示例: 修饰实例

我们可以用几乎任何方法定义 `content` 中的文字和图片样式。

```html
<span class="ribbon">Notice where the orange box is.</span>
```

```css
.ribbon {
   background-color: #5BC8F7;
}

.ribbon::before {
   content:          "Look at this orange box.";
   background-color: #FFBA10;
   border-color:     black;
   border-style:     dotted;
}
```

## 示例: 待办列表

在本例中我们将使用伪元素来创建一个简单的待办列表。这个方法也可用于 UI 的小幅度更改和用户体验的提升。

```html
<ul>
  <li>Buy milk</li>
  <li>Take the dog for a walk</li>
  <li>Exercise</li>
  <li>Write code</li>
  <li>Play music</li>
  <li>Relax</li>
</ul>
```

```css
li {
  list-style-type: none;
  position: relative;
  margin: 2px;
  padding: 0.5em 0.5em 0.5em 2em;
  background: lightgrey;
  font-family: sans-serif;
}

li.done {
  background: #CCFF99;
}

li.done::before {
  content: '';
  position: absolute;
  border-color: #009933;
  border-style: solid;
  border-width: 0 0.3em 0.25em 0;
  height: 1em;
  top: 1.3em;
  left: 0.6em;
  margin-top: -1em;
  transform: rotate(45deg);
  width: 0.5em;
}
```

```javascript
var list = document.querySelector('ul');
list.addEventListener('click', function(ev) {
  if( ev.target.tagName === 'LI') {
     ev.target.classList.toggle('done');
  }
}, false);
```
