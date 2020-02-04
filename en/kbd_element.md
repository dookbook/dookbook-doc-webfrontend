TOPICS: <kbd>

# HTML Keyboard Input Element: `<kbd>`

The **HTML Keyboard Input element** (**`<kbd>`**) represents a span of inline text denoting textual user
**input from a keyboard**, **voice input**, or any other **text entry device**.
By convention, the user agent
defaults to rendering the contents of a `<kbd>` element using its default `monospace` font, although
this is not mandated by the HTML standard.

`<kbd>` may be nested in various combinations with the *[`<samp>`](/en/webfrontend/<samp>)*
(Sample Output) element to represent various forms of input or input based on visual cues.

## Technical Summary

|  |  |
| :-- | :-- |
| **Content categories** | *Flow content*, *phrasing content*, *palpable content*. |
| **Permitted content** | *Phrasing content*. |
| **Tag omission** | None, both the starting and ending tag are mandatory. |
| **Permitted parents** | Any element that accepts *phrasing content*. |
| **Permitted ARIA roles** | Any |
| **DOM interface** | **`HTMLElement`** |

## Attributes

This element only includes the [global attributes](/en/webfrontend/HTML_Global_Attributes).

## Usage Notes

Other elements can be used in tandem with `<kbd>` to represent more specific scenarios:

- Nesting a `<kbd>` element within another `<kbd>` element represents an actual key or other unit of
input as a portion of a larger input. See Representing keystrokes within an input below.
- Nesting a `<kbd>` element inside a *[`<samp>`](/en/webfrontend/<samp>)* element represents input
that has been echoed back to the user by the system. See Echoed input, below, for an example.
- Nesting a *[`<samp>`](/en/webfrontend/<samp>)* element inside a `<kbd>` element, on the other hand,
represents input which is based on text presented by the system, such as the names of menus and menu
items, or the names of buttons displayed on the screen. See the example under Representing onscreen
input options below.
  
!!! warn "Styles for `<kbd>`"
    You can define a custom style to override the browser's default font selection for the `<kbd>` element,
    although the user's preferences may potentially override your [[CSS]].

## Examples

### Basic example

```html
<p>Use the command <kbd>help mycommand</kbd> to view documentation
for the command "mycommand".</p>
```

### Representing Keystrokes Within an Input

To describe an input comprised of multiple keystrokes, you can nest multiple `<kbd>` elements,
with an outer `<kbd>` element representing the overall input and each individual keystroke or
component of the input enclosed within its own `<kbd>`.

### Unstyled

First, let's look at what this looks like as just plain HTML.

```html
<p>You can also create a new document using the keyboard shortcut
<kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd>.</p>
```

This wraps the entire key sequence in an outer `<kbd>` element, then each individual key within its
own, in order to denote the components of the sequence.

### With Custom Styles

We can make more sense of this by adding some CSS:

We add a new style for `<kbd>` elements, "key", which we can apply when rendering keyboard keys:

```css
kbd.key {
  border-radius: 3px;
  padding: 1px 2px 0;
  border: 1px solid black;
}
```

Then we update the HTML to use this class on the keys in the output to be presented:

```html
<p>You can also create a new document by pressing <kbd><kbd class="key">Ctrl</kbd>+<kbd class="key">N</kbd></kbd>.</p>
```

### Echoed Input

Nesting a `<kbd>` element inside a [`<samp>`](/en/webfrontend/<samp>) element represents input that
has been echoed back to the user by the system.

```html
<p>If a syntax error occurs, the tool will output the initial
command you typed for your review:</p>
<blockquote>
  <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
</blockquote>
```

### Representing Onscreen Input Options

Nesting a [`<samp>`](/en/webfrontend/<samp>) element inside a `<kbd>` element represents input which
is based on text presented by the system, such as the names of menus and menu items, or the names of
buttons displayed on the screen.

For example, you can explain how to choose the "New Document" option in the "File"
menu using HTML that looks like this:

```html
<p>To create a new file, choose the menu option
<kbd><kbd><samp>File</samp></kbd>⇒<kbd><samp>New
Document</samp></kbd></kbd>.</p>

<p>Don't forget to click the <kbd><samp>OK</samp></kbd> button
to confirm once you've entered the name of the new file.</p>
```

This does some interesting nesting. For the menu option description, the entire input is enclosed in
a `<kbd>` element. Then, inside that, both the menu and menu item names are  contained within both
`<kbd>` and [`<samp>`](/en/webfrontend/<samp>), indicating an input which is selected from a screen widget.

Similarly, the representation of the keyboard shortcut is done by enclosing the entire keyboard
shortcut text inside `<kbd>`, but by also wrapping each key in its own `<kbd>` element.

You don't need to do all this wrapping; you can choose to simplify it by leaving out the external
`<kbd>` element. In other words, simplifying this to just
`<kbd>Ctrl</kbd>+<kbd>N</kbd>` would be perfectly valid.

Depending on your style sheet , though, you may find it useful to do this kind of nesting.
