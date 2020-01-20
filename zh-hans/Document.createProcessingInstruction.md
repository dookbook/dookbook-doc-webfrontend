TOPICS: Document.createProcessingInstruction

# `Document.createProcessingInstruction()`

**`createProcessingInstruction()`** 创建一个新的处理指令节点，并返回。

## 语法

```javascript
piNode = document.createProcessingInstruction(target, data)
```

- `piNode` is the resulting `ProcessingInstruction` node.

| 参数 | 说明 |
| :-- | :-- |
| `target` | 是指处理指令节点的`target`部分(i.e., `<?target … ?>`) |
| `data` | 是一个字符串，其中包含目标后面的处理指令应携带的任何信息。 数据由您决定，但不能包含?>，因为这会关闭处理指令。|

## 例外情况

`DOM_INVALID_CHARACTER`

如果满足以下任一条件，则抛出：

- 处理指令目标无效-它应该是有效的XML名称，不包含`"XML"`，`"XML"`或两者的任何大小写组合，除了`<？xml-stylesheet？>`之类的标准化名称之外。
- 关闭处理指令序列（？>）是数据的一部分。

## 示例

```javascript
// 该函数用来从本文档的第一个iframe中获取第一个element元素，
// 并插入到当前文档树中
function getEle(){
  var iframe = document.getElementsByTagName("iframe")[0],
    ele = iframe.contentWindow.document.body.firstElementChild
    if(ele){
      document.body.appendChild(document.adoptNode(ele))
    }else{
      alert("没有更多元素了")
    }
}
document.getElementById("move").onclick = getEle
```

```javascript
var doc = new DOMParser().parseFromString('<foo />', 'application/xml');
var pi = doc.createProcessingInstruction('xml-stylesheet', 'href="mycss.css" type="text/css"');

doc.insertBefore(pi, doc.firstChild);

console.log(new XMLSerializer().serializeToString(doc));
// Displays: <?xml-stylesheet href="mycss.css" type="text/css"?><foo/>
```
