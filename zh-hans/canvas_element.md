TOPICS: <canvas>

# `<canvas>`

`<canvas>`元素可被用来通过脚本（通常是JavaScript）绘制图形。比如,它可以被用来绘制图形,制作图片集合,甚至用来实现动画效果。你可以(也应该)在元素标签内写入可提供替代的代码内容，这些内容将会在旧的、不支持`<canvas>`元素的浏览器或是禁用了JavaScript的浏览器内渲染并展现。

更多关于`<canvas>`元素内容，参见[canvas元素讨论页面](https://wiki.developer.mozilla.org/en-US/docs/Web/API/Canvas_API).

|  |  |
| :-- | :-- |
| **内容分类**  | *流式内容*, *短语内容*, *嵌入内容*, *可触知内容*.|
| **允许的内容** | 透明的，但没有互动的内容，除了后代[`<a>`](/zh-hans/webfrontend/<a>)元素，[`<button>`](/zh-han/webfrontend/<button>)元素，[`<input>`](/zh-han/webfrontend/<input>)元素，其`type`属性`checkbox`，`radio`或`button`。|
| **标签省略** | 没有，开始标签和结束标签都是必需的。|
| **允许的父元素** | 接受*短语内容*的任何元素。 |
| **允许的ARIA角色** | 任何 |
| **DOM 接口** | **`HTMLCanvasElement`** |

## 属性

本元素支持 [全局属性](/zh-hans/webfrontend/HTML_Global_Attributes).

| 属性 | 描述 |
| :-- | :-- |
| `height` | 该元素占用空间的高度，以 CSS 像素（px）表示，默认为 150。 |
| `moz-opaque` | 通过设置这个属性，来控制`<canvas>`元素是否半透明。如果你不想`<canvas>`元素被设置为半透明，使用这个元素将可以优化浏览器绘图性能。 |
| `width` | 该元素占用空间的宽度，以 CSS 像素（px）表示，默认为 300。 |

## 注意事项

### 设置画布(canvas)的大小

直接在`<html>`标签中设置`width`和`height`属性或者使用JavaScript来指定画布尺寸，这将改变一个画布的水平像素和垂直像素数，就像定义了一张图片的大小一样。

可以通过CSS来控制`<canvas>`的大小。在渲染的过程中`<canvas>`元素中的内容会根据情况缩放来适应需要的大小。如果您发现`<canvas>`元素中展示的内容变形，您可以通过`<canvas>`自带的`height`和`width`属性进行相关设置，而不要使用CSS。

### 最大的画布尺寸

画布的最大的尺寸取决于浏览器，下表的结论来自别处 (e.g. [Stack Overflow](https://stackoverflow.com/questions/6081483/maximum-size-of-a-canvas-element)):

| 浏览器 | 最大高度 | 最大宽度 | 最大面积 |
| :-- | :-- | :-- | :-- |
| Chrome | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (i.e., 16,384 x 16,384) |
| Firefox | 32,767 pixels | 32,767 pixels | 472,907,776 pixels (i.e., 22,528 x 20,992) |
| Safari  | 32,767 pixels | 32,767 pixels | 268,435,456 pixels (i.e., 16,384 x 16,384) |
| IE | 8,192 pixels | 8,192 pixels | ? |

!!! warn "注意"
    超过最大尺寸或面积，会使画布无法使用绘图命令。

## 示例

```html
<canvas id="canvas" width="300" height="300">
  Sorry, your browser doesn't support the &lt;canvas&gt;

element.
</canvas>
```

如果你没有设置`<canvas>`元素的透明度，可以考虑使用`moz-opaque`属性。下面给出的示例代码可用于页面渲染优化。但需要您注意的是，这个属性目前还没有被推广开来，只能在基于Mozilla内核的浏览器内生效。

```html
<canvas id="mycanvas" moz-opaque></canvas>
```
