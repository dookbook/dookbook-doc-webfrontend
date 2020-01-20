TOPICS: Document.createNSResolver
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createNSResolver()`

Creates an `XPathNSResolver` which resolves namespaces with respect to the definitions in scope for
a specified node.

## Syntax

```javascript
nsResolver = document.createNSResolver(node);
```

| parameter | Description |
| :-- | :-- |
| `node` | is the node to be used as a context for namespace resolution. |

**Return value**: `nsResolver` is an `XPathNSResolver` object.

## Notes

Adapts any DOM node to resolve namespaces so that an XPath expression can be easily evaluated
relative to the context of the node where it appeared within the document. This adapter works
like the DOM Level 3 method `lookupNamespaceURI` on nodes in resolving the `namespaceURI` from a
given prefix using the current information available in the node's hierarchy at the time
`lookupNamespaceURI` is called. Also correctly resolves the implicit `XML` prefix.

Note, XPath defines QNames without prefix to match only elements in the null namespace. There is no
way in XPath to pick up the default namespace as applied to a regular element reference (e.g., `p[@id='_myid']`
for `xmlns='http://www.w3.org/1999/xhtml'`). To match default elements in a non-null namespace,
you either have to refer to a particular element using a form such as
`*namespace-uri()=http://www.w3.org/1999/xhtml and name()=p[@id='_myid']` (this approach works well
for dynamic XPath expressions where the namespaces might not be known) or use prefixed name tests,
and create a namespace resolver mapping the prefix to the namespace. Read more on how to create a
user defined namespace resolver if you wish to take the latter approach.

`createNSResolver` was introduced in DOM Level 3.
