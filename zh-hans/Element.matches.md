TOPICS: Element.matches
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.matches()`

如果元素被指定的选择器字符串选择，**`Element.matches()`**  方法返回`true`; 否则返回`false`。

!!! error ""
    有一些浏览器使用前缀, 在非标准名称  `matchesSelector()` 下实现了这个方法!

## 语法

```javascript
let result = element.matches(selectorString);
```

_ `result` 的值为 `true` 或 `false`.
_ `selectorString` 是个CSS选择器字符串.

## 示例

```html
<ul id="birds">
  <li>Orange-winged parrot</li>
  <li class="endangered">Philippine eagle</li>
  <li>Great white pelican</li>
</ul>

<script type="text/javascript">
  var birds = document.getElementsByTagName('li');

  for (var i = 0; i < birds.length; i++) {
    if (birds[i].matches('.endangered')) {
      console.log('The ' + birds[i].textContent + ' is endangered!');
    }
  }
</script>
```

```html
<div id="foo">This is the element!</div>
  <script type="text/javascript">
    var el = document.getElementById("foo");
    if (el.mozMatchesSelector("div")) {
      alert("Match!");
    }
  </script>
```

会显示弹出框,因为"div"选择器可以选择到el元素.

## 异常

|  |  |
| :-- | :-- |
| `SYNTAX_ERR` | 如果给定的CSS选择器无效. 在 Gecko 2.0之前,该方法会返回false,2.0之后,会直接抛出异常.
