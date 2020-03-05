TOPICS: clip-path property
AUTHORS: 笨笨哥; LOLZSXZXM@163.COM; github:ZSX-JOJO
         Crystal-RainSlide; Crystal-RainSlide@github.com; github:Crystal-RainSlide
         苍崎橙子; AozakiOrenji@mozilla.net; mdn:AozakiOrenji

# CSS 剪切属性: `clip-path`

**`clip-path`** CSS 属性可以创建一个只有元素的部分区域可以显示的剪切区域。区域内的部分显示，区域外的隐藏。剪切区域是被引用内嵌的URL定义的路径或者外部SVG的路径，
或者作为一个形状例如`circle()`。`clip-path`属性代替了现在已经弃用的剪切 `clip` 属性。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **margin-box** | 使用 `margin` box 作为引用框。|
| **border-box** | 使用 `border` box 作为引用框。|
| **padding-box** | 使用 `padding` box 作为引用框。|
| **content-box** |使用 `content` box 作为引用框。|
| **fill-box** | 利用对象边界框作为引用框。|
| **stroke-box** | 使用笔触边界框（stroke bounding box）作为引用框 |
| **view-box** | 使用最近的 SVG 视口（viewport）作为引用框。如果 `viewBox` 属性被指定来为元素创建 SVG 视口，引用框将会被定位在坐标系的原点，引用框位于由 `viewBox` 属性建立的坐标系的原点，引用框的尺寸用来设置 `viewBox` 属性的宽高值。|
| **`none`** | 不创建的剪切路径。|

## 示例

```html
<img id="clipped" src="https://mdn.mozillademos.org/files/12668/MDN.svg"
    alt="MDN logo">
```

```css
#clipped {
  margin-bottom: 20px;
  clip-path: circle(100px at 110px 100px);
}
```
