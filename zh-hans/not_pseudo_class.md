TOPICS: :not()
AUTHORS: 石博文; http_wenwen@live.com; github:Ritr
         Crystal-RainSlide; Crystal-RainSlide@github.com; github:Crystal-RainSlide
         小小鲁班; lantern.done@gmail.com; github:ly525
         Dong WEI; FredWe@mozilla.net; mdn:FredWe

# CSS 伪类: `:not()`

CSS 否定伪类，**`:not(X)`**，是以一个简单的以选择器 *X* 为参数的功能性标记函数。它匹配不符合参数选择器 *X* 描述的元素。*X* 不能包含另外一个否定选择器。

`:not()`伪类的优先级即为它参数选择器的优先级。`:not()`伪类不像其它伪类，它不会增加选择器的优先级。

- 可以利用这个伪类写一个完全没有用处的选择器。例如，`:not(*)` 匹配任何非元素的元素，因此这个规则将永远不会被应用。
- 可以利用这个伪类提高规则的优先级。例如，`#foo:not(#bar)` 和 `#foo` 会匹配相同的元素。但是前者的优先级更高。
- `:not(foo)` 将匹配任何非`foo`元素，包括[`<html>`](/zh-hans/webfrontend/<html>)和[`<body>`](/zh-hans/webfrontend/<body>)。
- 这个选择器只会应用在一个元素上，你无法用它排除所有父元素。比如，`body :not(table) a` 将依旧会应用在`table`内部的`<a>` 上, 因为 [`<tr>`](/zh-hans/webfrontend/<tr>)
将会被 `:not()` 这部分选择器匹配。

`:not()` 伪类可以将一个或多个以逗号分隔的选择器作为其参数。选择器中不得包含另一个否定选择符或伪元素。

## 示例

```html
<p>我是一个段落。</p>
<p class="fancy">我好看极了！</p>
<div>我不是一个段落。</div>
```

```css
.fancy {
  text-shadow: 2px 2px 3px gold;
}

/* 类名不是 `.fancy` 的 <p> 元素 */
p:not(.fancy) {
  color: green;
}

/* 非 <p> 元素 */
body :not(p) {
  text-decoration: underline;
}

/* 非 <div> 或 <span> 的元素 */
body :not(div):not(span) {
  font-weight: bold;
}

/* 类名不是 `.crazy` or `.fancy` 的元素 */
/* 注意，此语法尚未被较好地支持。 */
body :not(.crazy, .fancy) {
  font-family: sans-serif;
}
```
