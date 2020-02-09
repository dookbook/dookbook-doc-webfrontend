TOPICS: onpointerleave
        pointerleave
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerleave` 事件

就像在[`Element`](/zh-hans/webfrontend/Element)或`Window`中点击类似，在某目标区域内，发生触点（鼠标指针，触摸等）行为时会触发源于 **`pointerleave`**
事件全局事件 `handler` 行为。这个事件本身属于 Pointer Events API 的一部分。

## 语法

```javascript
var leaveHandler = EventTarget.onpointerleave;

EventTarget.onpointerleave = leaveHandler;
```

**`leaveHandler`** `pointerleave` 事件会执行 `EventListener` 监听器会委托执行用以发送给目标。

## 示例

这个样例展示了两种使用 `onpointerleave` 来设置元素 `pointerleave` 事件处理器的方式。

```html
<html>
<script>
function leaveHandler(ev) {
 // 执行 pointerleave event 事件
}
function init() {
 var el=document.getElementById("target1");
 el.onpointerleave = leaveHandler;
}
</script>
<body onload="init();">
<div id="target1"> Touch me ... </div>
<div id="target2" onpointerleave="leaveHandler(event)"> Touch me ... </div>
</body>
</html>
```
