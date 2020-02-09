TOPICS: onpointerout
        pointerout
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `pointerout` 事件

`GlobalEventHandlers` mixin的 **`onpointerout`** 属性是一个处理指针事件的`EventHandler`。

## 语法

```javascript
targetElement.onpointerout = outHandler;

var outHandler = targetElement.onpointerout;;
```

**`outHandler`** 元素 `targetElement` 的指针事件处理程序。

## Example

此示例显示了两种使用 `onpointerout` 设置元素的指针事件处理程序的方法。

```html
<html>
<script>
function outHandler(ev) {
  // Process the pointerout event
}
function init() {
  let el=document.getElementById('target1');
  el.onpointerout = outHandler;
}
</script>

<body onload="init();">
  <div id="target1"> Touch me ... </div>
  <div id="target2" onpointerout="outHandler(event)"> Touch me ... </div>
</body>
</html>
```
