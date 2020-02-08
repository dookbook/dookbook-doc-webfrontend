TOPICS: <datalist>

# `<datalist>`

HTML `<datalist>` 元素包含了一组[`<option>`](/zh-hans/webfrontend/<option>)元素，这些元素表示其它表单控件可选值。

`<datalist>` 标签被用来在为 `<input>` 元素提供"自动完成"的特性。用户能看到一个下拉列表，里边的选项是预先定义好的，将作为用户的输入数据。

请使用 `<input>`元素的 `list` 属性来绑定 `<datalist>` 元素。

|  |  |
| :-- | :-- |
| **内容范畴** | *流式内容*，*段落内容*。|
| **允许内容** | 要么 *段落内容* 要么0个或多个 [`<option>`](/zh-hans/webfrontend/<option>)元素。 |
| **遗漏标签** | 不允许，开始标签和结束标签都不能省略。|
| **允许父级元素** | 任何接受段落内容的元素. |
| **允许的ARIA角色** | None |
| **DOM接口** | **`HTMLDataListElement`** |

## 属性

该元素除了公用的[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)之外，没有其他属性。

## 示例

```html
<label>Choose a browser from this list:
<input list="browsers" name="myBrowser" /></label>
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Internet Explorer">
  <option value="Opera">
  <option value="Safari">
</datalist>
```
