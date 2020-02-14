TOPICS: onpointerup
        pointerup

# `pointerup` 事件

`GlobalEventHandlers` 混合的 **`onpointerup`** 属性是一个处理指针事件的`EventHandler`。

## 语法

```javascript
targetElement.onpointerup = upHandler;

var upHandler = targetElement.onpointerup;
```

**`upHandler`** The `pointerup` event handler for element `targetElement`.

## 示例

此示例显示了两种使用`onpointerup`设置元素的`pointerup`事件处理程序的方法。

```html
<html>
<script>
function upHandler(ev) {
  // Process the pointerup event
}
function init() {
  let el = document.getElementById('target1');
  el.onpointerup = upHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerup="upHandler(event)"> Touch me ... </div>
</body>
</html>
```
