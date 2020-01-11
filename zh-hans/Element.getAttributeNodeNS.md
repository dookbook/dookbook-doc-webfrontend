TOPICS: Element.getAttributeNodeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNodeNS()`

通过命名空间 URI 和名称来获取属性节点。

## 语法

```javascript
attributeNode = element.getAttributeNodeNS(namespace,nodeName)
```

| 参数 | 说明 |
| :-- | :-- |
| `attributeNode` | 获取的属性节点. |
| `namespace` | 命名空间字符串 |
| `nodeName` | 属性节点的名称. |

## 笔记

`getAttributeNodeNS` 相比 `getAttributeNode` 更加具体，允许你在特定的命名空间里获取属性. 对应的 `setter` 方法是 `setAttributeNodeNS`.
