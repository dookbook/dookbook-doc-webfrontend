TOPICS: Element.getAttributeNames
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNames()`

**`Element.getAttributeNames()`** 返回一个[`Array`](/zh-hans/webfrontend/Array)，该数组包含指定元素（Element）的所有属性名称，如果该元素不包含任何属性，则返回一个空数组。

将 `getAttributeNames()` 与 `getAttribute()` 组合使用， 是一种有效替代 `Element.attributes` 的使用方法.

## 语法

```javascript
let attributeNames = element.getAttributeNames();
```

## 示例

```javascript
// Iterate over element's attributes
for(let name of element.getAttributeNames())
{
  let value = element.getAttribute(name);
  console.log(name, value);
}
```
