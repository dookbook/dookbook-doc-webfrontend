TOPICS: Element.setAttributeNodeNS

# `Element.setAttributeNodeNS()`

**`setAttributeNodeNS`**将新的命名空间属性节点添加到元素。

## 语法

```javascript
replacedAttr = element.setAttributeNodeNS(attributeNode)
```

- `replaceAttr`是此函数返回的替换属性节点（如果有）。
- `attributeNode`是一个`Attr`节点。

## 示例

```javascript
// <div id="one" xmlns:myNS="http://www.mozilla.org/ns/specialspace"
            myNS:special-align="utterleft">one</div>
// <div id="two">two</div>


var myns = "http://www.mozilla.org/ns/specialspace";
var d1 = document.getElementById("one");
var d2 = document.getElementById("two");
var a = d1.getAttributeNodeNS(myns, "special-align");
d2.setAttributeNodeNS(a.cloneNode(true));
alert(d2.attributes[1].value) // returns: `utterleft'
```

## 注意

如果元素上已存在指定的属性，则将该属性替换为新属性，并返回替换后的属性。

请注意，如果您尝试在不克隆节点的情况下进行设置，则Mozilla会给出`NS_ERROR_DOM_INUSE_ATTRIBUTE_ERR`"属性已在使用中"错误，因为DOM要求克隆才能重用Attr（与其他可移动节点不同）。
