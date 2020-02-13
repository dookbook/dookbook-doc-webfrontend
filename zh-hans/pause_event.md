TOPICS: onpause
        pause

# `pause` 事件

`GlobalEventHandlers` mixin的 **`onpause`** 属性是用于处理暂停事件的`EventHandler`。

当媒体播放已暂停时，将触发 **`pause`** 事件。

## 语法

```javascript
element.onpause = handlerFunction;
var handlerFunction = element.onpause;
```

`handlerFunction` 应该为 `null` 或指定事件处理程序的JavaScript函数。
