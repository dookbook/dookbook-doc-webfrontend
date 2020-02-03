TOPICS: <section>

# HTML 区块（章节）元素 `<section>`

**HTML `<section>` 元素**表示一个包含在HTML文档中的**独立部分**，它没有更具体的语义元素来表示，一般来说会有包含一个标题。

例如，导航菜单应该包含在 *[`<nav>`](/zh-hans/webfrontend/<nav>)* 元素中，但搜索结果列表和地图显示及其控件没有特定元素，可以放在`<section>`里。

!!! warn "注意"
    如果元素的内容作为一个独立的有意义的集合，*[`<article>`](/zh-hans/webfrontend/<article>)* 元素可能是更好的选择。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*区块内容*，*可触知内容*。 |
| **允许的内容** | *流式内容* |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 接受*流式内容*的任何元素。请注意，`<section>`元素**不得**为 *[`<address>`](/zh-hans/webfrontend/<address>)* 元素的后代。 |
| **允许的 ARIA 角色** | `alert`, `alertdialog`, `application`, `banner`, `complementary`, `contentinfo`, `dialog`, `document`, `feed`, `log`, `main`, `marquee`, `navigation`, `search`, `status`, `tabpanel` |
| **DOM 接口** | **`HTMLElement`** |

## 属性

此元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)

## 使用说明

- 每一个`<section>`元素一般都通过是否包含一个标题
(*[`<h1>`](/zh-hans/webfrontend/<h1>)* 到 *[`<h6>`](/zh-hans/webfrontend/<h6>)* 元素)子节点来辨识。
- 如果元素的内容可以分为几个部分的话，应该使用 *[`<article>`](/zh-hans/webfrontend/<article>)* 而不是 `<section>`。
- 不要把 `<section>` 元素作为一个普通的容器来使用，这本应该是 *[`<div>`](/zh-hans/webfrontend/<div>)* 的用法。
（特别是当这个区块仅仅是为了美化样式的时候）。
一般来说，一个 `<section>` 应该出现在文档大纲中。

## 范例

之前

```html
<div>
  <h1>Heading 1</h1>
  <p>Bunch of awesome content</p>
</div>

<div>
  <h2>Heading 2</h2>
  <img src="bird.jpg" alt="bird">
</div>
```

之后

```html
<article>
  <section>
    <h1>Heading 1</h1>
    <p>Bunch of awesome content</p>
  </section>

  <section>
    <h2>Heading 2</h2>
    <img src="bird.jpg" alt="bird">
  </section>
</article>
```
