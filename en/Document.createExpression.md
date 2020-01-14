TOPICS: Document.createExpression
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createExpression()`

This method compiles an `XPathExpression` which can then be used for (repeated) evaluations of
the `XPath` expression.

## Syntax

```javascript
xpathExpr = document.createExpression(expression, resolver);
```

| parameter | Description |
| :-- | :-- |
| `expression` | A `DOMString` representing representing the XPath expression to be created. |
| `resolver` Optional | Permits translation of all prefixes, including the XML namespace prefix, within the XPath expression into appropriate namespace URIs. |

**Return value**: A `XPathExpression` representing the compiled form of the XPath expression.

## Exceptions

|  |  |
| :-- | :-- |
| **`INVALID_EXPRESSION_ERR`** | If the expression is not legal according to the rules of the `XPathEvaluator`, an `XPathException` of type `INVALID_EXPRESSION_ERR` is raised. |
| **`NAMESPACE_ERR`** | If the expression contains namespace prefixes which cannot be resolved by the specified `XPathNSResolver`, a `DOMException` of type `NAMESPACE_ERROR` is raised. |

## Examples

The following example shows the use of the `evaluate()` method.

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
