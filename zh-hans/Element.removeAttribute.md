TOPICS: Element.removeAttribute

# `Element.removeAttribute()`

元素方法 **`removeAttribute()`** 从指定的元素中删除一个属性。

## 语法

```javascript
element.removeAttribute(attrName);
```

| 参数 | 说明 |
| :-- | :-- |
| `attrName` | 一个`DOMString`，它指定要从元素中删除的属性的名称。 如果指定的属性不存在，则`removeAttribute()`返回而不会产生错误。

## 返回值

IE 返回`boolean`类型值，其他返回`undefined`

!!! warn "注意"
    因为 `removeAttribute()` 不会返回任何有效值，你不能使用链式方法（连续使用方法，例如 `document.body.removeAttribute("first").removeAttribute("second")…`）连续移除多个属性。

## 使用说明

若要彻底移除一个属性的效果，应当使用 `removeAttribute()`，而不是使用 `setAttribute()` 将属性值设置为 `null`。对于许多属性，如果仅将其值设为 `null`，这不会造达成和预期一样的效果。

## 示例

```javascript
// Given: <div id="div1" align="left" width="200px">
document.getElementById("div1").removeAttribute("align");
// Now: <div id="div1" width="200px">
```
