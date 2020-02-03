TOPICS: <bdi>

# `<bdi>`

**HTML `<bdi>` 元素** (双向隔离元素) 会隔离可能以不同方向进行格式化的外部文本。
当不知道是从什么方向嵌入文本时，如来自于数据库的文本（尤其数据库的文本方向）的时候；如在发布用户评论或其他您无法完全控制的内容时，该标签很有用。

*双向文本：* 既可以包含从左到右（LTR）排列的字符序列又可以从右到左（RTL）排列的字符序列的文本，例如：嵌入英语字符串中的阿拉伯语。浏览器实现 [Unicode双向算法](https://www.w3.org/International/articles/inline-bidi-markup/uba-basics)来处理此问题。在此算法中，字符被赋予了隐式的方向性：例如，拉丁字符被视为LTR，而阿拉伯字符被视为RTL。其他一些字符（例如空格和标点符号）被视为中性，并根据其周围字符的方向性分配了方向性。

通常，双向算法将做正确的算法，而无需作者提供任何特殊的标记，但是有时该算法需要帮助。那就是<bdi>进来的地方。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | 流式内容，短语内容，可触摸内容。 |
| **允许的内容** | 短语内容。 |
| **标签略写** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 可包含*短语内容*的任意元素 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

| 属性 | 描述 |
| :-- | :-- |
| `dir` | 如同其他HTML元素一样，它包含全局属性，但是有一些语义上的细微差别：`dir`属性不继承父元素。如果没有设置，默认值即为`auto`，以便浏览器根据元素内容决定元素内容的方向。 |

## 使用说明

用`<bdi>`元素包装一段文本，即使用双向算法把这篇文章与周围的环境分开来看。这个元素有两种优点:

- 嵌入文本`<bdi>`的方向不会影响周围文本的方向性。
- 嵌入文本的方向`<bdi>`不受周围文本的方向性的影响。

例如，考虑以下文本：

```html
EMBEDDED-TEXT - 1st place
```

如果 `EMBEDDED-TEXT` 是LTR, 则可以正常工作。但是`EMBEDDED-TEXT` 是 RTL,那么- 1则将被视为RTL文本（因为它由中性和弱字符组成）。结果将出现乱码：

```html
1 - EMBEDDED-TEXTst place
```

如果你提前知道 `EMBEDDED-TEXT`的方向性,您可以修复由`EMBEDDED-TEXT`包装问题，在[`<span>`](/en/webfrontend/<span>)或 `dir` 属性中设置为已知的方向性。但是，如果您不知道方向性（例如，由于`EMBEDDED-TEXT`正从数据库中读取或由用户输入），则应使用该方法`<bdi>`来防止方向性`EMBEDDED-TEXT`影响周围环境。

尽管`unicode-bidi: isolate`在[`<span>`](/en/webfrontend/<span>)或另一个文本格式元素上使用CSS规则可以实现相同的视觉效果，但在HTML中作者不建议使用此方法，因为它不符合语义，并且允许浏览器忽略CSS样式。

将字符嵌入`<span dir="auto">`或使用`<bdi>`的视觉效果相同，但是其语义不太确定。

## 示例

### 带有LTR文本，不用`<bdi>`时

本示例仅使用`<span>`元素列出比赛的获胜者。当名称仅包含LTR文本时，结果看起来不错：

```html
<ul>
 <li><span class="name">Henrietta Boffin</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

### 带有RTL文本，不用`<bdi>`时

本示例仅使用[`<span>`](/en/webfrontend/<span>) 元素列出比赛的获胜者，其中一位获胜者的名称由RTL文本组成。在这种情况下，“-1”（由具有中性或弱方向性的字符组成）将采用RTL文本的方向性，结果将出现乱码：

```html
<ul>
 <li><span class="name">اَلأَعْشَى</span> - 1st place</li>
 <li><span class="name">Jerry Cruncher</span> - 2nd place</li>
</ul>
```

### 使用`<bdi>`与LTR和RTL文字

本示例使用`<bdi>`元素列出比赛的获胜者。此元素指示浏览器将名称与其嵌入上下文隔离，因此示例输出应正确排序：

```html
<ul>
 <li><bdi class="name">اَلأَعْشَى</bdi> - 1st place</li>
 <li><bdi class="name">Jerry Cruncher</bdi> - 2nd place</li>
</ul>
```

### 其他示例

```html
<p dir="ltr">This arabic word <bdi>ARABIC_PLACEHOLDER</bdi> is automatically displayed right-to-left.</p>
```
