TOPICS: <hr>

# HTML 水平线元素 `<hr>`

**HTML `<hr>` 元素** 代表了段落级元素之间的**主题切换**：例如，故事中场景的改变或部分中主题的转移。

从历史上看，这被表示为*水平线*。尽管在视觉浏览器中仍可以将其显示为水平规则，但此元素现在是用语义术语而不是样式术语定义的，因此，如果要绘制水平线，则应使用适当的 [[CSS]]。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*。 |
| **允许的内容** | 无，它是一个 **[空元素](/zh-hans/webfrontend/empty_element)**。 |
| **标签遗漏** | 它必须具有开始标签，但不能具有结束标签。 |
| **允许的父元素** | 接受 *流式内容* 的任何元素。|
| **允许的 ARIA 角色** | `presentation` |
| **DOM 接口** | **`HTMLHRElement`** |

## 属性

该元素的属性包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| ~~`align`~~ | (**废弃**，请使用CSS) 设置**对齐方式**。如果未指定任何值，默认值为`left`（左）。|
| ~~`color`~~ | (**废弃**，请使用CSS) 设置**颜色**。值为*颜色名称*或*十六进制值*。|
| ~~`noshade`~~ | (**废弃**，请使用CSS) 设置为**无阴影**。|
| ~~`size`~~ | (**废弃**，请使用CSS) 设置**高度**，值以*像素*为单位。|
| ~~`width`~~ | (**废弃**，请使用CSS) 设置长度，值为*像素*或*百分比值*。|

## 示例

```html
<p>
  This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.
  This is the first paragraph of text.
</p>

<hr>

<p>
  This is the second paragraph of text.
  This is the second paragraph of text.
  This is the second paragraph of text.
  This is the second paragraph of text.
</p>
```
