TOPICS: <header>

# HTML 介绍性内容元素： `<header>`

HTML `<header>` 元素用于展示**介绍性内容**，通常包含一组*介绍性的*或是*辅助导航的*实用元素。它可能包含一些标题元素，
但也可能包含其他元素，比如 Logo、搜索框、作者名称，等等。

## 技术摘要

|||
| :-- | :--|
| **内容类型** | *流式内容*，*可触知内容*。|
| **允许的内容** | *流式内容*，但是不允许 ~~`<header>`~~ 或 ~~[`<footer>`](/zh-hans/webfrontend/<footer>)~~ 成为子元素 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受*流式内容*的元素。注意 `<header>` 元素不能作为 *[`<address>`](/zh-hans/webfrontend/<address>)*、*[`<footer>`](/zh-hans/webfrontend/<footer>)* 或另一个 *`<header>`* 元素的子元素。|
| **允许的 ARIA 角色** | `group` ，`presentation` |
| **DOM 接口** | **`HTMLElement`** |

## 使用提示

`<header>` 元素不是 *段落内容*，因此不会往 大纲 中引入新的段落。也就是说，`<header>` 元素通常用于包含周围部分的标题（`<h1>` 至 `<h6>` 元素），但这**不是**必需的。

## 属性

此元素仅拥有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 示例

### 页面的页首

```html
<header>
  <h1>主页标题</h1>
  <img src="mdn-logo-sm.png" alt="MDN logo">

  <!-- 可带页面导航 -->
  <nav>
    <a href="/home/" title="首页">首页</a>
    <a href="/tab1/" title="导航 1">导航 1</a>
    <a href="/tab2/" title="导航 2">导航 2</a>
  </nav>
</header>
```

### 文章的头部

```html
<article>
  <header>
    <h2>The Planet Earth</h2>
    <p>Posted on Wednesday, 4 October 2017 by Jane Smith</p>
  </header>
  <p>We live on a planet that's blue and green, with so many things still unseen.</p>
  <p><a href="https://dookbook.info/">继续阅读。。。</a></p>
</article>
```
