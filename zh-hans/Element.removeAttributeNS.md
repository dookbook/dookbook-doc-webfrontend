TOPICS: Element.removeAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.removeAttributeNS()`

`removeAttributeNS` 移除元素的指定属性

!!! warn ""
    在Firefox 3及更高版本中，此方法会将DOM值重置为其默认值。

## 语法

```javascript
element.removeAttributeNS(namespace,attrName);
```

- `namespace` 包含当前属性的`namespace`字符串
- `attrName` 当前移除的属性名字符串

## 示例

```javascript
// <div id="div1" xmlns:special="http://www.mozilla.org/ns/specialspace"
//      special:specialAlign="utterleft" width="200px" />
d = document.getElementById("div1");
d.removeAttributeNS("http://www.mozilla.org/ns/specialspace", "specialAlign");
// now: <div id="div1" width="200px" />
```
