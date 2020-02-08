TOPICS: oncancel
        cancel
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `cancel` 事件

`GlobalEventHandlers` 的 **`oncancel`** 属性是一个`EventHandler`，它是用来处理发送给`<dialog>`元素的`cancel` 事件的。

当用户需要离开一个`<dialog>`元素的时候就会触发 `cancel` 事件. 这个事件处理器会防止事件向上传递,因此任何父处理器都不会接受到该事件。

## 语法

```javascript
target.oncancel = functionRef;
```

`functionRef` 是一个函数名 或者 函数表达式. 这个函数接收一个 `Event` 对象作为它唯一的参数.

每次只有一个 `oncancel` 处理器可以被赋值给一个对象. 你可能更喜欢用 `EventTarget.addEventListener()` 方法, 因为它更灵活.

## 示例
