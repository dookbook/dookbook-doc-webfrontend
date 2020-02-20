TOPICS: :only-of-type
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 伪类: `:only-of-type`

CSS 伪类 **`:only-of-type`** 代表了任意一个元素，这个元素没有其他相同类型的兄弟元素。

## Example

```html
<main>
  <div>I am `div` #1.</div>
  <p>I am the only `p` among my siblings.</p>
  <div>I am `div` #2.</div>
  <div>I am `div` #3.
    <i>I am the only `i` child.</i>
    <em>I am `em` #1.</em>
    <em>I am `em` #2.</em>
  </div>
</main>
```

```css
main :only-of-type {
  color: red;
}
```
