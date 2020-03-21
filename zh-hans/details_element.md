TOPICS: <details>
        <summary>
        <details> open attribute

# HTML 细节补充元素 `<details>` 和 `<summary>`

**HTML 细节补充元素** (**`<details>`**) 创建一个*可展开折叠的挂件*(*widget*)，当挂件切换到*打开*状态时可显示隐藏的补充细节。

**HTML 摘要元素**（**`<summary>`**）指定 *`<details>`* 元素内容的**摘要**，**标题**，**标签**或**图例**。

## `<details>` 技术摘要

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*区块根*，*交互内容*，*可触知内容*。 |
| **允许的内容** | 一个 *`<summary>`* 元素，后跟*流式内容*。 |
| **标签省略** | 不允许，开始标签和结束标签都是必需的。 |
| **允许的父元素** | 任何接受*流式内容*的元素。 |
| **允许的 ARIA 角色** | 没有 |
| **DOM 接口** | **`HTMLDetailsElement`** |

## `<summary>` 技术摘要

|  |  |
| :-- | :-- |
| **允许的内容** | *短语内容* 或 *标题内容的一个标题元素* 。|
| **标签省略** | 不允许，开始标签和结束标签都是必需的。 |
| **允许的父元素** | *`<details>`* 元素。 |
| **允许的ARIA角色** | `button` |
| **DOM接口** | **`HTMLElement`** |

## `<details>` 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| **`open`** | 这个*布尔*属性指示详细信息是否**可见**。默认值为 *`false`*，表示细节不可见。|

## 使用须知

`<details>` 挂件通常使用*小三角形*显示在屏幕上，*旋转*以指示打开/关闭状态，旁边还有一个标签。如果存在 *`<summary>`*，则将其内容用作显示框的标签。如不存在，则浏览器将使用默认字符串（通常为“Details”）作为显示框的标签。

`<summary>` 元素只能用作 `<details>` 元素的第一个子元素。
单击 `<summary>` 元素可切换挂件的状态：*打开*和*关闭*。

## 示例：不带摘要

这个例子显示了一个 `<details>` 元素，没有提供摘要。

```html
<details>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

在这种情况下，浏览器将使用默认的摘要字符串（通常为“详细信息”）。

## 示例：提供摘要

此示例通过使用 `<details>` 内的 *`<summary>`* 元素为上述示例**添加摘要**，如下所示：

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

## 示例：创建一个打开的控件

要在默认打开状态下显示 `<details>` 控件，请添加布尔值 **`open`** 属性：

```html
<details open>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

## CSS 样式

您可以使用 [[CSS]] 来设置这个控件的样式，还可以通过设置/删除 `<details>` 元素中的 *`open`* 属性来以编程方式打开和关闭控件。

!!! warn ""
    注意：不幸的是，目前没有内置的方法可以在打开和关闭之间的过渡设置动画。

完全符合标准的 CSS **`display:list-item`** 将自动应用于 *`<summary>`* 元素，该图标通常是三角形。您可以使用它来进一步自定义外观。
您也可以将样式更改为 **`display:block`** 以删除图标三角形。

以下是一个**自定义可展开折叠控件**的示例。

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

三角形本身可以自定义，尽管并没有得到广泛支持。由于元素是在标准化的实验实现，因此浏览器如何支持此自定义项有所不同，因此我们不得不暂时使用多种方法。

`<summary>` 元素支持 **`list-style`** 的简写属性及其长写属性，比如 *`list-style-type`* 将显示三角形更改为任何形状（通常一起使用*`list-style-image`*）。
例如，我们可以通过设置 *`list-style:none`* 来删除控件图标。

Chrome 尚不支持此功能，因此我们还需要使用其非标准的 **`::-webkit-details-marker`** 伪元素来自定义。

```css
details {
  font: 16px "Open Sans", "Arial", sans-serif;
  width: 620px;
}

details > summary {
  padding: 2px 6px;
  width: 15em;
  background-color: #ddd;
  border: none;
  box-shadow: 3px 3px 4px black;
  list-style: none;
}

details > summary::-webkit-details-marker {
  display: none;
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}
```

该CSS的外观类似于选项卡界面，在该界面中，激活选项卡将展开并打开它以显示其内容。

## `toggle` 事件

除了 HTML 元素支持的常见事件外，`<details>` 元素还支持 **`toggle`** 事件，只要挂件的状态在*打开*和*关闭*之间发生变化就会触发。如果状态在浏览器可以触发事件之前多次更改，事件会合并在一起只发送一个。

您可以侦听 `toggle` 事件以检测挂件何时更改状态：

```javascript
details.addEventListener("toggle", event => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<details>` | 支持 | 支持 | 支持 |
| `<summary>` | 支持 | 支持 | 支持 |
