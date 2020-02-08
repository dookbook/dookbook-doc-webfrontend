TOPICS: ondurationchange
        durationchange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `durationchange` 事件

`GlobalEventHandlers` 的 **`ondurationchange`** 属性是一个处理 **`durationchange`** 事件的 `EventHandler` 。

`durationchange`事件会在`duration`发生变更时触发。

## 语法

```javascript
element.ondurationchange = handlerFunction;
var handlerFunction = element.ondurationchange;
```

`handlerFunction`可以为`null`也可以是一个处理该事件的JavaScript方法。
