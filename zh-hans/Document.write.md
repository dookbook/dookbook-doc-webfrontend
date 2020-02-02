TOPICS: Document.write
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.write()`

`Document.write()` 方法将一个文本字符串写入一个由 `document.open()` 打开的文档流（document stream）。

!!! warn "注意"
    因为 `document.write` 需要向文档流中写入内容，所以，若在一个已关闭（例如，已完成加载）的文档上调用 `document.write`，就会自动调用 `document.open`，这将清空该文档的内容。

## 语法

```javascript
document.write(markup);
```

| 参数 | 说明 |
| :-- | :-- |
| `markup` | 一个包含要写入文档的文本的字符串 |

## 示例

```html
<html>
<head>
  <meta charset="UTF-8">
  <title><code>document.write()</code> example</title>
  <script>
    function newContent() {
      document.open();
      document.write("<h1>Out with the old - in with the new!</h1>");
      document.close();
    }
  </script>
</head>
<body onload="newContent();">
  <p>Some original document content.</p>
</body>

</html>
```

## 备注

向一个已经加载，并且没有调用过 `document.open()` 的文档写入数据时，会自动调用 `document.open`。一旦完成了数据写入，建议调用 `document.close()`，
以告诉浏览器当前页面已经加载完毕。写入的数据会被解析到文档结构模型（DOM）里。在上面的例子里，元素 h1 会成为文档中的一个节点。

如果 `document.write()` 调用发生在 HTML 里的 `<script>` 标签中，那么它将不会自动调用 `document.open()`。详见如下例子：

```html
<script>
  document.write("<h1>Main title</h1>")
</script>
```

!!! warn "注意"
    `document.write` 和 `document.writeln` 在 XHTML 文档中不可用（控制台上会显示 "不支持该操作"
    `[NS_ERROR_DOM_NOT_SUPPORTED_ERR]` 的报错信息）。当打开本地的 `.xhtml` 格式的文件或任何其他 MIME 类型为
    `application/xhtml+xml` 的文档时，均会报错。更多信息可查看 W3C XHTML FAQ。

!!! warn "注意"
    在有 `deferred` 或 `asynchronous` 属性的 script 中，`document.write` 会被忽略，控制台会显示
    "从异步加载的外部脚本对 `document.write()`的调用被忽略" 的报错信息。

!!! warn "注意"
    在 Edge 中，在 `<iframe>` 内部调用 `document.write` 多于一次时会引发错误 SCRIPT70: Permission denied。

!!! warn "注意"
    从 Chrome 55 开始，Chrome（可能）不会运行通过 `document.write()` 注入的`<script>`，以防止使用 2G 连接的用户找不到 HTTP 缓存。前往此链接查看这种情况发生需要满足的条件。
