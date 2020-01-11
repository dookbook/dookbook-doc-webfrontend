TOPICS: Element.scrollIntoView
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.scrollIntoView()`

**`Element.scrollIntoView()`** 方法让当前的元素滚动到浏览器窗口的可视区域内。

## 语法

```javascript
element.scrollIntoView(); // 等同于element.scrollIntoView(true)
element.scrollIntoView(alignToTop); // Boolean型参数
element.scrollIntoView(scrollIntoViewOptions); // Object型参数
```

| 参数 | 说明 |
| :-- | :-- |
| `alignToTop` 可选 | 一个`Boolean`值：<br><br>1.如果为`true`，元素的顶端将和其所在滚动区的可视区域的顶端对齐。相应的 `scrollIntoViewOptions: {block: "start", inline: "nearest"}`。这是这个参数的默认值。<br><br>2. 如果为`false`，元素的底端将和其所在滚动区的可视区域的底端对齐。相应的`scrollIntoViewOptions: {block: "end", inline: "nearest"}`。
| `scrollIntoViewOptions` 可选 | 一个包含下列属性的对象：<br><br>1. `behavior` 可选<br>定义动画过渡效果，`"auto"`或 `"smooth"` 之一。默认为 `"auto"`。<br><br>2. `block` 可选<br>定义垂直方向的对齐，`"start"`, `"center"`, `"end"`, 或 `"nearest"`之一。默认为 `"start"`。<br><br>3. `inline` 可选<br>定义水平方向的对齐，`"start"`, `"center"`, `"end"`, 或 `"nearest"`之一。默认为 `"nearest"`。

## 示例

```javascript
var element = document.getElementById("box");

element.scrollIntoView();
element.scrollIntoView(false);
element.scrollIntoView({block: "end"});
element.scrollIntoView({behavior: "instant", block: "end", inline: "nearest"});
```

!!! warn "注意"
    取决于其它元素的布局情况，此元素可能不会完全滚动到顶端或底端。
