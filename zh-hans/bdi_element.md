TOPICS: <bdi>

# HTML 双向隔离元素: `<bdi>`

**HTML `<bdi>` 双向隔离元素** 会隔离可能以不同方向进行格式化的外部文本。当不知道是从什么方向嵌入文本时，如来自于数据库的文本（尤其数据库的文本方向）的时候；如在发布用户评论或其他您无法完全控制的内容时，该标签很有用。

!!! warn "注意"
    尽管同样的显示效果可以通过使用CSS规则 **`unicode-bidi`**：隔离[`<span>`](/en/webfrontend/<span>)或者其他文本格式化元素，但语义信息只能通过`<bdi>`元素传递。特别是，当浏览器允许忽略CSS样式时，在这种情况下，使用`<bdi>`仍然可以保证文本正确显示，而使用CSS样式来传递语义时就显得毫无用处。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触摸内容*。 |
| **允许的内容** | *短语内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 可包含*短语内容*的任意元素 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 示例：带有LTR文本，不用`<bdi>`时

本示例仅使用`<span>`元素列出比赛的获胜者。当名称仅包含LTR文本时，结果看起来不错：

```html
<ul>
 <li><span class="name">Henrietta Boffin</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

## 示例：带有RTL文本，不用`<bdi>`时

本示例仅使用[`<span>`](/en/webfrontend/<span>) 元素列出比赛的获胜者，其中一位获胜者的名称由RTL文本组成。在这种情况下，“- 1”（由具有中性或弱方向性的字符组成）将采用RTL文本的方向性，结果将出现乱码：

```html
<ul>
 <li><span class="name">اَلأَعْشَى</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

## 示例：使用`<bdi>`与LTR和RTL文字

本示例使用`<bdi>`元素列出比赛的获胜者。此元素指示浏览器将名称与其嵌入上下文隔离，因此示例输出应正确排序：

```html
<ul>
 <li><bdi class="name">اَلأَعْشَى</bdi> - 1st place</li>
 <li><bdi class="name">Jerry Cruncher</bdi> - 2nd place</li>
</ul>
```

## 其他示例

```html
<p dir="ltr">This arabic word <bdi>ARABIC_PLACEHOLDER</bdi> is automatically displayed right-to-left.</p>
```
