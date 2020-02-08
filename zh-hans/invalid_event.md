TOPICS: oninvalid
        invalid
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `invalid` 事件

`GlobalEventHandlers` 混合的 **`oninvalid`** 属性 是 `EventHandler` 处理 `invalid` 事件。

`invalid` 事件被触发当一个从属元素被勾选 `checked` 并且与之前的选中方式不同。 有效的从属元素在表单之前被选中, 或者在 `checkValidity()` 方法之后它自己的表单被调用。

## 语法

```javascript
target.oninvalid = functionRef;
var functionRef = target.oninvalid;
```

`functionRef` 是一个函数名称 或者 称为 函数表达式。这个函数需要 `Event` 对象做为它的参数。

## 示例

这个例子用一个表单说明 `oninvalid` 和 `onsubmit` 事件 句柄。。

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
