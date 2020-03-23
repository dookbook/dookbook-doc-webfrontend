TOPICS: box-shadow property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `box-shadow`

CSS **`box-shadow`** 属性用于在元素的框架上**添加阴影效果**，该属性可设置的值包括**X轴偏移**、**Y轴偏移**、**阴影模糊半径**、**阴影扩散半径**，和**阴影颜色**，并以多个逗号分隔。

`box-shadow` 以由逗号分隔的列表来描述一个或多个阴影效果。该属性可以让几乎所有元素的边框产生阴影。如果元素同时设置了 [*`border-radius`*](/zh-hans/webfrontend/border-radius)，阴影也会有圆角效果。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **h-shadow** | 必需的。水平阴影的位置。允许负值 |
| **v-shadow** | 必需的。垂直阴影的位置。允许负值 |
| **blur** | 可选。模糊距离 |
| **spread** | 可选。阴影的大小 |
| **color** | 可选。阴影的颜色 |
| **inset** | 可选。从外层的阴影（开始时）改变阴影内侧阴影 |

## 示例

```css
div {
  width: 300px;
  height: 100px;
  background-color: yellow;
  box-shadow: 10px 10px 5px #888;
}
```
