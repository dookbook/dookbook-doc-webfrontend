TOPICS: <video>

# `<video>`

**HTML `<video>` 元素** 用于在HTML或者XHTML文档中嵌入媒体播放器，用于支持文档内的视频播放。你也可以将 `<video>`  标签用于音频内容，
但是 [`<audio>`](/zh-hans/webfrontend/<audio>) 元素可能在用户体验上更合适。

`<video>` 元素的用法和 [`<img>`](/zh-hans/webfrontend/<img>) 元素的使用类似，在 `src` 属性里加入一个我们需要展示的视频地址，同时也可以用其他属性来定义视频的宽度高度、是否自动或者循环播放、是否展示浏览器默认的视频控件等信息。

在 `<video>` 和 `</video>` 标签之间放置文本内容，这样不支持 `<video>`元素的浏览器就可以显示出该标签的信息。

每个浏览器支持的视频格式都有所不同，所以你可以在 [`<source>`](/zh-hans/webfrontend/<source>) 元素里提供多个视频源，然后浏览器将会使用它所支持的第一个格式。

其他的使用注意事项：

- 如果你没有指定 `controls` 属性，那么视频不会展示浏览器自带的控件，你也可以用 JavaScript 和 `HTMLMediaElement` API 来创建你自己的控件。
详情请见Creating a cross-browser video player。
- `HTMLMediaElement` 会激活许多不同的事件，以便于让你可以控制视频（和音频）内容。
- 你可以用CSS 属性 object-position 来调整视频在元素内部的位置，它可以控制视频尺寸适应于元素外框的方式。
- 如果想在视频里展示字幕或者标题，你可以在 [`<track>`](/zh-hans/webfrontend/<track>) 元素和 WebVTT 格式的基础上使用 JavaScript 来实现。详情请见
Adding captions and subtitles to HTML5 video。

## 技术摘要

