TOPICS: Element.getBoundingClientRect
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getBoundingClientRect()`

**`Element.getBoundingClientRect()`**方法返回元素的大小及其相对于视口的位置。

## 语法

```javascript
rectObject = object.getBoundingClientRect();
```

## 值

返回值是一个 `DOMRect` 对象，这个对象是由该元素的 `getClientRects()` 方法返回的一组矩形的集合, 即：是与该元素相关的CSS 边框集合 。

`DOMRect` 对象包含了一组用于描述边框的只读属性——`left`、`top`、`right`和`bottom`，单位为像素。除了 `width` 和 `height` 外的属性都是相对于视口的左上角位置而言的。

![rect](/media/webfrontend__rect.png)

空边框盒（译者注：没有内容的边框）会被忽略。如果所有的元素边框都是空边框，那么这个矩形给该元素返回的 `width`、`height` 值为`0`，`left`、`top`值为第一个CSS盒子（按内容顺序）的`top`-`left`值。

当计算边界矩形时，会考虑视口区域（或其他可滚动元素）内的滚动操作，也就是说，当滚动位置发生了改变，`top`和`left`属性值就会随之立即发生变化（因此，它们的值是相对于视口的，而不是绝对的）。如果你需要获得相对于整个网页左上角定位的属性值，那么只要给`top`、`left`属性值加上当前的滚动位置（通过`window.scrollX`和`window.scrollY`），这样就可以获取与当前的滚动位置无关的值。

为了跨浏览器兼容，请使用 `window.pageXOffset` 和 `window.pageYOffset` 代替 `window.scrollX` 和 `window.scrollY`。不能访问这些属性的脚本可以使用下面的代码：

```javascript
// For scrollX
(((t = document.documentElement) || (t = document.body.parentNode))
  && typeof t.scrollLeft == 'number' ? t : document.body).scrollLeft
// For scrollY
(((t = document.documentElement) || (t = document.body.parentNode))
  && typeof t.scrollTop == 'number' ? t : document.body).scrollTop
```

## 示例

```javascript
// rect 是一个具有四个属性left、top、right、bottom的DOMRect对象
//译者注：DOMRect 是 TextRectangle或 ClientRect 的别称，他们是相同的。
var rect = obj.getBoundingClientRect();
```
