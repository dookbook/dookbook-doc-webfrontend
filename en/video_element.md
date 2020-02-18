TOPICS: <video>

# `<video>`

The **HTML Video element (`<video>`)** embeds a media player which supports video playback into the
document. You can use `<video>` for audio content as well, but the [`<audio>`](/en/webfrontend/<audio>)
element may provide a more appropriate user experience.

The above example shows simple usage of the `<video>` element. In a similar manner to the
[`<img>`](/en/webfrontend/<img>) element, we include a path to the media we want to display inside
the src attribute; we can include other attributes to specify information such as video width and
height, whether we want it to autoplay and loop, whether we want to show the browser's default
video controls, etc.

The content inside the opening and closing `<video></video>` TOPICS is shown as a
fallback in browsers that don't support the element.

Browsers don't all support the same video formats; you can provide multiple sources inside nested
[`<source>`](/en/webfrontend/<source>) elements, and the browser will then use the first one it understands:

```html
<video controls>
  <source src="myVideo.mp4" type="video/mp4">
  <source src="myVideo.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is
     a <a href="myVideo.mp4">link to the video</a> instead.</p>
</video>
```

Other Usage Notes:

- If you don't specify the `controls` attribute, the video won't include the browser's default controls;
you can create your own custom controls using JavaScript and the `HTMLMediaElement` API. See
Creating a cross-browser video player for more details.
- To allow precise control over your video (and audio) content,
`HTMLMediaElements` fire many different events.
- You can use the `object-position` property to adjust the positioning of the video within
the element's frame, and the `object-fit` property to control how the video's size is adjusted
to fit within the frame.
- To show subtitles/captions along with your video, you can use some JavaScript along with the
[`<track>`](/en/webfrontend/<track>) element and the WebVTT format. See
Adding captions and subtitles to HTML5 video for more information.

A good general source of information on using HTML `<video>` is the
Video and audio content beginner's tutorial.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *embedded content*. <br>If it has a `controls` attribute: *interactive content* and *palpable content*. |
| **Permitted content** | If the element has a src attribute: zero or more [`<track>`](/en/webfrontend/<track>) elements, followed by *transparent content* that contains no media elements–that is no [`<audio>`](/en/webfrontend/<audio>) or `<video>`<br>Else: zero or more [`<source>`](/en/webfrontend/<source>) elements, followed by zero or more [`<track>`](/en/webfrontend/<track>) elements, followed by transparent content that contains no media elements–that is no [`<audio>`](/en/webfrontend/<audio>) or `<video>`. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *embedded content*. |
| **Permitted ARIA roles** | `application` |
| **DOM interface** | **`HTMLVideoElement`** |

## Attributes

Like all other HTML elements, this element supports the [global attributes](/en/webfrontend/HTML_Global_Attributes).

