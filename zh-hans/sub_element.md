TOPICS: <sub>

# HTML 元素 `<sub>`

**HTML 下标元素** (**`<sub>`**) 标记了一个**下标**文本区域（出于排版的原因）。与主要的文本相比，应该展示得更低并且更小。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容* 和 *短语内容* |
| **允许的内容** | *短语内容* |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。 |
| **允许的父元素** | 可以包含 *短语内容* 的任意元素 |
| **允许的 ARIA 角色** | 任意 |
| **DOM 接口** | **`HTMLElement`** |

## 属性

这个元素仅仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)

## 用法注解

`<sub>` 元素应该只用于**排版目的**，也就是改变文本的位置会改变含义，而不是用于展示效果或者样式上的目的。

例如，公司名称中等应该使用 [[CSS]] 样式： *`vertical-align`* 属性。比如：*`vertical-align: sub`* 或者更精确的 `vertical-align: -25%`。

适合 `<sub>` 元素的场景包含以下 （但不限于）：

- *脚注的序号*。示例如下。
- *数学公式变量的下标*，也可以考虑使用 *MathML* 公式。示例如下。
- *化学方程式里的原子数量*。示例如下。

## 示例

### 脚注序号

```html
<p>According to the computations by Nakamura, Johnson, and
Mason<sub>1</sub> this will result in the complete annihilation
of both particles.</p>
```

### 数学公式变量的下标

```html
<p>The horizontal coordinates' positions along the X-axis are
represented as <var>x<sub>1</sub></var> ... <var>x<sub>n</sub></var>.</p>
```

### 化学方程式里的原子数量

```html
<p>The chemical formula of water: H<sub>2</sub>O</p>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<sub>` | 支持 | 支持 | 支持 |
