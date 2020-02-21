TOPICS: :indeterminate

# CSS 伪类: `:indeterminate`

**`:indeterminate`** CSS 伪类表示 **状态不确定** 的 *表单元素*。

例如，`radio` 和 `checkbox` 元素可以在选中状态和未选中状态之间切换，但有时处于不确定状态，既不选中也不取消选中。类似地，还有HTML5 [**`<progress>`**](/zh-hans/webfrontend/<progress>)标签，当完成的百分比未知时，进度条（[**`<progress>`**](/zh-hans/webfrontend/<progress>)）可以处于不确定状态。

- **`<input type="checkbox">`** 元素，其 `indeterminate` 属性被 JavaScript设置为 `true` 。
- **`<input type="radio">`** 元素, 表单中拥有相同 `name`值的所有单选按钮都未被选中时。
- 没有 `value` 属性的进度条 [**`<progress>`**](/zh-hans/webfrontend/<progress>) 元素

## 示例: 复选框和单选按钮

```html
<div>
  <input type="checkbox" id="checkbox">
  <label for="checkbox">Background should be green</label>
</div>
<div>
  <input type="radio" id="radio">
  <label for="radio">Background should be green</label>
</div>
```

```css
p:first-child {
input, span {
  background: red;
}

:indeterminate, :indeterminate + label {
  background: lime;
}
```

```javascript
var inputs = document.getElementsByTagName("input");
for(var i = 0; i < inputs.length; i++) {
  inputs[i].indeterminate = true;
}
```

## 示例: 进度条

```css
progress {
  margin: 4px;
}

progress:indeterminate {
  opacity: 0.5;
  background-color: lightgray;
  box-shadow: 0 0 2px 1px red;
}
```

```html
<progress>
```
