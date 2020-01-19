TOPICS: Document.createNSResolver

# `Document.createNSResolver()`

创建一个`XPathNSResolver`，用于解析指定命名空间范围内的名称空间

## 语法

```javascript
nsResolver = document.createNSResolver(node);
```

| 参数 | 说明 |
| :-- | :-- |
| `node` | 是用作名称空间解析的上下文的节点。|

**返回值**: `nsResolver`是`XPathNSResolver`对象

## 注意

调整任何DOM节点以解析名称空间，以便可以相对于`XPath`表达式相对于其在文档中出现的节点的上下文进行评估。此适配器的工作方式类似于节点上的DOM级别3方法`lookupNamespaceURI`，它使用调用`lookupNamespaceURI`时节点层次结构中的当前信息从给定的前缀解析`namespaceURI`。还可以正确解析隐式XML前缀。

注意，`XPath`定义了没有前缀的QName，以仅匹配`null`命名空间中的元素。`XPath`中没有办法选择应用于常规元素引用的默认名称空间（例如，
`xmlns ='http：//www.w3.org/1999/xhtml'的p [@id ='_ myid']`。要匹配非`null`命名空间中的默认元素，您必须使用
`*namespace-uri（）= http：//www.w3.org/1999/xhtml和name（）= p [@id ='_ myid']`（此方法适用于名称空间可能未知的动态`XPath`表达式）或使用带前缀的名称测试，并创建一个将名称前缀映射到名称空间的名称空间解析器。如果希望采用后一种方法，请阅读有关如何创建用户定义的名称空间解析器的更多信息。

`createNSResolver`在DOM级别3中引入。
