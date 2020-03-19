TOPICS: <q>
        <q> cite attribute

# HTML 内联引用元素: `<q>`

**HTML内联引用元素** (**`<q>`**) 表示所包含的文本是**短内联引用**。大多数现代浏览器通过将文本用*引号*包含来实现此目的。此元素用于不需要段落分隔符的短引号；
对于长块级引用，请使用 *[`<blockquote>`](/zh-hans/webfrontend/<blockquote>)* 元素。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触知内容* |
| **允许的内容** | *短语内容*. |
| **标签省略** | 不允许，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受*短语内容*的元素. |
| **允许的 ARIA 角色** | 任何 |
| **DOM 接口** | **`HTMLQuoteElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`cite`** | 引用信息来源的URL。 |

## 示例

!!! warn "使用说明"
    大多数现代浏览器都会在`<q>`元素内的文本周围自动添加**引号**。在较旧的浏览器中可能需要样式规则才能添加引号。

```html
<p>According to Mozilla's website,
  <q cite="https://www.mozilla.org/en-US/about/history/details/">
    Firefox 1.0 was released in 2004 and became a big success.</q>
</p>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<q>` | 支持 | 支持 | 支持 |
