TOPICS: accesskey
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# accesskey

The **`accesskey`** [global attribute](/en/webfrontend/HTML_Global_Attribute)
provides a hint for generating a keyboard shortcut for the current element. The attribute value must
consist of a single printable character (which includes accented and other characters that can be
generated by the keyboard).

!!! warn "Don't try this at home"
    Note: In the WHATWG spec, it says you can specify multiple space-separated characters, and the
    browser will use the first one it supports. However, this does not work in most browsers. IE/Edge
    uses the first one it supports without problems, provided there are no conflicts with other commands.

The way to activate the accesskey depends on the browser and its platform:

|  | Windows | Linux | Mac |
| :-- | :-- | :-- | :-- |
| **Firefox** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | On Firefox 57 or newer: !!!Control!!! + !!!Option!!! + !!!key!!! or !!!Control!!! + !!!Alt!!! + !!!key!!!<br>On Firefox 14 or newer: !!!Control!!! + !!!Alt!!! + !!!key!!!<br>On Firefox 13 or older: !!!Control!!! + !!!key!!!
| **Edge** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Internet Explorer** | !!!Alt!!! + !!!key!!! | N/A | N/A |
| **Google Chrome** | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Alt!!! + !!!Shift!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!!
| **Safari** | !!!Alt!!! + !!!key!!! | N/A | !!!Control!!! + !!!Alt!!! + !!!key!!!
| **Opera 15+** | !!!Alt!!! + !!!key!!! | !!!Alt!!! + !!!key!!! | !!!Control!!! + !!!Alt!!! + !!!key!!!
| **Opera 12** | !!!Shift!!! + !!!Esc!!! opens a contents list which are accessible by accesskey, then, can choose an item by pressing key | <- | <- |

## Accessibility concerns

In addition to poor browser support, there are numerous concerns with the `accesskey` attribute:

- An `accesskey` value can conflict with a system or browser keyboard shortcut, or assistive technology
functionality. What may work for one combination of operating system, assistive technology, and
browser may not work with other combinations.
- Certain `accesskey` values may not be present on certain keyboards, especially when
internationalization is a concern. So adapting to specific languages could cause further problems.
- `accesskey` values that rely on numbers may be confusing to individuals experiencing cognitive
concerns, where the number doesn't have a logical association with the functionality it triggers.
- Informing the user that `accesskey`s are present, so that they are aware of the functionality. If
the system lacks a method of notifying the user about this feature, the user might accidentally
activate `accesskey`s.

Because of these issues, it is generally advised not to use `accesskey`s for most general-purpose
websites and web apps.

- [WebAIM: Keyboard Accessibility - Accesskey](https://webaim.org/techniques/keyboard/accesskey#spec)

## See also

- [`Element.accessKey`](/en/webfrontend/Element.accessKey)
- [`HTMLElement.accessKeyLabel`](/en/webfrontend/HTMLElement.accessKeyLabel)
- All HTML [global attributes](/en/webfrontend/HTML_Global_Attribute).