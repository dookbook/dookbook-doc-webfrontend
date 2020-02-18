TOPICS: <footer>

# HTML 页脚元素：`<footer>`

**HTML `<footer>` 元素**表示最近一个章节内容或者根节点（sectioning root ）元素的页脚。一个页脚通常包含该章节*作者*、*版权数据*或者*与文档相关的链接*等信息。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*可触知内容*。|
| **允许的内容** | *流式内容*，但是不能包含 ~~`<footer>`~~ 或者 ~~[`<header>`](/zh-hans/webfrontend/<header>)~~。|
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接收*流式内容*的元素。注意`<footer>`元素必须不能是 *[`<address>`](/zh-hans/webfrontend/<address>)*, *[`<header>`](/zh-hans/webfrontend/<header>)* 或者另一个 *`<footer>`* 元素的后代。|
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

- [`<address>`](/zh-hans/webfrontend/<address>) 元素中的作者信息可以包含在 `<footer>` 元素内。
- `<footer>` 元素不是*段落内容*，因此在大纲中不能包含新的章节。

!!! warn "提示"
    假如您使用`<footer>`元素来插入联系信息，应该在`<footer>`元素内使用[`<address>`](/zh-hans/webfrontend/<address>)标签。

## 示例

```html
<article>
  <!-- 此处为主体内容 -->

  <footer>
    一些关于此<code>&lt;article&gt;<code>中内容的版权信息或作者信息？
    <address>由某某撰写。</address>
  </footer>
```
