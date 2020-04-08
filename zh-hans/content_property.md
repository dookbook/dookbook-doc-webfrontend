TOPICS: content property
        counter-increment property
        counter-reset property

# CSS 插入内容属性: `content`

CSS的 **`content`** CSS 属性用于在元素的 [`::before`](/zh-hans/webfrontend/::before) 和 [`::after`](/zh-hans/webfrontend/::after)
伪元素中**插入内容**。使用 `content` 属性插入的内容都是匿名的可替换元素。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 空 |
| **`normal`** | 正常，默认是`none` |
| **`counter`** | 设定计数器内容 |
| **`attr(attribute)`** | 作为选择器的属性之一 |
| **`string`** | 设置Content到你指定的文本 |
| **`open-quote`** | 开口引号 |
| **`close-quote`** | 闭合引号 |
| **`no-open-quote`** | 如果指定，移除内容的开始引号 |
| **`no-close-quote`** | 如果指定，移除内容的闭合引号 |
| **url(url)** | 媒体（图像，声音，视频等内容）URL地址 |
| **`inherit`** | 从父元素继承 |

## CSS 属性: `counter-increment`

**`counter-increment`** 属性**递增一个**或**多个计数器值**。通常用于 *`counter-reset`* 属性和 *`content`* 属性。

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 没有计数器将递增 |
| **custom-ident** | 要递增的**计数器名称** |
| **integer** | **计数器的值**。如果没有给出，默认为`1` |

## CSS 属性: `counter-reset`

**`counter-reset`** 属性**创建**或**重置一个**或**多个计数器**。通常是和 *`counter-increment`* 属性，*`content`* 属性一起使用。

| 属性值 | 说明 |
| :--- | :--- |
| **`none`** | 默认。不能对选择器的计数器进行重置 |
| **custom-ident** | 要重置的计数器名称 |
| **integer** | 每次出现元素时将计数器重置为的值。如果未指定，则默认为`0` |

## 简单示例

```html
<h1>5</h1>
<p> We shall start this with a quote from Sir Tim Berners-Lee,
    <q cite="http://www.w3.org/People/Berners-Lee/FAQ.html#Internet">
        I was lucky enough to invent the Web at the time when the Internet already existed - and had for a decade and a half.</q>  We must understand that there is nothing fundamentally wrong with building on the contributions of others.
</p>

<h1>6</h1>
<p> Here we shall quote the Mozilla Manifesto,
    <q cite="http://www.mozilla.org/en-US/about/manifesto/">
        Individuals must have the ability to shape the Internet and their own experiences on the Internet.</q> And so, we can infer that contributing to the open web, can protect our own individual experiences on it.
</p>
```

```css
q {
  color: #00008b;
  font-style: italic;
}

q::before { content: open-quote; }
q::after { content: close-quote; }

h1::before { content: "Chapter "; }
```

## 示例: 使用 `counter-increment` 和 `counter-reset` 属性

```html
<body>
  <h1>HTML tutorials</h1>
  <h2>HTML Tutorial</h2>
  <h2>XHTML Tutorial</h2>
  <h2>CSS Tutorial</h2>

  <h1>Scripting tutorials</h1>
  <h2>JavaScript</h2>
  <h2>VBScript</h2>

  <h1>XML tutorials</h1>
  <h2>XML</h2>
  <h2>XSL</h2>
</body>
```

```css
body { counter-reset: section; }

h1 { counter-reset: subsection; }

h1:before {
  counter-increment: section;
  content: "Section " counter(section) ". ";
}

h2:before {
  counter-increment: subsection;
  content: counter(section) "." counter(subsection) " ";
}
```