| Attribute | Description |
| :-- | :-- |
| `autoplay` | A Boolean attribute; if specified, the video automatically begins to play back as soon as it can do so without stopping to finish loading the data.<br>**Note:** Sites that automatically play audio (or video with an audio track) can be an unpleasant experience for users, so it should be avoided when possible. If you must offer autoplay functionality, you should make it opt-in (requiring a user to specifically enable it). However, this can be useful when creating media elements whose source will be set at a later time, under user control.<br>**Note:** To disable video autoplay, `autoplay="false"` will not work; the video will autoplay if the attribute is there in the `<video>` tag at all. To remove autoplay the attribute needs to be removed altogether.<br>**Note:** In some browsers (e.g. Chrome 70.0) autoplay is not working if no `muted` attribute is present. |
| `buffered` | An attribute you can read to determine the time ranges of the buffered media. This attribute contains a TimeRanges object. |
| `controls` | If this attribute is present, the browser will offer controls to allow the user to control video playback, including volume, seeking, and pause/resume playback. |
| `crossorigin` | This enumerated attribute indicates whether to use CORS to fetch the related image. CORS-enabled resources can be reused in the [`<canvas>`](/en/webfrontend/<canvas>) element without being tainted. The allowed values are:<br>**`anonymous`**<br>Sends a cross-origin request without a credential. In other words, it sends the `Origin:` HTTP header<br>without a cookie, X.509 certificate, or performing HTTP Basic authentication. If the server does not give credentials to the origin site (by not setting the `Access-Control-Allow-Origin:` HTTP header), the image will be tainted, and its usage restricted.<br>**`use-credentials`**<br>Sends a cross-origin request with a credential. In other words, it sends the `Origin:` HTTP header with a cookie, a certificate, or performing HTTP Basic authentication. If the server does not give credentials to the origin site (through `Access-Control-Allow-Credentials:` HTTP header), the image will be tainted and its usage restricted.<br>When not present, the resource is fetched without a CORS request (i.e. without sending the `Origin:` HTTP header), preventing its non-tainted used in [`<canvas>`](/en/webfrontend/<canvas>) elements. If invalid, it is handled as if the enumerated keyword `anonymous` was used. See CORS settings attributes for additional information. |
| `height` | The height of the video's display area, in CSS pixels (absolute values only; no percentages.) |
| `intrinsicsize` | This attribute tells the browser to ignore the actual intrinsic size of the image and pretend it’s the size specified in the attribute. Specifically, the image would raster at these dimensions and naturalWidth/naturalHeight on images would return the values specified in this attribute. `Explainer`, `examples`. |
| `loop` | A Boolean attribute; if specified, the browser will automatically seek back to the start upon reaching the end of the video. |
| `muted` | A Boolean attribute that indicates the default setting of the audio contained in the video. If set, the audio will be initially silenced. Its default value is false, meaning that the audio will be played when the video is played. |
| `preload` | This enumerated attribute is intended to provide a hint to the browser about what the author thinks will lead to the best user experience with regards to what content is loaded before the video is played. It may have one of the following values:<br>**`none`:** Indicates that the video should not be preloaded. metadata: Indicates that only video metadata (e.g. length) is fetched.<br>**`auto`:** Indicates that the whole video file can be downloaded, even if the user is not expected to use it.<br>**empty string:** Synonym of the `auto` value. The default value is different for each browser. The spec advises it to be set to `metadata`.<br>**Notes:**<br>The `autoplay` attribute has precedence over `preload`. If `autoplay` is specified, the browser would obviously need to start downloading the video for playback.<br>The specification does not force the browser to follow the value of this attribute; it is a mere hint. |
| `playsinline` | A Boolean attribute indicating that the video is to be played "inline", that is within the element's playback area. Note that the absence of this attribute does not imply that the video will always be played in fullscreen. |
| `poster` | A URL for an image to be shown while the video is downloading. If this attribute isn't specified, nothing is displayed until the first frame is available, then the first frame is shown as the poster frame. |
| `src` | The URL of the video to embed. This is optional; you may instead use the [`<source>`](/en/webfrontend/<source>) element within the video block to specify the video to embed. |
| `width` | The width of the video's display area, in CSS pixels (absolute values only; no percentages). |

## Events

| Event Name | Fired When |
| :-- | :-- |
| `audioprocess` | The input buffer of a ScriptProcessorNode is ready to be processed. |
| `canplay` | The browser can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content. |
| `canplaythrough` | The browser estimates it can play the media up to its end without stopping for content buffering. |
| `complete` | The rendering of an OfflineAudioContext is terminated. |
| `durationchange` | The duration attribute has been updated. |
| `emptied` | The media has become empty; for example, this event is sent if the media has already been loaded (or partially loaded), and the load() method is called to reload it. |
| `ended` | Playback has stopped because the end of the media was reached. |
| `loadeddata` | The first frame of the media has finished loading. |
| `loadedmetadata` | The metadata has been loaded. |
| `pause` | Playback has been paused. |
| `play` | Playback has begun. |
| `playing` | Playback is ready to start after having been paused or delayed due to lack of data. |
| `ratechange` | The playback rate has changed. |
| `seeked` | A seek operation completed. |
| `seeking` | A seek operation began. |
| `stalled` | The user agent is trying to fetch media data, but data is unexpectedly not forthcoming. |
| `suspend` | Media data loading has been suspended. |
| `timeupdate` | The time indicated by the currentTime attribute has been updated. |
| `volumechange` | The volume has changed. |
| `waiting` | Playback has stopped because of a temporary lack of data. |

## Usage Notes

### Styling with CSS

The `<video>` element is a replaced element — its `display` value is `inline` by default,
but its default width and height in the viewport is defined by the video being embedded.

There are no special considerations for styling `<video>`; a common strategy is to give it a
`display` value of `block` to make it easier to position, size, etc., and then provide styling and
layout information as required. Video player styling basics provides some useful styling techniques.

### Detecting track addition and removal

You can detect when tracks are added to and removed from a `<video>` element using
the `addtrack` and `removetrack` events. However, these events aren't sent directly to
the `<video>` element itself. Instead, they're sent to the track list object within the `<video>`
element's `HTMLMediaElement` that corresponds to the type of track that was added to the element:

- `HTMLMediaElement.audioTracks`

An `AudioTrackList` containing all of the media element's audio tracks. You can add a listener
for `addtrack` to this object to be alerted when new audio tracks are added to the element.

- `HTMLMediaElement.videoTracks`

Add an `addtrack` listener to this `VideoTrackList` object to be informed when video tracks
are added to the element.

- `HTMLMediaElement.textTracks`

Add an `addtrack` event listener to this `TextTrackList` to be notified when new text tracks
are added to the element.

For example, to detect when audio tracks are added to or removed from a `<video>` element,
you can use code like this:

