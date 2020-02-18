TOPICS: class attribute

# HTML 全局属性: `class`

[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes) **`class`** 定义了元素的类名，它允许 [[CSS]] 和 [[JavaScript]]
通过类选择器或DOM方法([`document.getElementsByClassName`](/zh-hans/webfrontend/Document.getElementsByClassName))
来选择和访问特定的元素。

尽管对 `class` 的命名没有要求，但 web 开发者最好使用可以表达元素语义目的的名称，而不是描述元素展现的名称（即使一个元素是斜体，但是 `class` 的命名也不应该是 `italics`）。**语义化**命名即使在页面展现发生改变时仍能合乎逻辑。

## 简单示例

```html
<h1 class="intro">标题 1</h1>
<p>段落。</p>
<p class="important">注意：这是一个很重要的段落。</p>

<style>
h1.intro {color:blue;}
p.important {color:green;}
</style>
```

## 示例：多个 `class` 类名

```html
<h1 class="intro bgColor">标题 1</h1>
<p>段落。</p>
<p class="important bgColor">注意：这是一个很重要的段落。</p>

<style>
h1.intro {
  color: blue;
}

p.important {
  color: green;
}

.bgColor {
  background: #000;
}
</style>
```

## 更多

- 所有HTML[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).
- [`element.className`](/zh-hans/webfrontend/Element.className)
- [`element.classList`](/zh-hans/webfrontend/Element.classList)
