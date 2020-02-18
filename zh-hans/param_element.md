TOPICS: <param>

# `<param>`

HTML `<param>`元素为[`<object>`](/zh-hans/webfrontend/<object>)元素定义参数

|  |  |
| :-- | :-- |
| **内容分类** | 无 |
| **允许内容** | 不允许，它是一个空元素（empty element）。|
| **标签省略** | 由于它是一个void元素，所以开始标签必须出现，而结束标签必须不出现。|
| **允许的父元素** | 任何以下内容（flow content](url）都可以在[`<object>`](/zh-hans/webfrontend/<object>)元素的前面作为它的父元素。|
| **DOM 接口** | `HTMLParamElement` |

## 属性

这个元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `name` | 参数的名字 |
| `value` | 确定参数的值。 |

## 示例

```html
<!-- Embed a flash movie with parameters -->
<object data="move.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
