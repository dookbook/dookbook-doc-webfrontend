TOPICS: <head>

# HTML 头部元素: `<head>`

HTML `<head>`元素**规定文档相关的配置信息**（**元数据**)，包括文档的*标题* ([`<title>`](/zh-hans/webfrontend/<title>))、*作者*、*描述*、
以及引用的*文档样式（[[CSS]]）* ([`<link>`](/zh-hans/webfrontend/<link>))和*脚本（JavaScript）* ([`<script>`](/zh-hans/webfrontend/<script>))等。

!!! warn "注意"
    `<head>`主要保存用于机器处理的信息，而不是可读性。有关可视的信息，如顶级标题和列出的作者，请参见[`<header>`](/zh-hans/webfrontend/<header>)元素。

如果在文档中忽略了`<head>`标签，则大部分浏览器会自动创建一个`<head>`元素。当然,在旧版浏览器中无法保证自动创建。

## `<head>` 元数据

|  |  |
| :-- | :-- |
| **内容类别** | 无 |
| **允许内容** | 至少包含一个[`<title>`](/zh-hans/webfrontend/<title>/)元素来指定文档的标题信息，除非标题已经从更高等级协议中指定（[`<iframe>`](/zh-hans/webfrontend/<iframe>)）。|
| **标签省略** | 如果`<head>`元素内部的第一是元素，则可以省略开始标签。如果`<head>`元素后面的第一不是空格字符或注释，则可以省略结束标签。|
| **允许父元素** | [`<html>`](/zh-hans/webfrontend/<html>)元素，并作为其第一个子元素。 |
| **允许的 ARIA 角色** | 无 |
| **DOM接口** | **`HTMLHeadElement`** |

## 示例

```html
<html>
  <head>
    <title>文档标题</title>
  </head>
</html>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<head>` | 支持 | 支持 | 支持 |
