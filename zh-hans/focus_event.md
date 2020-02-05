TOPICS: onfocus
        focus
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `focus` 事件

**`onfocus`** 属性用来获取或设置当前元素的`focus`事件的事件处理函数.

## 语法

```javascript
target.onfocus = functionRef;
```

## 示例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>onfocus示例演示</title>
</head>
<head>
<script>
function myFunction(x){
  x.style.background="yellow";
}
</script>
</head>
<body>

输入你的名字: <input type="text" onfocus="myFunction(this)">
<p>当输入框获取焦点时，修改背景色（background-color属性） 将被触发。</p>

</body>
</html>
```

## 备注

当前元素获得键盘焦点时会触发`focus`事件.

在IE中,几乎所有类型的元素都会触发`focus`事件, 但在Gecko中,只有少数几种类型的元素会触发`focus`事件.
