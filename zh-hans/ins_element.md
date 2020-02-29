TOPICS: <ins>
        <ins> cite attribute
        <ins> datetime attribute

# HTML 插入文本元素 `<ins>`

**HTML `<ins>` 元素**标记已经被**插入文档中的文本**。

!!! warn "提示"
   *[`<del>`](/zh-hans/webfrontend/<del>)*和`<ins>`一起使用，描述文档中的删除和更新。浏览器通常会在已删除文本上添加一条删除线，在新插入文本下添加一条下划线。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *短语内容* 或者 *流式内容*。|
| **允许内容** | *透明内容*。|
| **标签闭合** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父级标签** | 任意*短语内容* |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLModElement`** |

## 属性

该元素支持所有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)，除此以外还支持下列属性：

| 属性 | 描述 |
| :-- | :-- |
| **`cite`** | 指向另一个文档的 URL，该文档解释了文本被插入或修改的原因。 |
| **`datetime`** | 定义文本被插入的日期和时间。并且该特性的值必须是一个有效的日期或者时间字符串。 |

!!! warn "注意"
    目前没有主流浏览器能够正确地显示 `<ins>` 标签的 `cite` 或 `datetime` 属性。

## 示例

```html
<ins>这一段文本是新插入至文档的。</ins>

<ins cite="https://dookbook.info/zh-hans/webfrontend/<ins>/">
  这一段文本是新插入至文档的。</ins>
```

## 可访问性问题

`<ins>`在大多数屏幕阅读技术均未宣布该元素在默认配置中存在。可以通过使用CSS **`content`** 属性以及
**[`::before`](zh-hans/webfrontend/::before)** 和 **[`::after`](zh-hans/webfrontend/::after)**伪元素来宣布它。

```css
ins::before,
ins::after {
  clip-path: inset(100%);
  clip: rect(1px, 1px, 1px, 1px);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

ins::before {
  content: " insertion start] ";
}

ins::after {
  content: " insertion end] ";
}
```

我们应仅在不知道插入内容，会对理解产生不利影响的情况下使用它。

- [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
- [Tweaking Text Level Styles | Adrian Roselli](http://adrianroselli.com/2017/12/tweaking-text-level-styles.html)
