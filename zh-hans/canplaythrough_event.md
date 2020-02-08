TOPICS: oncanplaythrough
        canplaythrough
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `canplaythrough` 事件

全局事件处理器（`GlobalEventHandlers`)之一的 `canplaythrough` 属性，是处理当前元素 **`canplaythrough`** 事件的事件处理器`EventHandler`.

当用户代理可以播放媒体资源并且可以播放至其结束而不必进一步缓冲内容时，触发`canplaythrough`事件。

## 语法

```javascript
element.oncanplaythrough = handlerFunction;
var handlerFunction = element.oncanplaythrough;
```
