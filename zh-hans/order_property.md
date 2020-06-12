TOPICS: order property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `order`

CSS **`order`** 属性规定了弹性容器中的可伸缩项目在布局时的顺序。元素按照 **`order`** 属性的值的增序进行布局。拥有相同 **`order`** 属性值的元素按照它们在源代码中出现的顺序进行布局。

!!! warn "注意"
    **`order`** 仅仅对元素的视觉顺序 (**visual order**) 产生作用，并不会影响元素的逻辑或 tab 顺序。**`order`** 不可以用于非视觉媒体，例如 speech。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **integer** | 表示此可伸缩项目所在的次序组。|

## 示例

```html
<div id='main'>
   <article>1…</article>
   <nav>2…</nav>
   <aside>3…</aside>
</div>
<footer>4…</footer>
```

下面的CSS代码会创建一个经典的双 sidebar 围绕一个中央内容块的布局。 Flexible Box 布局模块会自动地创建三个具有相同高度的内容块，也会使用所有可用的水平空间。

```css
#main { display: flex; }
#main > article { flex:1;         order: 2; }
#main > nav     { width: 200px;   order: 1; }
#main > aside   { width: 200px;   order: 3; }
```
