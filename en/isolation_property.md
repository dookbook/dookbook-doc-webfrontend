TOPICS: isolation property

# CSS Property: `isolation`

The CSS **`solation`** property defines whether the element **must** create a new **cascading context**.

The main function of this property is that when used with the [**`background-blend-mode`**](/en/webfrontend/background-blend-mode_property)
property, you can only mix the background of a specified element stack: it allows Make a group of
elements independent from the background behind them, and only mix the background of this group of elements.

## Property value

| Property value | Description |
| :--- | :--- |
| **`auto`** | This keyword defines that a new element stack environment will be created only when the property of the element are needed. |
| **`isolate`** | This keyword defines that a new element stack environment will be created. |

## Examples

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
