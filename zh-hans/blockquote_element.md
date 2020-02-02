TOPICS: <blockquote>
        <blockquote> cite attribute

# HTML 块级引用元素: `<blockquote>`

**HTML 块级引用元素**（**`<blockquote>`**），代表其中的文字是**引用内容**。通常在渲染时，这部分的内容会有一定的缩进。
若引文来源于网络，则可以将原内容的出处 URL 地址设置到 *`cite`* 属性上，若要以文本的形式告知读者引文的出处时，
可以通过 *[`<cite>`](/zh-hans/webfrontend/<cite>)* 元素。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *章节根节点*, *可触摸内容*.|
| **允许的内容** | *流式内容* |
| **标签省略** | 不允许，开始和结束标签都是必需的 |
| **允许的父元素** | 任意可包含*流式内容*的元素 |
| **允许的ARIA角色** | 任意 |
| **DOM 接口** | **`HTMLQuoteElement`** |

## 属性

此元素的属性包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| **`cite`** | 标注引用信息的来源URL。|

## 使用备注

若要修改被引用内容的缩进距离，可以使用 CSS **`margin-left`** 和/或 **`margin-right`** 属性，或使用 **`margin`** 缩写属性。

若想使用在行内引用较短的内容而非创建一个单独的引用块，可使用 **[`<q>`](/zh-hans/webfrontend/<q>)** 元素。

## 示例

下面的这个例子演示了使用`<blockquote>`元素引用一段来自[RFC 1149](https://tools.ietf.org/html/rfc1149) (信鸽IP通讯传输标准)的内容。

```html
<blockquote cite="https://tools.ietf.org/html/rfc1149">
  <p>Avian carriers can provide high delay, low
  throughput, and low altitude service.  The
  connection topology is limited to a single
  point-to-point path for each carrier, used with
  standard carriers, but many carriers can be used
  without significant interference with each other,
  outside of early spring.  This is because of the 3D
  ether space available to the carriers, in contrast
  to the 1D ether used by IEEE802.3.  The carriers
  have an intrinsic collision avoidance system, which
  increases availability.</p>
</blockquote>
```
