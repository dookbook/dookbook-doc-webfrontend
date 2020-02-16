TOPICS: <output>

# HTML 计算结果元素 `<output>`

**HTML `<output>` 标签** 作为计算结果输出显示 (比如执行脚本的输出)。

|  |  |
| :-- | :-- |
| **内容分类** | *流式元素*，*短语元素*，*列出的*，*可标记的*，*可重置的*，*与表单相关的元素，可触摸的内容*. |
| **允许元素** | *短语元素* |
| **省略标签** | 不允许，开始标签和结束标签都不能省略。|
| **允许父元素** | 接受任何*短语内容*的元素 |
| **允许ARIA角色** | 任何 |
| **DOM 接口** | **`HTMLOutputElement`** |

## 属性

这个标签具有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `for` | 一个或多个元素的 `id` 列表，以空格分隔，规定计算中使用的元素与计算结果之间的关系。 |
| `form` | 与当前标签有关联的 [`<form>`](/zh-hans/webfrontend/<form>)（从属的表单）。该属性的值必须是当前文档内的表单元素的`ID`。如果未指明该属性，`<output>`标签必须是一个[`<form>`](/zh-hans/webfrontend/<form>)的后代标签。该属性的用处在于可以让 `<output>` 标签脱离 [`<form>`](/zh-hans/webfrontend/<form>) 标签，存在于一个网页文档的任意位置。 |
| `name` | 定义 `<output>` 元素的唯一名称（表单提交时使用）。 |

!!! "注意"
    `<output>` 中 `form` 属性由于目前几乎所有主流浏览器都不支持它，所以`<output>`不能再写在其它任意位置，只能在[`<form>`](/zh-hans/webfrontend/<form>)元素里面才有效果。

## 示例

```html
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
  <input type="range" id="a" value="50">100
  +<input type="number" id="b" value="50">
  =<output name="x" for="a b"></output>
</form>
```
