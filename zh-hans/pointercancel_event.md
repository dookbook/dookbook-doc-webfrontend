TOPICS: onpointercancel
        pointercancel

# `pointercancel` 事件

`GlobalEventHandlers` mixin的 **`onpointercancel`** 属性是一个 `EventHandler` ，它处理 **`pointercancel`** 事件。

## 语法

```javascript
targetElement.onpointercancel = cancelHandler;

var cancelHandler = targetElement.onpointercancel;
```

**`cancelHandler`** 元素 `targetElement` 的`pointercancel`事件处理程序。

## 示例

这个例子展示了两种使用`onpointercancel`处理元素的`pointercancel`事件的方法。

```html
<html>
<script>
function cancelHandler(ev) {
  // Process the pointercancel event
}
function init() {
  var el = document.getElementById('target1');
  el.onpointercancel = cancelHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointercancel="cancelHandler(event)"> Touch me ... </div>
</body>
</html>
```
