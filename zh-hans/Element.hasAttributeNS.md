TOPICS: Element.hasAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasAttributeNS()`

**`hasAttributeNS`** 返回一个布尔值，指示该元素是否包含有指定的属性（attribute）。

## 语法

```javascript
result =element.hasAttributeNS(namespace,localName)
```

- `result` 为返回的布尔值：`true` 或 `false`。
- `namespace` 是一个字符串，表示属性的命名空间。
- `localName` 是一个字符串，表示属性的名称。

## 示例

```javascript
// 在为属性设置值之前检测该属性是否存在
var d = document.getElementById("div1");
if (d.hasAttributeNS(
        "http://www.mozilla.org/ns/specialspace/",
        "special-align")) {
   d.setAttribute("align", "center");
}
```
