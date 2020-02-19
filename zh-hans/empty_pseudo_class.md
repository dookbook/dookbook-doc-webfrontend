TOPICS: :empty
AUTHORS: 夏凌晨; xgqfrms@mozilla.net; mdn:xgqfrms
         庄引; zhuangyin8@gmail.com; github:zhuangyin8
         xgqfrms; xgqfrms@github.com; github:xgqfrms
         Dong WEI; FredWe@mozilla.net; mdn:FredWe

# CSS 伪类: `:empty`

**`:empty`** CSS 伪类代表没有子元素的元素。子元素只可以是元素节点或文本（包括空格）。注释或处理指令都不会产生影响。

## 示例

```html
<div class="box"><!-- I will be lime --></div>
<div class="box">I will be pink</div>
<div class="box">
    <!-- I will be red because of the whitespace around this comment -->
</div>
```

```css
.box {
    background: pink;
    height: 80px;
    width: 80px;
}

.box:empty {
    background: lime;
}
```
