TOPICS: Element.toggleAttribute

# `Element.toggleAttribute()`

`Element` 接口的 **`toggleAttribute()`** 方法切换给定元素的某个布尔值属性的状态（如果属性存在则添加属性，属性不存在则移除属性）。

## 语法

```javascript
Element.toggleAttribute(name [, force]);
```

| 参数 | 说明 |
| :-- | :-- |
| `name` | 一个`DOMString`，它指定要切换的属性的名称。 在HTML文档中的HTML元素上调用`toggleAttribute()`时，属性名称会自动转换为所有小写字母。|
| `force` 可选 | 一个布尔值，用于确定是否应添加或删除该属性，而不管此刻是否存在该属性。|

**返回值**: 如果属性名称最终存在，则为`true`，否则为`false`。

## 异常

| 参数 | 说明 |
| :-- | :-- |
| **`InvalidCharacterError`** | 指定的属性名称包含一个或多个在属性名称中无效的字符。|

## 示例

在下面的例子中，`toggleAttribute()` 被用于切换 [`<input>`](/zh-hans/webfrontend/<input>) 的 `readonly` 属性。

```html
<input value="text">
<button>toggleAttribute("readonly")</button>
```

```javascript
var button = document.querySelector("button");
var input = document.querySelector("input");

button.addEventListener("click", function(){
  input.toggleAttribute("readonly");
});
```
