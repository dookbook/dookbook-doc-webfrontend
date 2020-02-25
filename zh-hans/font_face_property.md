TOPICS: @font-face property
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# CSS 属性: `@font-face`

**@font-face** CSS at-rule 指定一个用于显示文本的自定义字体；字体能从远程服务器或者用户本地安装的字体加载. 如果提供了`local()`函数，从用户本地查找指定的字体名称，
并且找到了一个匹配项, 本地字体就会被使用. 否则, 字体就会使用`url()`函数下载的资源。

通过允许作者提供他们自己的字体，`@font-face` 让设计内容成为了一种可能，同时并不会被所谓的"网络-安全"字体所限制(字体如此普遍以至于它们能被广泛的使用). 指定查找和使用本地安装的字体名称可以让字体的自定义化程度超过基本字体，同时在不依赖网络情况下实现此功能。

在同时使用`url()`和`local()`功能时，为了用户已经安装的字体副本在需要使用时被使用，如果在用户本地没有找到字体副本就会去使用户下载的副本查找字体。

`@font-face` 规则不仅仅使用在CSS的顶层，还可以用在任何CSS条件组规则中.

## 示例

下面的例子简单定义了一个可下载的字体，并应用到了文档的整个[`<body>`](/en/webfrontend/<body>)标签上。

```html
<html>
<head>
  <title>Web Font Sample</title>
  <style type="text/css" media="screen, print">
    @font-face {
      font-family: "Bitstream Vera Serif Bold";
      src: url("https://mdn.mozillademos.org/files/2468/VeraSeBd.ttf");
    }

    body { font-family: "Bitstream Vera Serif Bold", serif }
  </style>
</head>
<body>
  This is Bitstream Vera Serif Bold.
</body>
</html>
```

在接下来的例子中，用到了用户本地字体"Helvetica Neue Bold"的备份；如果当前用户(浏览器)未安装该字体(两种可能的字体名都已经试过)，就会用下载的字体"MgOpenModernaBold.ttf"来代替：

```css
@font-face {
  font-family: MyHelvetica;
  src: local("Helvetica Neue Bold"),
       local("HelveticaNeue-Bold"),
       url(MgOpenModernaBold.ttf);
  font-weight: bold;
}
```
