TOPICS: <style>
        <style> type attribute
        <style> scoped attribute
        <style> title attribute
        <style> media attribute

# HTML 样式信息元素: `<style>`

**HTML `<style>` 元素** 包含文档的样式信息或者文档的部分内容。默认情况下，该标签的样式信息通常是CSS的格式。

`<style>`元素可以包含在文档的[`<head>`](/zh-hans/webfrontend/<head>)或[`<body>`](/zh-hans/webfrontend/<body>)中，
并且样式仍然适用，但是建议您将样式包括在[`<head>`](/zh-hans/webfrontend/<head>)中，以用于组织目的–最好将您的内容与演示文稿尽可能分开。更好的是，将样式放在外部样式表中，并使用[`<link>`](/zh-hans/webfrontend/<link>)元素来应用它们。

如果您在文档中包含多个`<style>`和[`<link>`](/zh-hans/webfrontend/<link>)元素，则它们将按照它们在文档中包含的顺序应用于DOM-确保以正确的顺序包含它们，
以免出现意外情况 级联问题。

与[`<link>`](/zh-hans/webfrontend/<link>)元素相同，`<style>`元素可以包含包含媒体查询的媒体属性，从而允许您根据媒体功能（例如视口宽度）有选择地将内部样式表应用于文档。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *元数据内容*，以及是否存在`scoped`属性：*流式内容*。 |
| **允许的内容** | 与`type`属性匹配的文本内容，即`text/css`. |
| **标签遗漏** | 这两个标签都不可省略. |
| **允许的父元素** | 任何接受*元数据内容*的元素. |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLStyleElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `type` | 该属性以MIME类型（不应该指定字符集）定义样式语言。如果该属性未指定，则默认为 `text/css`。|
| `scoped` | 如果该属性存在，则样式应用于其父元素；如果不存在，则应用于整个文档。|
| `title` | 此属性指定替代样式表集。|
| `media` | 此属性定义应将样式应用于哪种媒体。它的值是一个媒体查询，如果缺少该属性，则默认为`all`. |

## 一个简单的样式表

在下面的示例中，我们将非常简单的样式表应用于文档：

```html
<!doctype html>
<html>
<head>
<style>
p {
  color: red;
}
</style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## 多种风格元素

在此示例中，我们包括了两个`<style>`元素—请注意，如果后一个`<style>`元素中的冲突声明具有相同的特异性，则它们之间的冲突声明将如何覆盖前一个声明中的声明。

```html
<!doctype html>
<html>
<head>
  <style>
  p {
    color: white;
    background-color: blue;
    padding: 5px;
    border: 1px solid black;
  }
  </style>
  <style>
  p {
    color: blue;
    background-color: yellow;
  }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## 包括媒体查询

在此示例中，我们基于前一个示例，在第二个`<style>`元素上包括`media`属性，因此仅在视口宽度小于500px时才应用此属性。

```html
<!doctype html>
<html>
<head>
  <style>
    p {
      color: white;
      background-color: blue;
      padding: 5px;
      border: 1px solid black;
    }
  </style>
  <style media="all and (max-width: 500px)">
    p {
      color: blue;
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```
