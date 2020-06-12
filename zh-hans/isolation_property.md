TOPICS: isolation property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `isolation`

CSS **`solation`** 属性定义该元素**是否必须**创建一个新的**层叠上下文**。

该属性的主要作用是当和 [**`background-blend-mode`**](/zh-hans/webfrontend/background-blend-mode_property) 属性一起使用时，可以只混合一个指定元素栈的背景：它允许使一组元素从它们后面的背景中独立出来，只混合这组元素的背景。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 该关键字定义只有在该元素的属性需要的时候才会创建一个新的元素栈环境。|
| **`isolate`** |该关键字定义一个新的元素栈环境会被创建。|

## 示例

```html
<div id="b" class="a">
  <div id="d">
    <div class="a c">auto</div>
  </div>
  <div id="e">
    <div class="a c">isolate</div>
  </div>
</div>
```

```css
.a {
  background-color: rgb(0,255,0);
}
#b {
  width: 200px;
  height: 210px;
}
.c {
  width: 100px;
  height: 100px;
  border: 1px solid black;
  padding: 2px;
  mix-blend-mode: difference;
}
#d {
  isolation: auto;
}
#e {
  isolation: isolate;
}
```
