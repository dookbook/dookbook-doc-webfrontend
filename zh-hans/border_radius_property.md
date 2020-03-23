TOPICS: border-radius property
        border-top-left-radius property
        border-top-right-radius property
        border-bottom-right-radius property
        border-bottom-left-radius property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 外边框圆角属性: `border-radius`

CSS 属性 **`border-radius`** 允许你设置元素的**外边框圆角**。当使用一个半径时确定一个圆形，当使用两个半径时确定一个椭圆。这个(椭)圆与边框的交集形成圆角效果。

此属性是 **`border-top-left-radius`**、**`border-top-right-radius`**、**`border-bottom-right-radius`**，
和 **`border-bottom-left-radius`** 的简写

即使元素没有边框，圆角也可以用到[**`background`**](/zh-hans/webfrontend/background)上面，具体效果受[**`background-clip`**](/zh-hans/webfrontend/background-clip)影响。

| 属性 | 说明 |
| :--- | :--- |
| **`border-top-left-radius`** | 定义了左上角的边框形状 |
| **`border-top-right-radius`** | 定义了右上角的边框形状 |
| **`border-bottom-right-radius`** | 定义右下角边框的形状 |
| **`border-bottom-left-radius`** | 定义左下角边框的形状 |

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| length | 定义弯道的形状 |
| **`%`** | 使用%定义角落的形状。 |

## 示例1

```html
<style>
div {
  padding: 10px 40px;
  background: #ddd;
  width: 300px;
  height: 200px;
  line-height: 200px;
  border-radius: 25px;
}
</style>

<div>This is a box with rounded corners.</div>
```

## 示例2

```html
<style>
section {
  padding: 10px 40px;
  background: #ddd;
  width: 300px;
  height: 200px;
  line-height: 200px;
  border-radius: 50% 20% / 10% 40%;
}
</style>

<section>This is a box with rounded corners.</section>
```

## 示例3

```html
<style>
footer {
  padding: 10px 40px;
  background: #ddd;
  width: 300px;
  height: 200px;
  line-height: 200px;
  border-top-right-radius: 2em 1em;
  border-bottom-left-radius: 2em 1em;
}
</style>

<footer>This is a box with rounded corners. </footer>
```
