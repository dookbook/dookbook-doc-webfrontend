TOPICS: <sup>

# HTML 上标元素 `<sup>`

**HTML 上标元素** (**`<sup>`**) 标记了一个**上标**文本区域（出于排版的原因）。与主要的文本相比，应该展示得更高并且更小。

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

这个元素仅仅包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## 用法注解

`<sup>` 元素应该只用于**排版目的**，也就是改变文本的位置会改变含义，而不是用于展示效果或者样式上的目的。

例如，公司名称中等应该使用 [[CSS]] 样式： *`vertical-align`* 属性。比如：*`vertical-align: super`* 或者
更精确的 `vertical-align: 50%`。

适合 `<sup>` 元素的场景包含以下 （但不限于）：

- *数学公式的指数*。也可以考虑使用 *MathML* 公式。示例如下。
- *法语等语言的上标字母*。示例如下。
- *英语序数*。示例如下。

## 示例

### 基础用法

```html
<p>This text is <sup>superscripted</sup></p>
```

### 数学公式的指数

```html
<p>One of the most common equations in all of physics is
<var>E</var>=<var>m</var><var>c</var><sup>2</sup>.<p>
```

### 法语上标字母

```html
<p>Robert a présenté son rapport à M<sup>lle</sup> Bernard.</p>
```

### 序列

```html
<p>The ordinal number "fifth" can be abbreviated in various
languages as follows:</p>
<ul>
  <li>English: 5<sup>th</sup></li>
  <li>French: 5<sup>ème</sup></li>
</ul>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<sup>` | 支持 | 支持 | 支持 |
