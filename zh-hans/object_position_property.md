TOPICS: object-position property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `object-position`

CSS 属性 **`object-position`** 规定了**可替换元素**的内容，在这里我们称其为**对象**（即 **`object-position`** 中的 **object**），在其**内容框中的位置**。可替换元素的内容框中未被对象所覆盖的部分，则会显示该元素的背景（**background**）。

你还可以使用 [**`object-fit`**](/zh-hans/webfrontend/object-fit_property) 属性来改变**可替换元素的对象**的内在（原文：intrinsic）**大小**（即它看上去的大小）的**调整方式**，借助**拉伸**与**缩放**等使对象更好地适应**元素的内容框**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **position** | 使用 **1 - 4个值**来定义该元素在它所处的二维平面中的定位。可以使用相对或绝对偏移。|

!!! warn "注意"
    这些定位方式允许被替换元素的对象被定位到内容框外部。

## 示例

这里我们看到HTML包含两个[`<img>`](/zh-hans/webfrontend/<img>)元素，每个元素显示MDN徽标。

```html
<img id="object-position-1" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>
<img id="object-position-2" src="https://mdn.mozillademos.org/files/12668/MDN.svg" alt="MDN Logo"/>
```

```css
img {
  width: 300px;
  height: 250px;
  border: 1px solid black;
  background-color: silver;
  margin-right: 1em;
  : none;
}

#object-position-1 {
  object-position: 10px;
}

#object-position-2 {
  object-position: 100% 10%;
}
```

第一个图像的位置是其左边缘从元素框的左边缘嵌入10个像素。第二幅图像的位置是其右边缘与元素框的右边缘齐平，位于元素框高度向下10%的位置。
