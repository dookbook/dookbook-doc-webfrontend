TOPICS: onpointerenter
        pointerenter

# `pointerenter` 事件

`GlobalEventHandlers` mixin的 **`onpointerenter`** 属性是一个 `EventHandler`，它处理 **`pointerenter`** 事件。

## 语法

```javascript
targetElement.onpointerenter = enterHandler;

var enterHandler = targetElement.onpointerenter;
```

**`enterHandler`** 元素 `targetElement` 的 `pointerenter` 事件处理程序。

## 示例

这个例子展示了两种使用`onpointerenter`来设置元素的`pointerenter`事件处理程序的方法。

```html
<html>
<script>
function enterHandler(ev) {
  // Process the pointerenter event
}
function init() {
  let el = document.getElementById('target1');
  el.onpointerenter = enterHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerenter="enterHandler(event)"> Touch me ... </div>
</body>
</html>
```
