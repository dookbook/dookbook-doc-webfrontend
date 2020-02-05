TOPICS: onclick
        click
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `click` 事件

全局事件处理器之一的 `onclick` 属性，是处理当前元素的 `click` 事件的事件处理器。

当用户点击一个元素时，会触发 `click` 事件。在每次点击的整个过程中，`click` 事件的运行顺序在 `mousedown` 和 `mouseup` 事件之后。

!!! warn "注意"
    当你使用 `click` 事件去触发一个动作时，也要考虑向 `keydown` 事件添加此动作，以便允许不使用鼠标或触摸屏的用户进行同样的操作。

## 语法

```javascript
element.onclick = functionRef;
```

`functionRef` 是一个函数名称，或一个函数表达式。该函数接收 `MouseEvent` 对象作为其唯一参数。在函数内，`this` 是触发当前事件的元素。

同一时刻，每个 `onclick` 接收器只能指向唯一一个对象。所以，你可能更倾向于使用`EventTarget.addEventListener()` 的方法，这种方法更加灵活，同时也是 DOM 事件规范格式。

## 示例

这个例子会记录每次点击的坐标。

```html
<p>请随意点击本例子。</p>
<p id="log"></p>
```

```javascript
let log = document.getElementById('log');

document.onclick = inputChange;

function inputChange(e) {
  log.textContent = `Position: (${e.clientX}, ${e.clientY})`;
}
```

也可以使用匿名函数：

```javascript
p.onclick = function() { alert("moot!"); };
```
