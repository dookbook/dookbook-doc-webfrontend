TOPICS: onended
        ended

# `ended` 事件

`GlobalEventHandlers` mixin的 **`onended`** 属性是用于处理结束事件的`EventHandler`。

当由于媒体已到达末尾而停止播放时，将触发`end`事件。

## 语法

```javascript
element.onended = handlerFunction;
var handlerFunction = element.onended;
```

`handlerFunction` 可以为 `null` 或者具体的事件响应函数。
