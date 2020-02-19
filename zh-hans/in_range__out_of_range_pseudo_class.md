TOPICS: :in-range
        :out-of-range

# CSS 伪类: `:in-range`、`:out-of-range`

**`:in-range`** CSS 伪类代表一个 [*`<input>`*](/zh-hans/webfrontend/<input>) 元素其值处于属性 **`min`** 和 **`max`**限定的**范围之内**的样式.

**`:out-of-range`** CSS 伪类表示一个 [*`<input>`*](/zh-hans/webfrontend/<input>) 元素其值处于属性 **`min`** 和 **`max`**限定的**范围之外**的样式。

## 示例

```html
<form action="" id="form1">
  <ul>Values between 1 and 10 are valid.
    <li>
      <input id="value1" name="value1" type="number" placeholder="1 to 10" min="1" max="10" value="12">
      <label for="value1">Your value is </label>
    </li>
  </ul>
</form>
```

```css
li {
  list-style: none;
  margin-bottom: 1em;
}

input {
  border: 1px solid black;
}

input:in-range {
  background-color: rgba(0, 255, 0, 0.25);
}

input:out-of-range {
  background-color: rgba(255, 0, 0, 0.25);
  border: 2px solid red;
}

input:in-range + label::after {
  content: 'okay.';
}

input:out-of-range + label::after {
  content: 'out of range!';
}
```
