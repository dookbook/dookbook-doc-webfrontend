TOPICS: Document.evaluate
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.evaluate()`

Returns an `XPathResult` based on an XPath expression and other given parameters.

## Syntax

```javascript
var xpathResult = document.evaluate(
  xpathExpression,
  contextNode,
  namespaceResolver,
  resultType,
  result
);
```

| parameter | Description |
| :-- | :-- |
| `xpathExpression` | is a string representing the XPath to be evaluated. |
| `contextNode` | specifies the context node for the query (see the XPath specification). It's common to pass `document` as the context node. |
| `namespaceResolver` | is a function that will be passed any namespace prefixes and should return a string representing the namespace URI associated with that prefix. It will be used to resolve prefixes within the XPath itself, so that they can be matched with the document. `null` is common for HTML documents or when no namespace prefixes are used. |
| `resultType` | is an integer that corresponds to the type of result `XPathResult` to return. Use named constant properties, such as `XPathResult.ANY_TYPE`, of the `XPathResult` constructor, which correspond to integers from `0` to `9`. |
| `result` | is an existing `XPathResult` to use for the results. `null` is the most common and will create a new `XPathResult` |

## Examples

```javascript
var headings = document.evaluate("/html/body//h2", document, null, XPathResult.ANY_TYPE, null);
/* Search the document for all h2 elements.  
 * The result will likely be an unordered node iterator. */
var thisHeading = headings.iterateNext();
var alertText = "Level 2 headings in this document are:\n";
while (thisHeading) {
  alertText += thisHeading.textContent + "\n";
  thisHeading = headings.iterateNext();
}
alert(alertText); // Alerts the text of all h2 elements
```

Note, in the above example, a more verbose XPath is preferred over common shortcuts such as `//h2`.
Generally, more specific XPath selectors as in the above example usually gives a significant performance
improvement, especially on very large documents. This is because the evaluation of the query spends
does not waste time visiting unnecessary nodes. Using // is generally slow as it visits every node
from the root and all subnodes looking for possible matches.

Further optimization can be achieved by careful use of the context parameter. For example, if you
know the content you are looking for is somewhere inside the body tag, you can use this:

```javascript
document.evaluate(".//h2", document.body, null, XPathResult.ANY_TYPE, null);
```

Notice in the above `document.body` has been used as the context instead of `document` so the XPath
starts from the body element. (In this example, the `"."` is important to indicate that the querying
should start from the context node, `document.body`. If the `"."` was left out (leaving `//h2`) the query
would start from the root node (HTML) which would be more wasteful.)

## Notes

- XPath expressions can be evaluated on HTML and XML documents.
- While using `document.evaluate()` works in FF2, in FF3 one must use `someXMLDoc.evaluate()` if
evaluating against something other than the current document
