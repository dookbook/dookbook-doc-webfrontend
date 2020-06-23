TOPICS: font-kerning property

# CSS 属性: `font-kerning`

CSS 属性 **`font-kerning`** 设置是否使用字体中**储存的字距信息**。

Kerning（字距）定义了字母的分布情况。对于良好地规定了字距的字体，字距特性使得字母分布更为统一，阅读体验更佳。如下图所示，左侧的示例没有应用字距，而右侧使用了：
**`font-kerning`** 属性通过以下的关键字进行指定。

## 属性值

| 属性值 | 说明 |
| :--- | :--- |
| **`auto`** | 浏览器来决定是否使用字体字距。比如，一些浏览器会在小字体的情况下禁用字距，因为这会使得文本可读性下降。|
| **`normal`** |必须应用字体中的字距信息。|
| **`none`** |禁用字体中的字距信息。|

## 示例

```html
<div id="kern"></div>
<div id="nokern"></div>
<textarea id="input">AV T. ij</textarea>
```

```css
div {
  font-size: 2rem;
  font-family: serif;
}

#nokern {
  font-kerning: none;
}

#kern {
  font-kerning: normal;
}
```

```javascript
var input  = document.getElementById('input'),
    kern   = document.getElementById('kern'),
    nokern = document.getElementById('nokern');

input.addEventListener('keyup', function() {
  kern.textContent = input.value; /* 更新内容 */
  nokern.textContent = input.value;
});

kern.textContent = input.value; /* 初始化内容 */
nokern.textContent = input.value;
```
