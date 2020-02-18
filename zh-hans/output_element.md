TOPICS: <output>
        <output> name attribute
        <output> for attribute
        <output> form attribute

# HTML 计算结果元素: `<output>`

**HTML `<output>` 标签** 作为计算结果输出显示 (比如执行脚本的输出)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*列出的*，*可标记的*，*可重置的*，*与表单相关的元素，可触摸的内容*。 |
| **允许元素** | *短语内容* |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 接受任何*短语内容*的元素。 |
| **允许的ARIA角色** | 任何 |
| **DOM 接口** | **`HTMLOutputElement`** |

## 属性

这个标签具有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`name`** | 定义 `<output>` 元素的唯一名称（表单提交时使用）。 |
| **`for`** | 一个或多个元素的 `id` 列表，以空格分隔，规定计算中使用的元素与计算结果之间的关系。 |
| `form` | 与当前标签有关联的 [`<form>`](/zh-hans/webfrontend/<form>)（从属的表单）。该属性的值必须是当前文档内的表单元素的`ID`。如果未指明该属性，`<output>`标签必须是一个[`<form>`](/zh-hans/webfrontend/<form>)的后代标签。该属性的用处在于可以让 `<output>` 标签脱离 [`<form>`](/zh-hans/webfrontend/<form>) 标签，存在于一个网页文档的任意位置。 |

!!! warn "注意"
    由于目前几乎所有主流浏览器都不支持`<output>`中的`form`属性，所以`<output>`不能再写在任何其它位置，它只能在[`<form>`](/zh-hans/webfrontend/<form>)元素中起作用。

## 示例

此表单提供了一个滑块，其值的范围可以在0到100之间。还提供了一个[`<input>`](/zh-hans/webfrontend/<input>)元素，您可以在其中输入第二个数字。每次将任何一个控件的值更改时，这两个数字就会加在一起，并且结果将显示在`<output>`元素中。

```html
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
  <input type="range" id="a" value="50">100
  +<input type="number" id="b" value="50">
  =<output name="x" for="a b"></output>
</form>
```