|  |  |
| :-- | :-- |
| **内容类别** | *流式内容*, *短语内容*, *嵌入内容*。<br> 如果具有`controls'属性：*交互式内容*和*可触摸的内容*。|
| **允许内容** | *流式内容*, 包含任一 src 属性或是一个或多个 [`<source>`](/zh-hans/webfrontend/<source>) 元素，其后紧跟*流式内容*或*段落内容* ， 不包括 `<video>` 或者 [`<audio>`](/zh-hans/webfrontend/<audio>) 元素。|
| **标记省略** | 无，开始标签和结束标签都必须有。 |
| **允许的父元素** | 任何接受*流式内容*，或者*段落内容*的元素。|
| **允许的 ARIA 角色**| `application` |
| **DOM 接口**  | **`HTMLVideoElement`** |
| **规范文档** | HTML5, 4.8.6节 |

## 属性

就像其他的HTML元素一样，这个元素也同样支持[全局属性](/zh-hans/webfrontend/HTML_Global_Attributes)。

| 属性 | 描述 |
| :-- | :-- |
| `autoplay` | 布尔属性；指定后，视频会马上自动开始播放，不会停下来等着数据载入结束。**注意**：在谷歌浏览器中即使设置了`autoplay` ，为了用户体验也不会自动播放，除非视频处于静音状态 |
| `buffered` | 这个属性可以读取到哪段时间范围内的媒体被缓存了。该属性包含了一个 `TimeRanges` 对象。 |
| `controls` | 加上这个属性，Gecko 会提供用户控制，允许用户控制视频的播放，包括音量，跨帧，暂停/恢复播放。 |
| `crossorigin` | 该枚举属性指明抓取相关图片是否必须用到CORS（跨域资源共享）。 支持CORS的资源 可在 [`<canvas>`](/zh-hans/webfrontend/<canvas>) 元素中被重用，而不会被污染。允许的值如下： |
| `height` | 视频展示区域的高度，单位是CSS像素。 |
| `loop` | 布尔属性；指定后，会在视频结尾的地方，自动返回视频开始的地方。 |
| `muted` | 布尔属性，指明了视频里的音频的默认设置。设置后，音频会初始化为静音。默认值是false,意味着视频播放的时候音频也会播放 。 |
| `played` | 一个 `TimeRanges` 对象，指明了视频已经播放的所有范围。 |
| `preload` | 该枚举属性旨在告诉浏览器作者认为达到最佳的用户体验的方式是什么。可能是下列值之一：<br>1. `none`: 提示作者认为用户不需要查看该视频，服务器也想要最小化访问流量；换句话说就是提示浏览器该视频不需要缓存。<br>2. `metadata`: 提示尽管作者认为用户不需要查看该视频，不过抓取元数据（比如：长度）还是很合理的。<br>3. `auto`: 用户需要这个视频优先加载；换句话说就是提示：如果需要的话，可以下载整个视频，即使用户并不一定会用它。<br>4. 空字符串：也就代指 `auto` 值。<br>假如不设置，默认值就是浏览器定义的了 （即，不同浏览器会选择自己的默认值），即使规范建议设置为 `metadata`。|
| `poster` | 一个海报帧的URL，用于在用户播放或者跳帧之前展示。如果属性未指定，那么在第一帧可用之前什么都不会展示；之后第一帧就像海报帧一样展示。 |
| `src` | 要嵌到页面的视频的URL。可选；你也可以使用video块内的 [`<source>`](/zh-hans/webfrontend/<source>) 元素来指定需要嵌到页面的视频。 |
| `width` | 视频显示区域的宽度，单位是CSS像素。 |

### 匿名

跨域请求（即，使用 `Origin:` 的HTTP头）会被执行。但是不发送凭证（即，不发送cookie， X.509 证书或者 HTTP Basic 授权）。如果服务器不提供证书给源站点
(不设置 `Access-Control-Allow-Origin:` HTTP头)，图片会被污染并且它的使用会受限。

### 使用凭证

跨域请求A cross-origin request (i.e. with `Origin:` HTTP header) 会被执行，且凭证会被发送 (即， 发送一个 cookie,
一个证书和HTTP Basic授权会被执行)。如果服务器不提供证书给源站点 (通过`Access-Control-Allow-Credentials:` HTTP 头)，图像会被污染且它的使用会受限。

不加这个属性时，抓取资源不会走CORS请求(即，不会发送 `Origin:` HTTP 头)，保证其在 [`<canvas>`](/zh-hans/webfrontend/<canvas>) 元素中使用时不会被污染。如果指定非法值，会被当作指定了枚举
关键字 **anonymous** 一样使用。 查看 CORS 设置属性 获取更多信息。

!!! warn "使用备注"
    - `autoplay` 属性优先于 `preload`。 假如用户想自动播放视频，那么很明显浏览器需要下载视频。同时设置 `autoplay` 和 `preload` 属性在规范里是允许的。
    - 但规范也没有强制浏览器去遵循该属性的值；这仅仅只是个提示。

时间偏移量目前是指定为float类型的值，表示偏移的秒数。

!!! warn "备注"
   HTML 5 规范中，时间偏移量值的定义还没有完成，有可能会变更。

## 事件

`<video>`元素可以触发许多不同的事件。

## 示例

```html
<!-- Simple video example -->
<video src="videofile.ogg" autoplay poster="posterimage.jpg">
  抱歉，您的浏览器不支持内嵌视频，不过不用担心，你可以 <a href="videofile.ogg">下载</a>
  并用你喜欢的播放器观看!
</video>

<!-- Video with subtitles -->
<video src="foo.ogg">
  <track kind="subtitles" src="foo.en.vtt" srclang="en" label="English">
  <track kind="subtitles" src="foo.sv.vtt" srclang="sv" label="Svenska">
</video>
```

第一个例子播放一个视频，视频收到，允许播放的时候就会立马开始播放，而不会停下来直到下载更多内容。 图片 "posterimage.jpg" 会一直展示在视频区域，直到开始播放。

第二个例子允许用户选择不同的字幕。

## 浏览器兼容性

| - | 谷歌 | 火狐 | Safari |
| :--- | :--- | :--- | :--- |
| `<video>` | 支持 | 支持 | 支持 |
