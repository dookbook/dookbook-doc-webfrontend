TOPICS: Document.createExpression
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createExpression()`

此方法编译 `XPathExpression`，然后可将其用于（重复）`XPath`表达式的求值。

## 语法

```javascript
xpathExpr = document.createExpression(expression, resolver);
```

| 参数 | 说明 |
| :-- | :-- |
| `expression` | 一个`DOMString`，表示要创建的`XPath`表达式。 |
| `resolver` | 允许将`XPath`表达式中的所有前缀（包括XML名称空间前缀）转换为适当的名称空间URI。 |

**返回值**: `XPathExpression`，表示`XPath`表达式的编译形式。

## 特殊情况

|  |  |
| :--- | :--- |
| **`INVALID_EXPRESSION_ERR`** | 如果根据`XPathEvaluator`的规则，该表达式不合法，则引发`INVALID_EXPRESSION_ERR`类型的`XPathException`。|
| **`NAMESPACE_ERR`** | 如果表达式包含不能由指定的`XPathNSResolver`解析的名称空间前缀，则会引发`NAMESPACE_ERROR`类型的`DOMException`。|

## 示例

下面的示例说明了`validate()`方法的用法。

```html
<div>XPath example</div>
<div>Number of &lt;div&gt;s: <output></output></div>
```

```javascript
var xpath = "//div";
var evaluator = new XPathEvaluator();
var expression = evaluator.createExpression("//div");
var result = expression.evaluate(document, XPathResult.ORDERED_NODE_SNAPSHOT_TYPE);
document.querySelector("output").textContent = result.snapshotLength;
```
