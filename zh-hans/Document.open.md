TOPICS: Document.open
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# `Document.open()`

**`Document.open()`** 方法打开一个要写入的文档。

这将会有一些连带的影响。例如：

- 此时已注册到文档、文档中的节点或文档的window的所有事件监听器会被清除。
- 文档中的所有节点会被清除。

## 语法

```javascript
document.open();
```

**参数**: 没有参数

**返回值**: 一个 `Document` 对象实例。

## 示例

以下简单的代码，会打开一个文档，并将原有内容替换为一些不同的HTML片段，然后关闭文档。

```javascript
document.open();
document.write("<p>Hello world!</p>");
document.write("<p>I am a fish</p>");
document.write("<p>The number is 42</p>");
document.close();
```

## 注意

当 `document.write()` 在页面加载后调用，会发生自动的 `document.open()`调用。

很多年以来，Firefox和IE浏览器会在清除所有节点的同时，将所有JavaScript变量等一并清除，但现在已经不采用这一做法。
不要和 `window.open()` 方法混淆。`document.open` 可用于重写当前的文档内容或者追加内容, 而 `window.open` 是提供了打开一个新的窗口的方法，
当前的网页文档内容会被保留。由于 window 是一个全局对象，直接调用 `open(...)`  和 `window.open(...)` 的效果是一样的。你可以使用 `document.close()`关闭打开的文档。

如果不想在当前文本追加内容， 使用 `open("text/html", "replace")` 替换 `open()` .

### 针对Gecko的注意事项

从Gecko 1.9开始，这个方法与其他属性一样受到同源策略的控制，若调用会使文档的源产生变化则不可用。

从Gecko 1.9.2开始，`document.open()` 使用文档的使用的URI的`principal`大，而不是从`stack`中取来`principal`。因此，你无需再在不可信的文档里调用
`document.write()` ，包括使用`wrappedJSObject`

## 三个参数的`document.open()`

有一个更少人知道且更少被使用的 `document.open()` 的版本，这是`Window.open()` 的一个别名（前往该页面查看更多）。

这种调用，例如在新窗口打开github.com，把`opener`设为`null`：

```javascript
document.open('https://www.github.com','', 'noopener=true')
```

## 两个参数的`document.open()`

浏览器过往支持一个两个参数版本的document.open()，方法参数签名如下：

```javascript
document.open(type, replace)
```

`type`指定了所需写入的数据的MIME类型，`replace`（如有设置，值为一个字符串`“replace”`）指定了新文档的历史写入会代替现有的例如写入。

这种形式现在已经弃用；它不会抛出错误，但会直接调用`document.open()`（相当于无参数形式的调用）。这种历史写入替换行为现在一定会发生。
