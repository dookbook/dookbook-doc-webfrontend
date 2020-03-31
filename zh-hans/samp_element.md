TOPICS: <samp>

# HTML 计算机程序输出元素 `<samp>`

`<samp>` 元素用于标识**计算机程序输出**。通常使用浏览器默认的 *`monotype`* 字体（例如 `Courier` 或 `Lucida Console`）。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*短语内容*，*可触知内容*。 |
| **允许内容** | *短语内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 任何接受 *短语内容* 的元素。 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素只包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 使用须知

!!! warn ""
    如果你需要显示由网站服务器端或者网页App计算结果的容器元素，请使用 **[`<output>`](/zh-hans/webfrontend/<output>)** 元素。

## 示例

```html
<p>Regular text. <samp>This is sample text.</samp> Regular text.</p>
```

### 样本输出包括用户输入

您可以将[`<kbd>`](/zh-hans/webfrontend/<kbd>) 元素嵌套在 `<samp>` 中显示，其中包含用户输入文本。 如文本呈现Linux（或macOS）控制台会话的记录：

```html
<pre>
<samp><span class="prompt">mike@interwebz:~$</span><kbd>md5 -s "Hello world"</kbd>
MD5 ("Hello world") = 3e25960a79dbc69b674cd4ec67a72c62

<span class="prompt">mike@interwebz:~$</span> <span class="cursor">█</span></samp></pre>
```

[`<span>`](/zh-hans/webfrontend/<span>)可以自定义示例文本的特定部分（如外壳提示和光标）的外观。
[`<kbd>`](/zh-hans/webfrontend/<kbd>) 代表用户在示例文本中的提示符下输入的命令。

```css
.prompt {
  color: #b00;
}

samp > kbd {
  font-weight: bold;
}

.cursor {
  color: #00b;
}
```

上述CSS样式仅使提示和光标具有相当细微的色彩，使输入文本增强了字体效果。

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<samp>` | 支持 | 支持 | 支持 |
