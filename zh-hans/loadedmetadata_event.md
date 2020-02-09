TOPICS: onloadedmetadata
        loadedmetadata
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `loadedmetadata` 事件

`GlobalEventHandlers` mixin的 **`onloadedmetadata`** 属性是处理 **`loadedmetadata`** 事件的 `EventHandler`。

**`loadedmetadata`** 事件在元数据被加载完成后触发。

## 语法

```javascript
element.onloadedmetadata = handlerFunction;
var handlerFunction = element.onloadedmetadata;
```

`handlerFunction` 应当是 `null` 或是由JavaScript函数声明的事件 `handler`。
