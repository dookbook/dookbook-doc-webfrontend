TOPICS: <mark>

# HTML标记文本元素：`<mark>`

**HTML标记文本元素**（**`<mark>`**）表示**已标记**或**突出显示**的文本，以供参考或标记，因为标记的段落在封闭上下文中具有相关性或重要性。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触摸内容*. |
| **允许的内容** | *短语内容*. |
| **标签省略** | 无，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受*短语内容*的元素. |
| **允许的 ARIA 角色** | 任何 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

`<mark>`的典型用例包括：

- 当用于*引用元素*（*[`<q>`](/zh-hans/webfrontend/<q>)*）或*块级引用元素*（*[`<blockquote>`](/zh-hans/webfrontend/<blockquote>)*）时，
通常表示具有特殊意义但未在原始源材料中标记的文本，或者即使经过特殊检查也需要特别检查的材料 原始作者认为这不是特别重要。 可以将其想象为在书中使用荧光笔标记您感兴趣的段落。
- 否则，`<mark>`指示文档内容的一部分，该部分很可能与用户的当前活动有关。 例如，这可用于指示与搜索操作匹配的单词。
- 不要将`<mark>`用于语法突出显示；而是使用 *[`<span>`](/zh-hans/webfrontend/<span>)* 元素上应用适当的[[CSS]]。

!!! warn "**`<mark>`** vs. **`<strong>`**"
    不要将`<mark>`与[`<strong>`](/zh-hans/webfrontend/<strong>)元素混淆；`<mark>`用于表示具有一定程度相关性的内容，
    而 *[`<strong>`](/zh-hans/webfrontend/<strong>)* 则表示重要文本的范围。

## 示例

### 标记感兴趣的文字

在第一个示例中，使用`<mark>`元素来标记引号中用户特别感兴趣的一些文本。

```html
<blockquote>
  It is a period of civil war. Rebel spaceships, striking from a
  hidden base, have won their first victory against the evil
  Galactic Empire. During the battle, <mark>Rebel spies managed
  to steal secret plans</mark> to the Empire’s ultimate weapon,
  the DEATH STAR, an armored space station with enough power to
  destroy an entire planet.
</blockquote>
```

### 识别上下文相关段落

这个例子演示了使用`<mark>`标记段落中的搜索结果。

```html
<p>It is a dark time for the Rebellion. Although the Death
Star has been destroyed, <mark class="match">Imperial</mark>
troops have driven the Rebel forces from their hidden base and
pursued them across the galaxy.</p>

<p>Evading the dreaded <mark class="match">Imperial</mark>
Starfleet, a group of freedom fighters led by Luke Skywalker
has established a new secret base on the remote ice world of
Hoth.</p>
```

为了帮助将对搜索结果使用`<mark>`与其他可能的用法区分开，此示例将自定义类“ match”应用于每个匹配项。

## 无障碍建议

大多数屏幕阅读技术均未在默认配置中宣布`mark`元素的存在。可以通过使用[[CSS]]的 **`content`**属性以及 **`:: before`** 和 **`:: after`**伪元素来宣布。

```css
mark::before,
mark::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

mark::before {
  content: " highlight start] ";
}

mark::after {
  content: " highlight end] ";
}
```

一些使用屏幕阅读器的人有意禁用宣布会产生额外冗长内容的内容。 因此，重要的是不要滥用此技术，而应仅将其应用在不知道突出显示内容会对理解产生不利影响的情况下。

- [关于制作商标的简短说明（更易于访问）| Paciello集团](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [调整文本级别样式| 阿德里安·罗塞利（Adrian Roselli）](http://adrianroselli.com/2017/12/tweaking-text-level-styles.html)
