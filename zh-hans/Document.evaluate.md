TOPICS: Document.evaluate

# `Document.evaluate()`

根据传入的 `XPath` 表达式以及其他参数，返回一个 `XPathResult` 对象。

## 语法

```javascript
var xpathResult = document.evaluate(
  xpathExpression,
  contextNode,
  namespaceResolver,
  resultType,
  result
);
```

| 参数 | 说明 |
| :-- | :-- |
| `xpathExpression` | 表示要计算的 `Xpath` 字符串。|
| `contextNode` | 表示本次查询的上下文节点（参照XPath规范 [http://www.w3.org/TR/xpath](http://www.w3.org/TR/xpath)）。通常会使用 `document`。|
| `namespaceResolver` | 是函数。传入名空间前缀，返回跟此前缀相关的名空间URI（字符串）。通常用来解析Xpath内的前缀，以便对文档进行匹配。HTML文档或者不使用名空间前缀的文档，通常传入 `null。` |
| `resultType` | 是整数。指定所返回的 `XPathResult` 的类型，常使用命名常量属性，如 `XPathResult.ANY_TYPE`，范围 `0` 到 `9`，见下表。|
| `result` | 为 `XPathResult` 型，用以存储查询结果。通常传入 `null`，此时将创建新的 `XPathResult` 对象。|

## `resultType` 参数支持的值

## 示例

```javascript
var headings = document.evaluate("/html/body//h2", document, null, XPathResult.ANY_TYPE, null);
/* 在 document 中查找所有的 h2 元素。  
 * 结果可能是无序节点迭代器。 */
var thisHeading = headings.iterateNext();
var alertText = "Level 2 headings in this document are:\n";
while (thisHeading) {
  alertText += thisHeading.textContent + "\n";
  thisHeading = headings.iterateNext();
}
alert(alertText); // 显示所有 h2 节点的文本
```

注意，在上述例子中，最好写更冗长的`XPath`，而不是常用的简写，比如 `//h2`。 通常，像上述例子所示，更具体的`XPath`选择器会得到显著的性能提升，特别是在非常大的文档中。这是因为查询计
算不会将时间浪费在查看不需要的节点上。使用 `//` 通常很慢，这是因为它要从根节点和所有子节点中查找所有可能匹配的节点。

通过谨慎使用上下文参数能得到进一步的优化。比如，如果你知道你要查找的内容在 `body` 标签的某处，你可以这样做：

```javascript
document.evaluate(".//h2", document.body, null, XPathResult.ANY_TYPE, null);
```

注意上面的 `document.body` 已经替代了`document`作为上下文，所以 `XPath` 从 `body` 元素开始查找。
（在这个例子中，`"."` 很重要，因为它指示了查找要从document.body这个上下文节点开始。如果遗漏了 `"."` (剩下 `//h2`) ，查找会从根节点（HTML）处开始，这样会很浪费。）

## 注意

- XPath 表达式能在 HTML 和 XML 文档上计算。
- 如果要计算别的而不是当前文档，在 FF3 上必须使用`someXMLDoc.evaluate()` ，虽然在 FF2 上 `document.evaluate()` 也有效。
