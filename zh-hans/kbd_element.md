TOPICS: <kbd>

# HTML 键盘输入元素 `<kbd>`

**HTML 键盘输入元素** (**`<kbd>`**) 用于表示**用户输入**（**键盘输入**、**语音输入**、或其他**文本输入设备**）。
它是一个行内元素，以浏览器的默认 `monospace` 字体显示。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*, *短语内容*, *可触知内容* |
| **允许的内容** | *短语内容*. |
| **标签省略** | 不允许，开始和结束标签都不能省略 |
| **允许的父元素** | 任何可接受 *短语内容* 的元素 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

该元素仅支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 使用须知

- 当 `<kbd>` 元素处于 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素之中时，它代表着被系统回显的输入。
- 当 `<kbd>` 元素中包含 *[`<samp>`](/zh-hans/webfrontend/<samp>)* 元素时，该输入是基于系统输出的，比如调用某个菜单项。
- 当 `<kbd>` 元素处于另一个 `<kbd>` 元素之中时，它代表了一个实际的按键，或是该输入机制下的某个单位输入。

!!! warn "`<kbd>` 样式"
    通过定义 [[CSS]] 规则可以改变 `<kbd>` 的默认字体。用户首选项设置比 [[CSS]] 规则具有更高优先级。

## 示例

```html
<p>Type the following in the Run dialog: <kbd>cmd</kbd><br>Then click the <kbd>OK</kbd> button.</p>

<p>Save the document by pressing <kbd>Ctrl</kbd> + <kbd>S</kbd></p>
```
