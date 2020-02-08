TOPICS: oncuechange
        cuechange
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `cuechange` 事件

**`oncuechange`** 属性属于`GlobalEventHandlers`，是一个处理 **`cuechange`** 事件的`EventHandler`。
当`TextTrack`更改了当前显示的提示时，`cuechange` 事件将会触发。

## 语法

```javascript
element.oncuechange = handlerFunction;
var handlerFunction = element.oncuechange;
```

`handlerFunction` 可以为 `null`，也可以是一个处理指定事件的JavaScript函数。
