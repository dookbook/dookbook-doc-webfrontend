TOPICS: <samp>

# HTML 计算机程序输出元素 `<samp>`

`<samp>` 元素用于标识**计算机程序输出**。通常使用浏览器默认的 *`monotype`* 字体（例如 `Courier` 或 `Lucida Console`）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触知内容*. |
| **允许内容** | *短语内容*. |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父级元素** | 任何接受 *短语内容* 的元素. |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用须知

!!! warn ""
    如果你需要显示由网站服务器端或者网页App计算结果的容器元素，请使用 **[`<output>`](/zh-hans/webfrontend/<output>)** 元素。

## 示例

```html
<p>Regular text. <samp>This is sample text.</samp> Regular text.</p>
```
