TOPICS: resize property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `resize`

CSS **`resize`** 属性允许你**控制一个元素的可调整大小性**。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 用户无法调整元素的尺寸。|
| **`both`** | 用户可调整元素的**高度**和**宽度**。|
| **`horizontal`** | 用户可调整元素的**宽度**。|
| **`vertical`** | 用户可调整元素的**高度**。|

!!! warn "注意"
    如果一个 **block** 元素的 [**`overflow`**](/zh-hans/webfrontend/overflow_property) 属性被设置成了 *`visible`*，那么
    **`resize`** 属性对该元素无效。

## 示例

[*`<textarea>`*](/zh-hans/webfrontend/<textarea>) 元素在Gecko 2.0 (Firefox 4)中默认是可以进行缩放的. 你可以通过下面的CSS代码来重写这种行为：

```css
textarea.example {
  resize: none; /* 禁用调整大小 */
}
```

```html
<textarea class="example">Type some text here.</textarea>
```
