TOPICS: Element.hasAttribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.hasAttribute()`

**`hasAttribute`** 返回一个布尔值，指示该元素是否包含有指定的属性（attribute）。

## 语法

```javascript
var result = element.hasAttribute(attName);
```

- `result` 为返回的布尔值：`true` 或 `false`。
- `attName` 是一个字符串，表示属性的名称。

## 示例

```javascript
// 在为属性设置新值前检测该属性是否存在
var d = document.getElementById("div1");

if (d.hasAttribute("align")) {
  d.setAttribute("align", "center");
}
```
