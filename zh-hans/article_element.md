TOPICS: <article>

# HTML 独立自包含元素： `<article>`

**HTML `<article>` 元素**表示*文档*、*页面*、*应用*或*网站*中的**独立结构**，其意在成为**可独立分配的或可复用的结构**，如在发布中，它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。​​

给定文档中可以包含多篇文章；例如，阅读器在博客上滚动时一个接一个地显示每篇文章的文本，每个帖子将包含在`<article>`元素中，可能包含一个或多个[`<section>`](/zh-hans/webfrontend/<section>)。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*区块内容*，*可触知内容*。 |
| **允许的内容** | *流式内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 所有接受*流式内容*的元素。注意`<article>`元素不能成为 *[`<address>`](/zh-hans/webfrontend/<address>)* 元素的子元素。|
| **允许的 ARIA 角色** | `application`, `document`, `feed`, `main`, `presentation`, `region` |
| **DOM 实例** | **`HTMLElement`** |

## 属性

此元素只具有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

- 每个`<article>`，通常包括标题元素（[`<h1>`](/zh-hans/webfrontend/<h1>) - [`<h6>`](/zh-hans/webfrontend/<h6>)）。
- 当`<article>`元素嵌套使用时，则该元素代表与外层元素有关的文章。例如，代表博客评论的`<article>`元素可嵌套在代表博客文章的`<article>`元素中。
- `<article>`元素的作者信息可通过[`<address>`](/zh-hans/webfrontend/<address>)元素提供，但是不适用于嵌套的`<article>`元素。
- 可以使用 *[`<time>`](/zh-hans/webfrontend/<time>)* 元素的 *`datetime`* 属性来描述`<article>`元素的发布日期和时间。
**请注意[`<time>`](/zh-hans/webfrontend/<time>)的`pubdate`属性不再是W3C HTML5标准。**

## 示例

```html
<article class="film_review">
  <header>
    <h2>Jurassic Park</h2>
  </header>
  <section class="main_review">
    <p>Dinos were great!</p>
  </section>
  <section class="user_reviews">
    <article class="user_review">
      <p>Way too scary for me.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-16 19:00">May 16</time>
          by Lisa.
        </p>
      </footer>
    </article>
    <article class="user_review">
      <p>I agree, dinos are my favorite.</p>
      <footer>
        <p>
          Posted on
          <time datetime="2015-05-17 19:00">May 17</time>
          by Tom.
        </p>
      </footer>
    </article>
  </section>
  <footer>
    <p>
      Posted on
      <time datetime="2015-05-15 19:00">May 15</time>
      by Staff.
    </p>
  </footer>
</article>
```
