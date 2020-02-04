TOPICS: <var>

# HTML 变量元素 `<var>`

**HTML 变量元素** (**`<var>`**) 表示**数学公式或计算机编程里的变量名称**。经常被渲染成*斜体*(*`italic`*)字。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容* *短语内容* *可触知内容* |
| **允许内容** | *短语内容* |
| **标签省略** | 不允许，开始标签和结束标签都是必需的 |
| **允许的父级元素** | 任何接受 *短语内容* 的元素 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

本元素仅支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

## 相关元素

- **[`<code>`](/zh-hans/webfrontend/<code>)**: HTML 代码元素
- **[`<kbd>`](/en/webfrontend/<kbd>)**: HTML 键盘输入元素
- **[`<samp>`](/en/webfrontend/<samp>)**: HTML 样本输出元素

## 样式

## 默认样式

```css
var {
  font-style: italic;
}
```

## 示例

### 数学公式变量

```html
<p> A simple equation: <var>x</var> = <var>y</var> + 2 </p>
```

### 标记物理变量

```html
<p>The variables <var>minSpeed</var> and <var>maxSpeed</var> control
   the minimum and maximum speed of the apparatus in revolutions
   per minute (RPM).</p>
```
