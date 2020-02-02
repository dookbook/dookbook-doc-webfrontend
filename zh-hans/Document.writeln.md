TOPICS: Document.writeln
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.writeln()`

向文档中写入一串文本，并紧跟着一个换行符。

## 语法

```javascript
document.writeln(line);
```

| 参数 | 说明 |
| :-- | :-- |
| `line` | 为包含文本的字符串 |

## 示例

```javascript
document.writeln("<p>enter password:</p>");
```

## 注意

`document.writeln` 和 `document.write` 一样，但是会添加一个换行符。

!!! warn "注意"
    `document.writeln`（如`document.write`）在XHTML文档中不起作用（错误控制台上会出现“不支持操作”（`NS_ERROR_DOM_NOT_SUPPORTED_ERR`）错误）。
    如果打开带有`.xhtml`文件扩展名的本地文件或使用`application/xhtml+xml` MIME类型提供服务的任何文档，就属于这种情况。W3C XHTML常见问题解答中提供了更多信息。
