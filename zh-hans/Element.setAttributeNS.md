TOPICS: Element.setAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.setAttributeNS()`

**`setAttributeNS`** 添加一个新属性或更改具有给定命名空间和名称的一个属性的值。

## 语法

```javascript
element.setAttributeNS(namespace,name,value)
```

- `namespace` 是指定属性的命名空间的一个字符串。
- `name` 是标识要设置的属性的一个字符串。
- `value` 是新属性的所需字符串值。

## 示例

```javascript
let d = document.getElementById("d1");
d.setAttributeNS("http://www.mozilla.org/ns/specialspace", "align", "center");
```
