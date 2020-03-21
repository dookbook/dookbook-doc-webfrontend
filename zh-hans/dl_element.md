TOPICS: <dl>
        <dt>
        <dd>

# HTML 描述列表元素: `<dl>`, `<dt>`, `<dd>`

**HTML `<dl>` 元素** （或 HTML **描述列表元素**）是一个包含**术语定义及描述**的列表，通常用于展示*词汇表*或者*元数据* (键-值对列表)。

在 HTML5 之前， `<dl>` 被大家以**定义列表**所熟知。

## `<dl>` 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，如果元素`<dl>`的子元素包括一对名称/值，则为 *可触知内容*。|
| **允许的内容** | 零个或多个 **`<dt>`** 元素，每个元素后接一个或多个 **`<dd>`** 元素。也可以是 **[`<script>`](/zh-hans/webfrontend/<script>)** 和 **[`<template>`](/zh-hans/webfrontend/<template>)** 混合。<br><br>或：一个或多个 **[`<div>`](/zh-hans/webfrontend/<div>)** 元素和 **[`<script>`](/zh-hans/webfrontend/<script>)** 和 **[`<template>`](/zh-hans/webfrontend/<template>)** 的混合。 |
| **标签省略** | 不允许，开始标签和结束标签都不能省略。|
| **允许的父元素** | 接受 *流式内容* 的任何元素。 |
| **DOM 接口** | **`HTMLDListElement`** |

## `<dl>` 属性

该元素包含[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

## HTML 术语定义元素 `<dt>`

**HTML 术语定义元素**（**`<dt>`**）定义一个描述列表的*项目/名字*。该元素仅能作为 *`<dl>`* 的子元素出现。通常该元素后面会跟着
*`<dd>`* 元素，然而多个连续出现的 `<dt>` 元素都将由出现在它们后面的第一个 `<dd>` 元素定义。

### `<dt>` 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | 没有 |
| **允许的内容** | *流式内容*，但是不能包含 *[`<header>`](/zh-hans/webfrontend/<header>)* 元素、*[`<footer>`](/zh-hans/webfrontend/<footer>)* 元素或者其他区块内容或者标题内容。|
| **标签省略** | 必须有开标签。如果该元素后面紧跟着另一个 `<dd>` 元素，或者父元素中没有更多内容，则可以省略闭标签。|
| **允许的父元素** | 该元素需要出现在 `<dt>` 元素或者 `<dd>` 元素之前，并且在 `<dl>` 元素中。|
| **DOM 接口** | **`HTMLDListElement`** |

## HTML 术语描述元素 `<dd>`

**HTML 术语描述元素**（**`<dd>`**）用来对一个描述列表(`<dl>`)中的*项目/名字*进行描述。这个元素只能作为描述列表元素的子元素出现，并且必须和 `<dt>` 元素一起使用。

### `<dd>` 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | 无 |
| **允许的内容** | *流式内容* |
| **标签省略** | 必须有开标签。如果该元素后面紧跟着另一个 `<dd>` 元素，或者父元素中没有更多内容，则可以省略闭标签。|
| **允许的父元素** | **`<dl>`** 元素，或（在 *[[WHATWG]]* HTML 规范里）在 `<dl>` 里的 **[`<div>`](/zh-hans/webfrontend/<div>)** 元素。|
| **允许的兄弟元素** | **`<dt>`** 元素，或另一个 **`<dd>`** 元素。|
| **DOM 接口** | **`HTMLElement`** |

### `<dd>` 属性

| 属性 | 描述 |
| :-- | :-- |
| `nowrap` (*非标准*) | 如果这个属性的值为 `yes`，那么定义的描述文字将不会包裹。默认值为 `no`。 |

## 示例

### 单一术语及描述

```html
<dl>
  <dt>Firefox</dt>
  <dd>A free, open source, cross-platform, graphical web browser
      developed by the Mozilla Corporation and hundreds of volunteers.
  </dd>

  <!-- 其他术语及描述 -->
</dl>
```

### 多个术语，单一描述

```html
<dl>
  <dt>Firefox</dt>
  <dt>Mozilla Firefox</dt>
  <dt>Fx</dt>
  <dd>
    A free, open source, cross-platform,
    graphical web browser developed by the
    Mozilla Corporation and hundreds of
    volunteers.
  </dd>

  <!-- 其他术语及描述 -->
</dl>
```

### 单一术语，多个描述

```html
<dl>
  <dt>Firefox</dt>
  <dd>
    A free, open source, cross-platform,
    graphical web browser developed by the
    Mozilla Corporation and hundreds of
    volunteers.
  </dd>
  <dd>
    The Red Panda also known as the Lesser
    Panda, Wah, Bear Cat or Firefox, is a
    mostly herbivorous mammal, slightly larger
    than a domestic cat (60 cm long).
  </dd>

  <!-- 其他术语及描述 -->
</dl>
```

### 多术语，多描述

可以将上述示例综合使用。

### 元数据

定义列表可以用来显示一组键值对的元数据。

```html
<dl>
  <dt>姓名</dt>
  <dd>ABC</dd>
  <dt>出生</dt>
  <dd>1952</dd>
  <dt>出生地</dt>
  <dd>中国</dd>
  <dt>颜色</dt>
  <dd>绿色</dd>
</dl>
```

提示：可以用CSS定义键值对的分隔符，就像：

```css
dt::after {
  content: ": ";
}
```

### 将键值对打包成组

```html
<dl>
  <div>
    <dt>姓名</dt>
    <dd>ABC</dd>
  </div>
  <div>
    <dt>出生</dt>
    <dd>1952</dd>
  </div>
  <div>
    <dt>出生地</dt>
    <dd>中国</dd>
  </div>
  <div>
    <dt>颜色</dt>
    <dd>绿色</dd>
  </div>
</dl>
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<dl>` | 支持 | 支持 | 支持 |
| `<dt>` | 支持 | 支持 | 支持 |
| `<dd>` | 支持 | 支持 | 支持 |
