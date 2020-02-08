TOPICS: <details>
        <summary>

# `<details>`

**HTML Details元素(`<details>`)** 创建一个公开窗口小部件，其中仅当该窗口小部件切换到“打开”状态时，信息才可见。可以使用`<summary>`元素来提供摘要或标签。

公开窗口小部件通常使用小三角形显示在屏幕上，该小三角形旋转（或扭曲）以指示打开/关闭状态，三角形旁边有一个标签。如果`<details>`元素的第一个子元素是`<summary>`，则将`<summary>`元素的内容用作公开窗口小部件的标签。

!!! warn "Don't try this at home"
    注意：旋转或扭曲的三角形通常用来表示打开或关闭小部件，这就是为什么有时将它们称为“扭曲”的原因。

`<details>`小部件可以处于两种状态之一。 默认的关闭状态仅在`<summary>`内显示三角形和标签（如果没有`<summary>`，则显示用户代理定义的默认字符串）。 看起来可能如下所示：

在这里，我们看到带有标签“系统要求”的标准公开小部件，其默认关闭状态。当用户单击窗口小部件或对其进行聚焦，然后按空格键时，它将“扭曲”打开，显示其内容：

从那里，您可以使用CSS来设置披露窗口小部件的样式，还可以通过设置/删除窗口小部件的open属性来以编程方式打开和关闭窗口小部件。

默认情况下，当关闭时，小部件仅高到足以显示显示三角形和摘要。 打开后，它将展开以显示其中包含的详细信息。

!!! warn "Don't try this at home"
    注意：不幸的是，目前没有内置的方法可以为打开和关闭之间的过渡设置动画。

完全符合标准的实现将CSS`display:list-item`自动应用于`<summary>`元素。您可以使用它来进一步自定义外观。 有关更多详细信息，请参见自定义披露小部件。

|  |  |
| :-- | :-- |
| **内容分类** | *流式内容*，*切片根*，*交互内容*，*可触知的内容*。 |
| **允许的内容** | 一个`<summary>`元素，后跟*流式内容*。 |
| **标签遗漏** | 无，开始标签和结束标签都是必需的. |
| **允许的父元素** | 任何接受*流程内容*的元素. |
| **允许的ARIA角色** | 没有 |
| **DOM 接口** | **`HTMLDetailsElement`** |

## 属性

此元素包括[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `open` | 这个布尔属性指示详细信息（即`<details>`元素的内容）当前是否可见。 默认值为`false`，表示细节不可见. |

## 大事记

除了HTML元素支持的常见事件外，`<details>`元素还支持`toggle`事件，只要事件的状态在打开和关闭之间发生变化，该事件就会分派到`<details>`元素。 它是在状态更改后发送的，尽管如果状态在浏览器可以分派事件之前多次更改，事件会合并在一起，因此只发送一个。

您可以侦听`toggle`事件以检测小部件何时更改状态：

```javascript
details.addEventListener("toggle", event => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

## `<summary>`

**HTML Disclosure Summary元素（`<summary>`）** 元素指定`<details>`元素的显示框的摘要，标题或图例。 单击`<summary>`元素可切换打开和关闭父`<details>`元素的状态。

|  |  |
| :-- | :-- |
| **允许的内容** | *短语内容* 或 *标题内容*之一 。|
| **标签遗漏** | 无，开始标签和结束标签都是必需的。 |
| **允许的父元素** | `<details>`元素. |
| **允许的 ARIA 角色** | `button` |
| **DOM 接口** | `HTMLElement` |

## 使用说明

`<summary>`元素的内容可以是段落中可以使用的任何标题内容，纯文本或HTML。

`<summary>`元素只能用作`<details>`元素的第一个子元素。 当用户单击摘要时，父`<details>`元素被切换为打开或关闭，然后一个`toggle`事件发送到
`<details>`元素，该事件可用于通知您何时 状态发生变化。

### 默认标签文字

如果`<details>`元素的第一个子元素不是`<summary>`元素，则用户代理将使用默认字符串（通常为“Details”）作为显示框的标签。

### 默认样式

根据HTML规范，`<summary>`元素的默认样式包括`display:ist-item`。 这使得可以更改或删除默认情况下标签旁边显示为公开窗口小部件的图标，该图标通常是三角形。

您也可以将样式更改为`display:block`以删除显示三角形。

有关详细信息，请参见“浏览器兼容性”部分，因为并非所有浏览器都支持此元素的全部功能。

## 示例

### 一个简单的披露例子

这个例子显示了一个`<details>`元素，没有提供摘要。

```html
<details>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

在这种情况下，浏览器将使用默认的摘要字符串（通常为“详细信息”）。这是您的浏览器使用的功能：

### 提供摘要

此示例通过使用`<details>`内的`<summary>`元素为上述示例添加摘要，如下所示：

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### 创建一个开放的披露框

要在打开状态下打开`<details>`框，请添加布尔值`open`属性：

```html
<details open>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### 自定义外观

现在，我们应用一些CSS来定制显示框的外观。

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
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}
```

该CSS的外观类似于选项卡式界面，单击该选项卡可将其打开以显示其内容。

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```

### 自定义披露小部件

披露三角形本身可以自定义，尽管并没有得到广泛支持。 由于该元素是标准化的，因此由于实验性实施，浏览器如何支持此自定义项有所不同，因此我们不得不暂时使用多种方法。

`<summary>`元素支持`list-style`的简写属性及其长写属性，例如`list-style-type`，以将显示三角形更改为您选择的任何形状（通常使用`list-style-image`）。
例如，我们可以通过设置`list-style:none`来删除披露控件图标。

Chrome尚不支持此功能，因此我们还需要使用其非标准的`::-webkit-details-marker`伪元素来自定义该浏览器的外观。

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

```html
<details>
  <summary>System Requirements</summary>
  <p>Requires a computer running an operating system. The computer
  must have some memory and ideally some kind of long-term storage.
  An input device as well as some form of output device is
  recommended.</p>
</details>
```
