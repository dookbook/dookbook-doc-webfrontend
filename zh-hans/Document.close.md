TOPICS: Document.close
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.close()`

**`Document.close()`** 用于结束由 对文档的 [`Document.write()`](/zh-hans/webfrontend/Document.write) 写入操作，
这种写入操作一般由 [`Document.open()`](/zh-hans/webfrontend/Document.open) 打开。

## 语法

```javascript
document.close();
```

## 示例

```javascript
// 打开一个文档，以便写入数据
document.open();

// 写入文档内容
document.write("<p>文档内容~</p>");

// 关闭文档
document.close();
```
