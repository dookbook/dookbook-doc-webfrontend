TOPICS: onsubmit
        submit
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `submit` 事件

`GlobalEventHandlers` 的 `onsubmit` 属性是一个处理 `submit` 的 `EventHandler`。

`submit` 事件会在用户点击提交按钮（`<input type="submit"/>` 元素）提交表单时触发。

## 语法

```javascript
target.onsubmit = functionRef;
```

- `functionRef` 是一个函数名或 函数表达式。该函数接收`FocusEvent`对象作为其唯一参数。

## 示例

本示例演示了表单上的`oninvalid`和`onsubmit`事件处理程序。

```html
<form id="form">
  <p id="error" hidden>Please fill out all fields.</p>

  <label for="city">City</label>
  <input type="text" id="city" required>

  <button type="submit">Submit</button>
</form>
<p id="thanks" hidden>Your data has been received. Thanks!</p>
```

```javascript
const form = document.getElementById('form');
const error = document.getElementById('error');
const city = document.getElementById('city');
const thanks = document.getElementById('thanks');

city.oninvalid = invalid;
form.onsubmit = submit;

function invalid(event) {
  error.removeAttribute('hidden');
}

function submit(event) {
  form.setAttribute('hidden', '');
  thanks.removeAttribute('hidden');

  // For this example, don't actually submit the form
  event.preventDefault();
}
```
