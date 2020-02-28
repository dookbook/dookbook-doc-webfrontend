TOPICS: <kbd>

# HTML 键盘输入元素 `<kbd>`

**HTML 键盘输入元素** (**`<kbd>`**) 用于表示**用户输入**（**键盘输入**、**语音输入**、或其他**文本输入设备**）。
它是一个行内元素，以浏览器的默认 *`monospace`* 字体显示。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*, *可触知内容* |
| **允许的内容** | *短语内容*。 |
| **标签省略** | 不允许，开始和结束标签都不能省略。 |
| **允许的父元素** | 任何可接受 *短语内容* 的元素。 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素仅支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 使用须知

- 当 `<kbd>` 元素处于 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素之中时，它代表着被系统回显的输入。
- 当 `<kbd>` 元素中包含 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素时，该输入是基于系统输出的，比如调用某个菜单项。
- 当 `<kbd>` 元素处于另一个 `<kbd>` 元素之中时，它代表了一个实际的按键，或是该输入机制下的某个单位输入。

通过自定义 [[CSS]] 可以改变 `<kbd>` 的默认样式，但用户浏览器设置优先级更高，可以覆盖CSS样式。

## 基本示例

```html
<p>Type the following in the Run dialog: <kbd>cmd</kbd><br>Then click the <kbd>OK</kbd> button.</p>

<p>Save the document by pressing <kbd>Ctrl</kbd> + <kbd>S</kbd></p>
```

## 自定义样式示例

通过在CSS为`<kbd>`元素添加一种新样式“ `key`”，可以在渲染键盘按键时应用：

```css
kbd.key {
  border-radius: 3px;
  padding: 1px 2px 0;
  border: 1px solid black;
}
```

然后在`HTML`可使用：

```html
<p>您还可以通过按 <kbd><kbd class="key">Ctrl</kbd>+<kbd class="key">N</kbd></kbd>.</p>
```

## `<samp>`元素示例

当 `<kbd>` 元素处于 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素之中，代表着被系统回显的输入时。

```html
<p>如果发生语法错误，该工具将输出初始化，您可以输入以下命名供查看：</p>
<blockquote>
  <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
</blockquote>
```

当 `<kbd>` 元素中包含 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素，该输入是基于系统输出的，如下所示是HTML在“文件”菜单中选择“新文档”选项。

```html
<p>要创建一个新文件，请选择菜单选项
<kbd><kbd><samp>文件</samp></kbd>⇒<kbd><samp>新文档</samp></kbd></kbd>.</p>

<p>别忘了点击 <kbd><samp>OK</samp></kbd> 按钮输入新文件的名称后进行确认.</p>
```
