TOPICS: height property
AUTHORS: mozhs; mozhs@github.com; github:mozhs
         Sebastian Zartner; SebastianZ@github.com; github:SebastianZ
         Sphinx; SphinxKnight@github.com; github:SphinxKnight
         Teoli; teoli@mozilla.net; mdn:teoli
         Ivan Yan; yanxyz@github.com; github:yanxyz

# CSS 属性: `height`

**`height`** CSS 属性指定了一个**元素的高度**。默认情况下，这个属性决定的是**内容区的高度**，但是，如果将 **`box-sizing`** 设置为
**`border-box`**, 这个属性决定的将是**边框区域的高度**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 默认。浏览器会计算出实际的高度。|
| length | 使用 `px`、`em` 等单位定义高度。|
| **`%`** | 基于包含它的块级对象的百分比高度。|

## 示例

```html
<div id="taller">I'm 50 pixels tall.</div>
<div id="shorter">I'm 25 pixels tall.</div>
<div id="parent">
  <div id="child">
    I'm half the height of my parent.
  </div>
</div>
```

```css
div {
  width: 250px;
  margin-bottom: 5px;
  border: 2px solid blue;
}

#taller {
  height: 50px;
}

#shorter {
  height: 25px;
}

#parent {
  height: 100px;
}

#child {
  height: 50%;
  width: 75%;
}
```
