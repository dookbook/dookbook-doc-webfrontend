TOPICS: <embed>

# `<embed>`

HTML `<embed>` 元素将外部内容嵌入文档中的指定位置。此内容由外部应用程序或其他交互式内容源（如浏览器插件）提供。

!!! warn "Don't try this at home"
    这篇文档仅定义该元素在 HTML5 中定义的部分，不包含该元素之前的声明内容和非标准的实现。

请记住，大多数现代浏览器已经弃用并取消了对浏览器插件的支持，所以如果您希望您的网站可以在普通用户的浏览器上运行，那么依靠 `<embed>` 通常是不明智的。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*，*嵌入内容*，*交互内容*，*可触知内容*。|
| **允许的内容** | 无，它是一个*空元素*。 |
| **标签省略** | 必须具有开始标签，并且不能具有结束标签。|
| **允许的父元素** | 接受*嵌入内容*的任何元素。|
| **允许的 ARIA 角色** | `application`, `document`, `img`, `presentation`|
| **DOM 接口** | **`HTMLEmbedElement`** |

## 属性

这个元素的属性包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `height` | 资源显示的高度，in CSS pixels。  -- (Absolute values only.  NO percentages) |
| `src` | 被嵌套的资源的URL。 |
| `type` | 用于选择插件实例化的 MIME 类型。 |
| `width` | 资源显示的宽度，in CSS pixels。 -- (Absolute values only.  NO percentages) |

## 示例

```html
<embed type="video/quicktime" src="movie.mov" width="640" height="480">
```
