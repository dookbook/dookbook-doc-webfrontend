TOPICS: Document.createCDATASection
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.createCDATASection()`

**`createCDATASection()`**创建一个新的`CDATA`节节点，并将其返回。

## 语法

```javascript
var CDATASectionNode = document.createCDATASection(data);
```

- `CDATASectionNod`e是`CDATA`节节点。
- `data`是一个字符串，其中包含要添加到`CDATA`节中的数据。

## 示例

```javascript
var docu = new DOMParser().parseFromString('<xml></xml>', 'application/xml')

var cdata = docu.createCDATASection('Some <CDATA> data & then some');

docu.getElementsByTagName('xml')[0].appendChild(cdata);

alert(new XMLSerializer().serializeToString(docu));
// Displays: <xml><![CDATA[Some <CDATA> data & then some]]></xml>
```

## 笔记

- 这仅适用于XML，不适用于HTML文档（因为HTML文档不支持CDATA部分）；在HTML文档上尝试将其抛出`NOT_SUPPORTED_ERR`。
- 如果试图将结束的CDATA序列（`"]]>"`）作为数据的一部分提交，将抛出`NS_ERROR_DOM_INVALID_CHARACTER_ERR`异常，因此，如果不使用此方法获取此异常（`createTextNode()`通常可以在其位置使用）。