```javascript
var elem = document.querySelector("video");

elem.audioTrackList.onaddtrack = function(event) {
  trackEditor.addTrack(event.track);
};

elem.audioTrackList.onremovetrack = function(event) {
  trackEditor.removeTrack(event.track);
};
```

This code watches for audio tracks to be added to and removed from the element, and calls a
hypothetical function on a track editor to register and remove the track from the
editor's list of available tracks.

You can also use `addEventListener()` to listen for the `addtrack`
and `removetrack` events.

## Examples

### Simple Video Example

This example plays a video when activated, providing the user with the browser's default
video controls to control playback.

```html
<!-- Simple video example -->
<!-- 'Big Buck Bunny' licensed under CC 3.0 by the Blender foundation. Hosted by archive.org -->
<!-- Poster from peach.blender.org -->
<video controls
    src="https://archive.org/download/BigBuckBunny_124/Content/big_buck_bunny_720p_surround.mp4"
    poster="https://peach.blender.org/wp-content/uploads/title_anouncement.jpg?x11217"
    width="620">

Sorry, your browser doesn't support embedded videos,
but don't worry, you can <a href="https://archive.org/details/BigBuckBunny_124">download it</a>
and watch it with your favorite video player!

</video>
```

Until the video starts playing, the image provided in the `poster` attribute is displayed in its
place. If the browser doesn't support video playback, the fallback text is displayed.

### Multiple Sources Example

This example builds on the last one, offering three different sources for the media; this allows the
video to be watched regardless of which video codecs are supported by the browser.

```html
<!-- Using multiple sources as fallbacks for a video tag -->
<!-- 'Elephants Dream' by Orange Open Movie Project Studio, licensed 
under CC-3.0, hosted by archive.org -->
<!-- Poster hosted by Wikimedia -->
<video width="620" controls
  poster="https://upload.wikimedia.org/wikipedia/commons/e/e8/Elephants_Dream_s5_both.jpg" >
  <source
    src="https://archive.org/download/ElephantsDream/ed_1024_512kb.mp4"
    type="video/mp4">
  <source
    src="https://archive.org/download/ElephantsDream/ed_hd.ogv"
    type="video/ogg">
  <source
    src="https://archive.org/download/ElephantsDream/ed_hd.avi"
    type="video/avi">
  Your browser doesn't support HTML5 video tag.
</video>
```

First WebM is tried. If that can't be played, then MP4 is tried. Finally, OGG is tried. A fallback
message is displayed if the video tag isn't supported, but not if all sources fail.

### Server Support For Video

If the MIME type for the video is not set correctly on the server, the video may not show or show a
gray box containing an X (if JavaScript is enabled).

If you use Apache Web Server to serve Ogg Theora videos, you can fix this problem by adding the
video file type extensions to "video/ogg" MIME type. The most common video file type extensions are
".ogm", ".ogv", or ".ogg". To do this, edit the "`mime.types`" file in `/etc/apache` or use the
`"AddType"` configuration directive in `httpd.conf`.

```html
AddType video/ogg .ogm
AddType video/ogg .ogv
AddType video/ogg .ogg
```

If you serve your videos as WebM, you can fix this problem for the Apache Web Server by adding the
extension used by your video files (".webm" is the most common one) to the MIME type "video/webm"
via the "`mime.types`" file in "`/etc/apache`" or via the "AddType" configuration directive in `httpd.conf`.

```html
AddType video/webm .webm
```

Your web host may provide an easy interface to MIME type configuration changes for new technologies
until a global update naturally occurs.

## Accessibility Concerns

Videos should provide both captions and transcripts that accurately describe its content (see
Adding captions and subtitles to HTML5 video for more information on how to implement these).
Captions allow people who are experiencing hearing loss to understand a video's audio content as the
video is being played, while transcripts allow people who need additional time to be able to review
audio content at a pace and format that is comfortable for them.

If automatic captioning services are used, it is important to review the generated content to ensure
it accurately represents the source video.

In addition to spoken dialog, subtitles and transcripts should also identify music and sound effects
that communicate important information. This includes emotion and tone:

```http
14
00:03:14 --> 00:03:18
Dramatic rock music

15
00:03:19 --> 00:03:21
whispering What's that off in the distance?

16
00:03:22 --> 00:03:24
It's… it's a…

16 00:03:25 --> 00:03:32
Loud thumping
Dishes clattering
```

Captions should not obstruct the main subject of the video. They can be positioned
using the `align` VTT cue setting.

- MDN Subtitles and closed caption — Plugins
- Web Video Text Tracks Format (WebVTT)
- WebAIM: Captions, Transcripts, and Audio Descriptions
- MDN Understanding WCAG, Guideline 1.2 explanations
- Understanding Success Criterion 1.2.1 | W3C Understanding WCAG 2.0
- Understanding Success Criterion 1.2.2 | W3C Understanding WCAG 2.0
