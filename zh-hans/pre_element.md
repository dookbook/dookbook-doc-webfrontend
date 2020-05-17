TOPICS: <pre>

# HTML 预定义格式元素 `<pre>`

**HTML `<pre>` 元素**表示**预定义格式文本**。在该元素中的文本通常按照原文件格式编排，以*等宽字体*的形式展现出来。
文本中的*空白符*（比如空格 `Space` 和 *换行符* `Tab`）都会显示出来。(紧跟在 `<pre>` 开始标签后的第一个换行符也会被省略)

可以导致段落断开的标签（比如`<h1>`、`<p>` 和 `<address>` 标签）尽量不要包含在 `<pre>` 所定义的块里，虽然现在的浏览器（Google、IE和火狐），虽然可以把段落结束标签解释为简单地换行，但是在代码编辑器里会报错 "Invalid location of tag (h1)."

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*, *可触知内容*。|
| **允许的内容** | *短语内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何可以接受 *流式内容* 的元素。|
| **允许的 ARIA 角色** | 任何 |
| **DOM 接口** | **`HTMLPreElement`** |

## 属性

这个元素只具有[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| Attribute | Description |
| :-- | :-- |
| ~~`wrap`~~ | 指示必须如何发生溢出的提示。在现代浏览器中，此提示被忽略，并且当前没有视觉效果。为了达到这样的效果，请改用CSS **`white-space`**。 |

## 简单示例

```html
<p>Using CSS to change the font color is easy.</p>
<pre>
body {
  color: red;
}
</pre>
```

## `<pre>`中的HTML 代码字符转义

```html
<pre>
&lt;html&gt;
</pre>  <!-- 请注意使用符号实体来转义 -->
```

如果您希望使用 `<pre>` 标签来定义**计算机源代码**，请结合 **[`<code>`](/zh-hans/webfrontend/<code>)** 元素一起使用，以获得更加精确的语义。

```html
<pre><code>
&lt;html&gt;  <!-- 请注意使用符号实体来转义 -->
</code></pre>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<pre>` | 支持 | 支持 | 支持 |
