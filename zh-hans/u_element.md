TOPICS: <u>

# HTML 非文本注释 `<u>`

**`<u>` 元素** 在HTML4中废弃，但是在HTML5中重新被定义，意思是：将文本标记为 **非文本注释**。例如：汉语中的专有名词或拼写错误。样式呈现为 **下划线**。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*，*短语内容*，*可触知内容*。|
| **允许的内容** | *短语内容* |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受*短语内容*的元素。|
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

这个元素仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用说明

!!! warn "注意"
    在可能和超链接混淆的地方，避免使用 `<u>`。因为超链接的默认样式，也是下划线。

## 用例

`<u>`元素的有效用例包括**注解拼写错误**，**中文文本中的专有名称**等。

### 表示拼写错误

此示例使用`<u>`元素和一些 CSS 来显示包含拼写错误的段落：

HTML

```html
<p>This paragraph includes a <u class="spelling">wrnogly</u>
spelled word.</p>
```

在HTML中，我们看到 `<u>` 使用了一个类 `spelling`，用于表示“wrongly”一词的拼写错误。

```css
u.spelling {
  text-decoration: red wavy underline;
}
```

这个CSS表示它的文本下面应该有一个红色的波浪下划线。这是拼写错误的常见样式。也可以使用另一种常见样式 *`red dashed underline`*。

## 避免使用 `<u>` 的场景

以下是一些避免使用`<u>`的用例场景：

### 非语义下划线

您不应该使用`<u>`简单地为文字加下划线。要为文本加下划线，您应该使用 **`text-decoration: underline`** 的CSS样式，如下所示：

```html
<span class="underline">Today's Special</span>
<br>
Chicken Noodle Soup With Carrots
```

```css
.underline {
  text-decoration: underline;
}
```

### 表示书名

您不应该使用`<u>`表示*书籍的标题*，应使用 **[`<cite>`](/zh-hans/webfrontend/<cite>)** 元素。

```html
<p>The class read <cite>Moby Dick</cite> in the first term.</p>
```

请注意: [`<cite>`](/zh-hans/webfrontend/<cite>) 元素的默认样式会以斜体显示文本。可以使用CSS改变它的样式：

```css
cite {
  font-style: normal;
  text-decoration: underline;
}
```

### 其他相关的 HTML 元素

在大多数情况下，您应该使用`<u>`以外的元素，例如：

- *[`<em>`](/zh-hans/webfrontend/<em>)* 表示强调重点。
- *[`<b>`](/zh-hans/webfrontend/<b>)* 提示注意文字。
- *[`<mark>`](/zh-hans/webfrontend/<mark>)* 标记关键词或短语。
- *[`<strong>`](/zh-hans/webfrontend/<strong>)* 表明文本具有重要意义。
- *[`<i>`](/zh-hans/webfrontend/<i>)* 表示西方文本中的技术术语，音译，思想或船名。
- *[`<cite>`](/zh-hans/webfrontend/<cite>)* 标记书名时或创意作品引用元素。

要提供文本注释（与使用`<u>`创建的非文本注释相对），请使用 [`<ruby>`](/zh-hans/webfrontend/<ruby>) 元素。

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<u>` | 支持 | 支持 | 支持 |
