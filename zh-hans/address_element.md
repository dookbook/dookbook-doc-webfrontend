TOPICS: <address>

# HTML 联系信息元素：`<address>`

**HTML `<address>` 元素** 包括的内容,表示某一个人或某个组织（等等）的**联系信息**。

`<address>`元素以任何形式提供的联系信息,适用于上下文的背景信息,可以是必要的任何一种联系方式，
比如*真实地址*、*[[URL]]*、*电子邮箱*、*电话号码*、*社交媒体账号*、*地理坐标*等等。此元素应该包含联系信息对应的个人、团体或组织的名称。

`<address>`可以使用在多种语境中，例如在文章开头提供商务的联系方式，或者放在 *[`<article>`](/zh-hans/webfrontend/<article>)* 元素内，指明该文章的作者。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *可触知内容*. |
| **允许的内容** | 流式内容, 不能嵌套`<address>`元素, 不能是标题内容 ([`<hgroup>`](/zh-hans/webfrontend/<hgroup>), [`<h1>`](/zh-hans/webfrontend/<h1>), [`<h2>`](/zh-hans/webfrontend/<h2>), [`<h3>`](/zh-hans/webfrontend/<h3>), [`<h4>`](/zh-hans/webfrontend/<h4>), [`<h5>`](/zh-hans/webfrontend/<h5>), [`<h6>`]((/zh-hans/webfrontend/<h6>))), 不能是区块内容 ([`<article>`](/zh-hans/webfrontend/<article>), [`<aside>`](/zh-hans/webfrontend/<aside>), [`<section>`](/zh-hans/webfrontend/<section>), [`<nav>`](/zh-hans/webfrontend/<nav>)), 不能是[`<header>`](/zh-hans/webfrontend/<header>) 或 [`<footer>`](/zh-hans/webfrontend/<footer>)元素. |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父级元素** | 父级元素可以是任何接受*流式内容*的元素，但除了 `<address>` 元素(根据对称性的逻辑原理，如果`<address>`元素作为父级元素，则不能有嵌套元素；如果有`<address>`元素,则不能用`<address>`元素作为其父级元素）。|
| **允许的 ARIA 角色** | 无 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

此元素只有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 用法说明节

- 当表示一个和联系信息无关的任意的地址时，请改用 [`<p>`](/zh-hans/webfrontend/<p>) 元素而不是 `<address>` 元素。
- 这个元素不能包含除联系信息之外的任何信息，比如出版日期（这应当被包含在 [`<time>`](/zh-hans/webfrontend/<time>) 元素之中）。
- 通常，`<address>` 元素可以放在 [`<footer>`](/zh-hans/webfrontend/<footer>) 元素之中（如果存在的话）。

## 示例

这个例子演示了如何使用 `<address>` 表示一篇文章的作者的联系信息。

```html
<address>
  You can contact author at <a href="https://dookbook.info/about/zh-hans/">
  dookbook.info</a>.<br>
  If you see any bugs, please <a href="mailto:dookbook@zhiliaokeji.com">
  contact webmaster</a>.<br>
  You may also want to visit us:<br>
  Mozilla Foundation<br>
  331 E Evelyn Ave<br>
  Mountain View, CA 94041<br>
  USA
</address>
```
