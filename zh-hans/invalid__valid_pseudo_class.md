TOPICS: :invalid
        :valid

# CSS 伪类: `:invalid`、`:valid`

**`:invalid`** CSS伪类表示任意内容未通过验证的[*`<input>`*](/zh-hans/webfrontend/<input>)或其他[*`<form>`*](/zh-hans/webfrontend/<form>)元素.

**`:valid`** CSS伪类表示内容验证正确的[*`<input>`*](/zh-hans/webfrontend/<input>)或其他[*`<form>`*](/zh-hans/webfrontend/<form>)元素。这能简单地将校验字段展示为一种能让用户辨别出其输入数据的正确性的样式。

## 示例

以下示例是一个简单的表单，当值有效时，元素颜色为绿色，无效时为红色。

```html
<form>
  <label for="url_input">Enter a URL:</label>
  <input type="url" id="url_input" />
  <br />
  <br />
  <label for="email_input">Enter an email address:</label>
  <input type="email" id="email_input" required/>
</form>
```

```css
input:invalid {
  background-color: #ffdddd;
}

form:invalid {
  border: 5px solid #ffdddd;
}

input:valid {
  background-color: #ddffdd;
}

form:valid {
  border: 5px solid #ddffdd;
}
  
input:required {
  border-color: #800000;
  border-width: 3px;
}

input:required:invalid {
  border-color: #C00000;
}
```

## 注意

### 单选钮（Radio buttons）

若一组单选钮被设定为必须选定一个，在该组中没有按钮被选中的情况，`:invalid`伪类被应用到该组中的所有按钮。（单选钮组按照`name`属性共享相同值。）

### Gecko 默认

默认情况下，Gecko不应用`:invalid`伪类设置的样式。但是，Gecko可以使用`:-moz-ui-invalid`伪类的样式（使用 `box-shadow` 属性设置红色发光边框）来达到类似的效果，它可以被应用在`:invalid`伪类的子集中。

你可以使用以下CSS禁用红色发光边框,或完全重写它以改变无效输入域的外观：

```css
:invalid {
  box-shadow: none;
}

:-moz-submit-invalid {
  box-shadow: none;
}

:-moz-ui-invalid {
  box-shadow: none;
}
```
