TOPICS: :required
        :optional
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 伪类: `:required`、`:optional`

**`:required`** CSS伪类表示任意[`<input>`](/zh-hans/webfrontend/<input>)元素表示任意拥有`required`属性的
[`<input>`](/zh-hans/webfrontend/<input>)或 [`<textarea>`](/zh-hans/webfrontend/<textarea>) 元素使用它.

**`:optional`** CSS伪类表示任意没有`required`属性的[`<input>`](/zh-hans/webfrontend/<input>)，[`<select>`](/zh-hans/webfrontend/<select>)
或 [`<textarea>`](/zh-hans/webfrontend/<textarea>) 元素使用它。

## 示例

```html
<form>
  <label for="url_input">输入网址：</label>
  <input type="url" id="url_input"/>
  <br />
  <br />
  <label for="email_input">输入电子邮件地址：</label>
  <input type="email" id="email_input" required/>
</form>
```

```css
input:required {
  background-color: yellow;
}

input:optional {
  background-color: yellow;
}
```
