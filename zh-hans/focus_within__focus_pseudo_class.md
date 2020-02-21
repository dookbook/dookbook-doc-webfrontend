TOPICS: :focus-within
        :focus

# CSS 伪类: `:focus-within`、`:focus`

CSS **`:focus-within`** 伪类表示**一个元素获得焦点**，或，**该元素的后代元素获得焦点**。换句话说，元素自身或者它的某个后代匹配`:focus`伪类。

该选择器非常实用。举个通俗的例子：表单中的某个 [`<input>`](/zh-hans/webfrontend/<input>) 字段获得焦点时，整个表单的
[`<form>`](/zh-hans/webfrontend/<form>) 元素都可被高亮。

CSS **`:focus`** 伪类表示**获得焦点的元素**（如表单输入）。当用户 *点击* 或 *触摸* 元素或通过 *键盘* 的 !!!tab!!! 键选择它时会被触发。

## 示例: `:focus-within`

例子中，当表单某个文本输入框获得焦点后，表单会被设置颜色样式。

```html
<p>试试在这个表单中输入点什么。</p>

<form>
  <label for="given_name">Given Name:</label>
  <input id="given_name" type="text">
  <br>
  <label for="family_name">Family Name:</label>
  <input id="family_name" type="text">
</form>
```

```css
form {
  border: 1px solid;
  color: gray;
  padding: 4px;
}

form:focus-within {
  background: #ff8;
  color: black;
}

input {
  margin: 4px;
}
```

## 示例: `:focus`

```html
<input class="red-input" value="I'll be red when focused."><br>
<input class="blue-input" value="I'll be blue when focused.">
```

```css
.red-input:focus {
  background: yellow;
  color: red;
}

.blue-input:focus {
  background: yellow;
  color: blue;
}
```
