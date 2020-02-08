TOPICS: onerror
        error
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `error` 事件

**`error`** 事件的事件处理程序。针对各种目标的不同类型的错误触发了 `Error` 事件：

当JavaScript运行时错误（包括语法错误）发生时，`window`会触发一个`ErrorEvent`接口的`error`事件，并执行`window.onerror()`。
当一项资源（如[`<img>`](/zh-hans/webfrontend/<img>)或[`<script>`](/zh-hans/webfrontend/<script>)）加载失败，加载资源的元素会触发一个E`vent`接口的`error`事件，并执行该元素上的`onerror()`处理函数。这些error事件不会向上冒泡到`window`，不过（至少在Firefox中）能被单一的`window.addEventListener`捕获。
加载一个全局的`error`事件处理函数可用于自动收集错误报告。

## 语法

由于历史原因，`window.onerror`和`element.onerror`接受不同的参数。

### `window.onerror`

```javascript
window.onerror = function(message, source, lineno, colno, error) { ... }
```

函数参数：

- `message`：错误信息（字符串）。可用于HTML `onerror=""`处理程序中的`event`。
- `source`：发生错误的脚本URL（字符串）
- `lineno`：发生错误的行号（数字）
- `colno`：发生错误的列号（数字）
- `error`：Error对象（对象）

若该函数返回`true`，则阻止执行默认事件处理函数。

### `window.addEventListener('error')`

```javascript
window.addEventListener('error', function(event) { ... })
```

`ErrorEvent` 类型的event包含有关事件和错误的所有信息。

### `element.onerror`

```javascript
element.onerror = function(event) { ... }
```

`element.onerror`使用单一`Event`参数的函数作为其处理函数。

## 注意事项

当加载自不同域的脚本中发生语法错误时，为避免信息泄露，语法错误的细节将不会报告，而代之简单的`"Script error."`。在某些浏览器中，通过在`<script>`使用`crossorigin`
属性并要求服务器发送适当的 CORS HTTP 响应头，该行为可被覆盖。一个变通方案是单独处理`"Script error."`，告知错误详情仅能通过浏览器控制台查看，无法通过JavaScript访问。

```javascript
window.onerror = function (msg, url, lineNo, columnNo, error) {
  var string = msg.toLowerCase();
  var substring = "script error";
  if (string.indexOf(substring) > -1){
    alert('Script Error: See Browser Console for Detail');
  } else {
    var message = [
      'Message: ' + msg,
      'URL: ' + url,
      'Line: ' + lineNo,
      'Column: ' + columnNo,
      'Error object: ' + JSON.stringify(error)
    ].join(' - ');

    alert(message);
  }

  return false;
};
```

当使用行内HTML标签（`<body onerror="alert('an error occurred')">`）时，HTML规范要求传递给`onerror`的参数命名为`event`、`source`、`lineno`、`colno`、`error`。针对不满足此要求的浏览器，传递的参数仍可使用`arguments[0]`到`arguments[2]`来获取。
