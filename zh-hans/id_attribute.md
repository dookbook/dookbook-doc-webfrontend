TOPICS: id attribute

# HTML 全局属性: `id`

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) **`id`** 定义了 HTML 元素的唯一的标识符 (ID)。可用作链接锚（link anchor），
通过 JavaScript（HTML DOM）或通过 CSS 为带有指定 `id` 的元素改变或添加样式。

!!! error ""
    该属性的值是一个透明（opaque）字符串，这意味着网页开发者不能使用它来传递人类可读的信息。

`id` 的值不得包含空白字符（whitespace，包括空格和制表符等）。浏览器会将不符合规范的 `id` 中的空白字符视为 `id` 的一部分。与允许以空格分隔值的 [`class`](/zh-hans/webfrontend/class_attribute)
属性不同，元素只能拥有一个 `id` 值。

!!! warn "注意"
    使用除 [[ASCII]] 字母、数字、`_`、`-` 和 `.` 以外的字符可能会造成兼容性问题，因为 HTML4 中不允许使用它们。虽然这个限制在 HTML5 中被解除了，
    但为兼容性考虑 `id` 应该以字母 `A-Z` 或 `a-z` 开头。

## 示例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>简单示例</title>
<script>
function displayResult() {
  document.getElementById("myHeader").innerHTML="Have a nice day!";
}
</script>
<style>
#myHeader {
  font-size: 28px;
  color: red;
}
</style>
</head>
<body>

<h1 id="myHeader">Hello World!</h1>
<button onclick="displayResult()">编辑文本</button>

</body>
</html>
```

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- 反映该属性的 [`Element.id`](/zh-hans/webfrontend/Element.id)。
