TOPICS: :scope

# CSS 伪类: `:scope`

**`:scope`** 属于 CSS 伪类，它表示作为选择器要匹配的参考点的元素。

当前，在样式表中使用时, `:scope` 等效于 *`:root`*，因为目前尚无一种方法来显式建立作用域元素。当从DOM API使用，
如（`querySelector()`, `querySelectorAll()`, `matches()`, 或 `Element.closest()）`, `:scope` 匹配你调用API的元素。

## 示例: 身份匹配

在这个简单的示例中，我们演示了调用 `Element.matches()` 方法中使用 `:scope` 伪类来匹配调用它的元素。

```javascript
let paragraph = document.getElementById("para");
let output = document.getElementById("output");

if (paragraph.matches(":scope")) {
  output.innerText = "Yep, the element is its own scope as expected!";
}
```

```html
<p id="para">
  This is a paragraph. It is not an interesting paragraph. Sorry about that.
</p>
<p id="output"></p>
```

## 示例: 直接后代元素

当需要获取已检索到的的直接后代元素时，`:scope` 伪类很有用。

```javascript
var context = document.getElementById('context');
var selected = context.querySelectorAll(':scope > div');

document.getElementById('results').innerHTML = Array.prototype.map.call(selected, function (element) {
    return '#' + element.getAttribute('id');
}).join(', ');
```

```html
<div id="context">
    <div id="element-1">
        <div id="element-1.1"></div>
        <div id="element-1.2"></div>
    </div>
    <div id="element-2">
        <div id="element-2.1"></div>
    </div>
</div>
<p>
    Selected elements ids :
    <span id="results"></span>
</p>
```
