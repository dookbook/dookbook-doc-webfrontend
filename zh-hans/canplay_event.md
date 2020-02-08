TOPICS: oncanplay
        canplay
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `canplay` 事件

`GlobalEventHandlers` 的 **`oncanplay`** 属性是 `EventHandler` 处理 **`canplay`** 事件。

当用户代理能够播放媒体时 `canplay` 事件被触发 , 但是预估没有加载全部的数据以支持媒体播放完毕。

## 语法

```javascript
element.oncanplay = handlerFunction;
var handlerFunction = element.oncanplay;
```

`handlerFunction` 或者是 `null` 或者是一个 JavaScript `function` 指定事件的处理句柄。
