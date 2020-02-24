TOPICS: text-justify property

# CSS 属性: `text-justify`

CSS属性 **`text-justify`** 定义的是当文本的 **`text-align`** 属性被设置为 **`justify`** 时的齐行方法。

## 属性值

| 属性值 | 描述 |
| :--- | :--- |
| **`none`** | 表示关闭掉齐行的设置。表现的效果和没有设置 `text-align` 一样，当你因为某种原因需要在已经设置了 `text-align` 的元素上禁用齐行效果的时候，这个属性值很有用。|
| **`auto`** | 默认值，浏览器根据显示的效果和质量来确定符合当前状态的最佳对齐方式，当然这种对齐方式将是最适合某种语言文字的排版（例如：英语，中文，日语，韩语等）。如果没有对 `text-justify` 进行设置的话，则是默认使用这样子的对齐规则。|
| **`inter-word`** | 通过在文本中的单词之间添加空间来实现行对齐（这将会改变 `word-spacing` 的值），比如英语或韩语就是最适合使用这个属性来用空格分隔单词的语言。|
| **`inter-character`** | 通过在文本中的字符之间添加空间来实现行对齐（这将会改变 `letter-spacing` 的值），比如日语就是最适合使用这个属性的语言。|

## 示例

```css
p {
  font-size: 1.5em;
  border: 1px solid black;
  padding: 10px;
  width: 95%;
  margin: 10px auto;
  text-align: justify;
}

.none {
  text-justify: none;
}

.auto {
  text-justify: auto;
}

.word {
  text-justify: inter-word;
}

.char {
  text-justify: inter-character;
}
```

```html
<p class="none">text-justify: none —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="auto">text-justify: auto —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="dist">text-justify: distribute —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="word">text-justify: inter-word —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
<p class="char">text-justify: inter-character —
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc ornare maximus vehicula. Duis nisi velit, dictum id mauris vitae, lobortis pretium quam. Quisque sed nisi pulvinar, consequat justo id, feugiat leo. Cras eu elementum dui.</p>
```
