TOPICS: :default

# CSS 伪类: `:default`

**`:default`** CSS `pseudo-class` 表示一组相关元素中的默认表单元素。

该选择器可以在 [**`<button>`**](/zh-hans/webfrontend/<button>), [**`<input type="checkbox">`**](/zh-hans/webfrontend/<input>),
[**`<input type="radio">`**](/zh-hans/webfrontend/<input>),
以及 [**`<option>`**](/zh-hans/webfrontend/<button>) 上使用。

允许多个选择的分组元素也可以具有多个默认值，即，它们可以具有最初选择的多个项目。在这种情况下，所有默认值都使用 `:default` 伪类表示。例如，您可以在一组复选框之间设置默认复选框。

## 示例

```html
<input type="radio" name="season" id="spring">
<label for="spring">Spring</label>

<input type="radio" name="season" id="summer" checked>
<label for="summer">Summer</label>

<input type="radio" name="season" id="fall">
<label for="fall">Fall</label>

<input type="radio" name="season" id="winter">
<label for="winter">Winter</label>
```

```css
input:default {
  box-shadow: 0 0 2px 1px coral;
}

input:default + label {
  color: coral;
}
```
