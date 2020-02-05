TOPICS: oninput
        input
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `input` 事件

`GlobalEventHandlers` mixin的 **`oninput`** 属性是`EventHandler`，它处理`<input>`，`<select>`和 `<textarea>`
元素上的 `input` 事件。 它还会在`contenteditable` 或 `designMode`打开的元素上处理这些事件。

!!! warn "注意"
    与`oninput`不同的是， `onchange` 事件处理程序不一定会针对元素值的每次更改而调用。

## 语法

```html
target.oninput = functionRef;
```

- `functionRef`是一个函数名或函数表达式。该函数接收`InputEvent` 对象作为唯一参数。

## 示例

```html
<input type="text" placeholder="Type something here to see its length." size="50"> <p id="log"></p>
```

```javascript
let input = document.querySelector('input');
let log =document.getElementById('log');
input.oninput = handleInput;
function handleInput(e) {
  log.textContent = `The field's value is${e.target.value.length} character(s) long.`;
}
```
