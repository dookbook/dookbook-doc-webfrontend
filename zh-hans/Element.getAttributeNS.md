TOPICS: Element.getAttributeNS
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Element.getAttributeNS()`

`Element` 接口的 **`getAttributeNS()`**方法返回具有指定名称空间和名称的属性的字符串值。如果`named`属性不存在，则返回的值将为`null`或`""`(空字符串)；否则，返回值为`0`

## 语法

```javascript
attrVal = element.getAttributeNS(namespace, name)
```

| 参数 | 说明 |
| :-- | :-- |
| `namespace` | 查找指定属性的名称空间。|
| `name` | 要查找的属性的名称。|

## 返回值

指定属性的字符串值。 如果该属性不存在，则结果为`null`。

!!! warn "注意"
    DOM规范的早期版本将此方法描述为针对不存在的属性返回空字符串，但是通常不以这种方式实现，因为`null`更有意义。 DOM4规范现在说此方法应该为不存在的属性返回`null`。

## 示例

以下SVG文档在自定义名称空间中读取`foo`属性的值。

```html
<svg xmlns="http://www.w3.org/2000/svg"
    xmlns:test="http://www.example.com/2014/test" width="40" height="40">

  <circle id="target" cx="12" cy="12" r="10" stroke="#444"
      stroke-width="2" fill="none" test:foo="Hello namespaced attribute!"/>

  <script type="text/javascript">
    var ns = 'http://www.example.com/2014/test';
    var circle = document.getElementById( 'target' );

    console.log( 'attribute test:foo: "' + circle.getAttributeNS( ns, 'foo' ) + '"' );
  </script>
</svg>
```

在HTML5文档中，由于不支持名称空间，因此必须使用`test:foo`访问该属性。

```javascript
<!DOCTYPE html>
<html>
<body>

<svg xmlns="http://www.w3.org/2000/svg"
    xmlns:test="http://www.example.com/2014/test" width="40" height="40">
  <circle id="target" cx="12" cy="12" r="10" stroke="#444" stroke-width="2"
      fill="none" test:foo="Foo value"/>
</svg>

<script type="text/javascript">
  var ns = 'http://www.example.com/2014/test';
  var circle = document.getElementById( 'target' );
  console.log('Attribute value: ' + circle.getAttribute('test:foo'));
</script>

</body>
</html>
```
