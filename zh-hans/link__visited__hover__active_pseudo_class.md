TOPICS: :link
        :visited
        :hover
        :active

# CSS 伪类: `:link`、`:visited`、`:hover`、`:active`

**`:link`** CSS 伪类表示尚未访问的元素。它匹配具有`href`属性的所有未访问的[`<a>`](/zh-hans/webfrontend/<a>)，[`<area>`](/zh-hans/webfrontend/<area>)或[`<link>`](/zh-hans/webfrontend/<link>)元素。

**`:visited`** CSS 伪类表示用户已访问过的链接。出于隐私原因，可以使用此选择器修改的样式非常有限。

**`:hover`** CSS 伪类在鼠标移到链接上时添加的特殊样式。

**`:active`** CSS 伪类匹配被用户激活的元素。它让页面能在浏览器监测到激活时给出反馈。当用鼠标交互时，它代表的是用户按下按键和松开按键之间的时间。

!!! warn "注意"
    请按照LVHA-order所定义的顺序来定义: `:link` — `:visited` — `:hover` — `:active`。

## 示例

```html
<a href="#">dookbook</a>
```

```css
a:link { color: #FF0000; } /* 未访问的链接 */
a:visited { color: #00FF00; } /* 已访问的链接 */
a:hover { color: #FF00FF; } /* 鼠标划过链接 */
a:active { color: #0000FF; } /* 已选中的链接 */
```
