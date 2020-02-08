TOPICS: <code>

# HTML 代码元素 `<code>`

**HTML `<code>` 元素**呈现一段**计算机代码**。 默认情况下, 它以浏览器的默认*等宽字体* *`monospace`* 显示.

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触知内容*。 |
| **允许的内容** | *短语内容* |
| **标签省略** | 不允许，开始和结束标签都是不能省略的。 |
| **允许的父元素** | 任意可接受 *短语内容* 的元素。 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

此元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 示例

```html
<p>Regular text. <code>selectAll()</code> Regular text.</p>
```

## 注意

要表示多行代码，请将`<code>`元素包装在 **[`<pre>`](/zh-hans/webfrontend/<pre>)** 元素内。`<code>`元素本身仅表示*单个代码短语*或*代码行*。

[[CSS]] 规则可以覆盖浏览器默认的 `<code>` 标签样式。但用户设置的浏览器字体选项优先级高于CSS。
