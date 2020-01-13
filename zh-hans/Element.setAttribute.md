TOPICS: Element.setAttribute

# `Element.setAttribute()`

设置指定元素上的某个属性值。如果属性已经存在，则更新该值；否则，使用指定的名称和值添加一个新的属性。

要获取某个属性当前的值，可使用 `getAttribute()`；要删除某个属性，可使用 `removeAttribute()`。

## 语法

```javascript
element.setAttribute(name, value);
```

| 参数 | 说明 |
| :-- | :-- |
| `name` | 表示属性名称的字符串。一个`DOMString`，它指定要设置其值的属性的名称。 在HTML文档中的HTML元素上调用`setAttribute()`时，属性名称将自动转换为所有小写字母。
| `value` | 属性的值/新值。包含要分配给属性的值的`DOMString`。 指定的任何非字符串值都将自动转换为字符串。

当在 HTML 文档中的 HTML 元素上调用 `setAttribute()` 方法时，该方法会将其属性名称（attribute name）参数小写化。

如果指定的属性已经存在，则其值变为传递的值。如果不存在，则创建指定的属性。

尽管对于不存在的属性，`getAttribute()` 返回 `null`，你还是应该使用 `removeAttribute()` 代替 `elt.setAttribute(attr, null)` 来删除属性。

如果布尔属性完全存在于元素上，则将其视为`true`，而与它们的实际`value`; 无关。 通常，您应该在`value`中指定一个空字符串(`""`)（某些人使用该属性的名称；此方法有效，但不标准）。请参见下面的示例以进行实际演示。

由于将指定的值转换为字符串，因此指定`null`不一定能达到您的期望。 而不是删除属性或将其值设置为`null`，而是将属性的值设置为字符串`"null"`。 如果要删除属性，请调用`removeAttribute()`。

**返回值**: `undefined`

## 例外情况

|  |  |
| :-- | :-- |
| **`InvalidCharacterError`** | 指定的属性名称包含一个或多个在属性名称中无效的字符。|

## 示例

在下面的例子中，`setAttribute()` 被用于设置 [`<button>`](/zh-hans/webfrontend/<button>) 上的属性。

```html
<button>Hello World</button>
```

```javascript
var b = document.querySelector("button");

b.setAttribute("name", "helloButton");
b.setAttribute("disabled", "");
```

这说明了两件事：

- 上面对`setAttribute()`的第一次调用显示了将`name`属性的值更改为`"helloButton"`。 您可以使用浏览器的页面检查器（Chrome，Edge，Firefox，Safari）查看此内容。
- 要设置布尔属性的值（例如禁用），可以指定任何值。 建议使用空字符串或属性名称。 重要的是，如果根本不存在该属性，则不管其实际值如何，都将其值视为真实。 该属性的缺失表示其值是`false`。 通过将`Disabled`属性的值设置为空字符串（`""`），我们将`disable`设置为`true`，这将导致按钮被禁用。
