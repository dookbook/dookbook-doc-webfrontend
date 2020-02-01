TOPICS: <aside>

# `<aside>`

**HTML `<aside>` 元素**表示一个和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。其通常表现为
**侧边栏**或者**标注框**（call-out boxes）。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *区块内容*, *可触知内容*. |
| **允许的内容** | *流式内容*. |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 所有元素接受*流式内容*。注意 `<aside>` 不能是 [`<address>`](/zh-hans/webfrontend/<address>) 元素的后代 |
| **允许的 ARIA 角色** | `feed`, `note`, `presentation`, `region`, `search` |
| **DOM 接口** | **`HTMLElement`** |

## 属性

此元素只有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

- 不要使用 `<aside>` 元素去除尾随括号内的文本 ，因为这种文本被认为是主要流内容的一部分。

## 示例

```html
<article>
  <p>
    迪斯尼电影<cite>海的女儿</cite>（<cite>The Little Mermaid</cite>）于 1989 年首次登上银幕。
  </p>
  <aside>
    在首次发行期间，该片便收获了 8700 万美元的票房。
  </aside>
  <p>
    更多有关该电影的信息…
  </p>
</article>
```
