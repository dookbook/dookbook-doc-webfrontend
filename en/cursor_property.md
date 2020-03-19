TOPICS: cursor property

# CSS Mouse Cursor Properties: `cursor`

The **`cursor`** CSS property defines **the mouse cursor displayed when the mouse pointer is hovering
over the element**.

## Property Value

| Property Value | Description |
| :--- | :--- |
| **`default`** | The default cursor, usually a **arrow** |
| **`auto`** | Default. Browser-set cursor |
| **`crosshair`** | The cursor appears as **cross hair** |
| **`pointer`** | The cursor is rendered as a pointer indicating a link **one hand** |
| **`move`** | This cursor indicates that an object **can be moved** |
| **`e-resize`** | This cursor indicates the edge of the rectangular frame **can be moved to the right (east)** |
| **`ne-resize`** | This cursor indicates the edge of the rectangular frame **can be moved up and to the right (North / East)** |
| **`nw-resize`** | This cursor indicates the edge of the rectangular frame **can be moved up and to the left (North / West)** |
| **`n-resize`** | This cursor indicates the edge of the rectangular frame **can be moved up (north)** |
| **`se-resize`** | This cursor indicates the edge of the rectangular frame **can be moved down and to the right (South / East)** |
| **`sw-resize`** | This cursor indicates the edge of the rectangular frame **can be moved down and to the left (South / West)** |
| **`s-resize`** | This cursor indicates the edge of the rectangular frame **can be moved down (North / West)** |
| **`w-resize`** | This cursor indicates the edge of the rectangular frame **can be moved to the left (west)** |
| **`text`** | This cursor indicates **text** |
| **`wait`** | This cursor indicates that **program is busy**, usually **a watch** or **hourglass** |
| **`help`** | This cursor indicates **available help**, usually **a question mark** or **a balloon** |
| **`none`** | **No pointer is rendered** |
| **`context-menu`** | Under the pointer **available content directory** |
| **`progress`** | **Program background is busy**, users can still interact (unlike *`wait`*) |
| **`cell`** | Indicates that **cells can be selected** |
| **`vertical-text`** | Indicates that **vertical text can be selected** |
| **`alias`** | **Copy** or **Shortcut will be created** |
| **`copy`** | Indication **Copyable** |
| **`no-drop`** | **Cannot drop the current position** |
| **`not-allowed`** | **Cannot execute** |
| **`all-scroll`** | Element **can scroll in any direction** (pan) |
| **`col-resize`** | Element **can be reset to width**. Usually rendered as **left and right arrows with a vertical line in the middle** |
| **`row-resize`** | Element **can be reset to height**. Usually rendered as **up and down arrows with a horizontal line in the middle** |
| **`ew-resize`** | **Bidirectional resize cursor** |
| **`ns-resize`** | **Bidirectional resize cursor** |
| **`nesw-resize`** | **Bidirectional resize cursor** |
| **`nwse-resize`** | **Bidirectional resize cursor** |
| **`zoom-in`** | Indication **can be enlarged** |
| **`zoom-out`** | Indicates that **can be reduced** |
| **`grab`** | **Something can be grabbed** (dragged to be moved).|
| **`grabbing`** | **Something is being grabbed** (dragged to be moved). |
| **url** | URL of **custom cursor to use**. <br>**Note**: Please always define a common cursor at the end of this list in case there is no available cursor defined by URL |

## Example

```html
<p>Please move your mouse over the word, you can see the mouse pointer changes:</p>
<span style="cursor:default;">default</span><br>
<span style="cursor:auto;">auto</span><br>
<span style="cursor:crosshair;">crosshair</span><br>
<span style="cursor:pointer;">pointer</span><br>
<span style="cursor:move;">move</span><br>
<span style="cursor:e-resize;">e-resize</span><br>
<span style="cursor:ne-resize;">ne-resize</span><br>
<span style="cursor:nw-resize;">nw-resize</span><br>
<span style="cursor:n-resize;">n-resize</span><br>
<span style="cursor:se-resize;">se-resize</span><br>
<span style="cursor:sw-resize;">sw-resize</span><br>
<span style="cursor:s-resize;">s-resize</span><br>
<span style="cursor:w-resize;">w-resize</span><br>
<span style="cursor:text;">text</span><br>
<span style="cursor:wait;">wait</span><br>
<span style="cursor:help;">help</span><br>
<span style="cursor:none;">none</span><br>
<span style="cursor:context-menu;">context-menu</span><br>
<span style="cursor:progress;">progress</span><br>
<span style="cursor:cell;">cell</span><br>
<span style="cursor:vertical-text;">vertical-text</span><br>
<span style="cursor:alias;">alias</span><br>
<span style="cursor:copy;">copy</span><br>
<span style="cursor:no-drop;">no-drop</span><br>
<span style="cursor:not-allowed;">not-allowed</span><br>
<span style="cursor:all-scroll;">all-scroll</span><br>
<span style="cursor:col-resize;">col-resize</span><br>
<span style="cursor:row-resize;">row-resize</span><br>
<span style="cursor:ew-resize;">ew-resize</span><br>
<span style="cursor:ns-resize;">ns-resize</span><br>
<span style="cursor:nesw-resize;">nesw-resize</span><br>
<span style="cursor:nwse-resize;">nwse-resize</span><br>
<span style="cursor:zoom-in;">zoom-in</span><br>
<span style="cursor:zoom-out;">zoom-out</span><br>
<span style="cursor:grab;">grab</span><br>
<span style="cursor:grabbing;">grabbing</span><br>
```
