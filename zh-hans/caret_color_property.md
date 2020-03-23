TOPICS: caret-color property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `caret-color`

**`caret-color`** 属性用来定义 **插入光标**（caret）的颜色，这里说的插入光标，就是那个在网页的可编辑器区域内，用来指示用户的输入具体会插入到哪里的那个一闪一闪的形似竖杠`|`的东西。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 默认颜色，此时浏览器应该用 `currentcolor` 来作为插入光标的颜色，但浏览器可能还会根据当前的背景色、阴影色等来对该颜色进行适当的调整以确保该插入光标具有良好的可见性。|
| **color** | 所指定的插入光标的颜色值 |

## 示例

```html
<input type="text" value="请输入内容">
```

```css
input {
  caret-color: red;
}
```
