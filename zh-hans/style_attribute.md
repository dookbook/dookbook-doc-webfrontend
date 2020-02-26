TOPICS: style attribute

# HTML 全局属性: `style`

**`style`** [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) 定义元素的**行内样式**。`style` 属性将覆盖任何全局的样式设定，
例如在 [`<style>`](/zh-hans/webfrontend/<style>) 标签或在外部样式表中规定的样式。要注意样式最好定义在单独的文件中。

!!! warn "用法注解"
    这个属性不能用于传递语义信息。即使所有样式都移除了，页面也应该保留正确语义。通常它不应用于隐藏不相关的信息；这应该使用
    [`hidden`](/zh-hans/webfrontend/hidden_attribute) 属性来实现。

## 示例

下列展示了 `style` 属性的行内样式覆盖了 [`<style>`](/zh-hans/webfrontend/<style>) 标签的样式。

```html
<style>
  h1 { color: red }
</style>

<h1 style="color:blue;text-align:center">这是一个标题</h1>
<p style="color:green">这是一个段落。</p>
```

## 参见

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
