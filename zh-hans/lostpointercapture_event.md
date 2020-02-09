TOPICS: onlostpointercapture
        lostpointercapture

# `lostpointercapture` 事件

`GlobalEventHandlers` mixin的 **`onlostpointercapture`** 属性是一个处理 **`lostpointercapture`** 事件的 `EventHandler`。

## 语法

```javascript
target.onlostpointercapture = functionRef;
```

`functionRef` 是函数名称或函数表达式。 该函数接收一个`PointerEvent`对象作为其唯一的参数。

## 示例

```javascript
function overHandler(event) {
  // Determine the target event's lostpointercapture handler
  let lostCaptureHandler = event.target.onlostpointercapture;
}

function init() {
  let el = document.getElementById('target');
  el.onlostpointercapture = overHandler;
}
```
