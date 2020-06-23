TOPICS: all property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `all`

CSS **`all`** 简写属性除 `unicode-bidi` 与 `direction` 之外的所有属性**重设至其初始值**，或**继承值**。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`initial`** | 修改所有元素属性或父元素的值为其初始化值。 |
| **`inherit`** | 修改所有元素属性或父元素的值为其父元素的值。 |
| **`unset`** | 修改所有元素属性或父元素的值为其父元素的值(如果有继承)或其初始值。 |

## 示例

```css
html {
  font-size: small;
  color: blue;
}

#ex1 {
  background-color: yellow;
  color: red;
}

#ex2 {
  background-color: yellow;
  color: red;
  all: inherit;
}

#ex3 {
  background-color: yellow;
  color: red;
  all: initial;
}

#ex4 {
  background-color: yellow;
  color: red;
  all: unset;
}
```

```html
<p>没有 all 属性:</p>
<div id="ex1">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: inherit:</p>
<div id="ex2">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: initial:</p>
<div id="ex3">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>

<p>all: unset:</p>
<div id="ex4">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>
```
