TOPICS: <h1>
        <h2>
        <h3>
        <h4>
        <h5>
        <h6>

# HTML 标题元素： `<h1>` ~ `<h6>`

**HTML 标题元素** (**`<h1>`** ~ **`<h6>`**) 代表节标题的六个级别。 `<h1>`是最高的部分级别，而`<h6>`是最低的部分级别。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*，*标题内容*，*可触摸的内容* |
| **允许的内容** | *短语内容* |
| **标签省略** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 接受*流式内容*的任何元素；不要将`<h1>`~`<h6>`元素用作[`<hgroup>`](/zh-hans/webfrontend/<hgroup>)元素的子元素 - 现在已弃用。|
| **允许的ARIA角色** | `tab`, `presentation` |
| **DOM 接口** | **`HTMLHeadingElement`** |

## 属性

这些元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

!!! warn "过时废弃"
    `align`属性已过时废弃，不要使用它。

## 使用说明

- 标题信息可以由用户代理使用。例如，自动为文档构建目录。
- 避免使用标题来调整文本大小。 而是使用[[CSS]] *`font-size`*属性。标题使用大小来指示其相对重要性，但是[[CSS]]是通用调整大小的首选。
- 避免跳过标题级别：始终从`<h1>`开始，然后再使用`<h2>`，依此类推。
- 您应该考虑避免在页面上多次使用`<h1>`。

## 示例

### 所有标题

以下代码显示了正在使用的所有标题级别。

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
<h4>四级标题</h4>
<h5>五级标题</h5>
<h6>六级标题</h6>
```

### 示例页面

以下代码显示了一些标题及其下的某些内容。

```html
<h1>元素标题</h1>
<h2>概述</h2>
<p>一些描述性文字。。。</p>

<h2>示例</h2>
<h3>示例 1</h3>
<p>示例文字。。。</p>

<h3>示例 2</h3>
<p>示例文字。。。</p>

<h2>参考</h2>
<p>参考文字。。。</p>
```

## 无障碍建议

### 导航

屏幕阅读软件用户的常用导航技术是从标题跳到标题，以快速确定页面的内容。因此，重要的是不要跳过一个或多个标题级别。这样做可能会造成混乱，因为这样导航的人可能会想知道丢失的标题在哪里。

错误用法

```html
<h1>一级标题</h1>
<h3>三级标题</h3>
<h4>四级标题</h4>
```

正确用法

```html
<h1>一级标题</h1>
<h2>二级标题</h2>
<h3>三级标题</h3>
```

### 嵌套

标题可以嵌套为小节，以反映页面内容的组织。大多数屏幕阅读器还可以生成页面上所有标题的有序列表，这可以帮助人们快速确定内容的层次结构：

1. `h1`甲虫
   1. `h2`词源
   2. `h2`分布与多样性
   3. `h2`进化
      1. `h3`晚古生代
      2. `h3`侏罗纪
      3. `h3`白垩纪
      4. `h3`新生代
   4. `h2`外部形态
      1. `h3`头
         1. `h4`口器
      2. `h3`胸部
         1. `h4`胸部
         2. `h4`翼龙
      3. `h3`腿
      4. `h3`翅膀
      5. `h3`腹部

嵌套标题时，关闭子节时标题级别可能会“跳过”。

- [标题 • 页面结构 • WAI无障碍教程](https://www.w3.org/WAI/tutorials/page-structure/headings/)
- WCAG 1.3解释
    - [1.3.1 | W3C WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/content-structure-separation-programmatic.html)
- WCAG 2.4解释
    - [2.4.1 | W3C WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-skip.html)
    - [2.4.6 | W3C WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-descriptive.html)
    - [2.4.10 | W3C WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-headings.html)

### 标签部分内容

屏幕阅读软件用户的另一种常见导航技术是生成切片内容列表，并使用它来确定页面的布局。

可以使用`aria-labelledby`和`id`属性的组合来标记节内容，该标签简明地描述了节的目的。 对于在同一页面上有多个sectioning元素的情况，此技术很有用。

示例如下:

```html
<header>
  <nav aria-labelledby="primary-navigation">
    <h2 id="primary-navigation">主导航</h2>
    <!-- 导航项 -->
  </nav>
</header>

<!-- 网页内容 -->

<footer>
  <nav aria-labelledby="footer-navigation">
    <h2 id="footer-navigation">页脚导航</h2>
    <!-- 导航项 -->
  </nav>
</footer>
```

在此示例中，屏幕阅读技术将宣布有两个[`<nav>`](/zh-hans/webfrontend/<nav>)部分，一个称为“*主导航*”，另一个称为“*页脚导航*”。
如果未提供标签，则使用屏幕阅读软件的人员可能必须调查每个导航元素的内容以确定其目的。

- [使用`aria-labelledby`属性](https://wiki.developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques/Using_the_aria-labelledby_attribute)
- [标签区域 • 页面结构 • W3C WAI 无障碍教程](https://www.w3.org/WAI/tutorials/page-structure/labels/#using-aria-labelledby)

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<h1>~<h6>` | 支持 | 支持 | 支持 |
