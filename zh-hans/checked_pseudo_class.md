TOPICS: :checked
AUTHORS: 石博文; http_wenwen@live.com; github:Ritr

# CSS 伪类: `:checked`

**`:checked`** CSS伪类选择器代表任何 **`radio`** (`<input type =“ radio”>`), **`checkbox`** (`<input type =“ checkbox”>`)
或 **`option`** ([`<select>`](/zh-hans/webfrontend/<select>)中的[`<option>`](/zh-hans/webfrontend/<option>)
元素被选中或切换为开启状态。

用户通过勾选/选中元素或取消勾选/取消选中，来改变该元素的 `:checked` 状态。

!!! warn "注意"
    因为浏览器经常将`<option>`视为可替换元素,因此不同的浏览器通过`:checked`伪类渲染出来的效果也不尽相同.

## 示例

```html
<div>
  <input type="radio" name="my-input" id="yes">
  <label for="yes">Yes</label>

  <input type="radio" name="my-input" id="no">
  <label for="no">No</label>
</div>

<div>
  <input type="checkbox" name="my-checkbox" id="opt-in">
  <label for="opt-in">Check me!</label>
</div>

<select name="my-select" id="fruit">
  <option value="opt1">Apples</option>
  <option value="opt2">Grapes</option>
  <option value="opt3">Pears</option>
</select>
```

```css
div,
select {
  margin: 8px;
}

/* Labels for checked inputs */
input:checked + label {
  color: red;
}

/* Radio element, when checked */
input[type="radio"]:checked {
  box-shadow: 0 0 0 3px orange;
}

/* Checkbox element, when checked */
input[type="checkbox"]:checked {
  box-shadow: 0 0 0 3px hotpink;
}

/* Option elements, when selected */
option:checked {
  box-shadow: 0 0 0 3px lime;
  color: red;
}
```
