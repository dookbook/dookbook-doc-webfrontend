TOPICS: dir attribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# HTML Global Attribute: `dir`

!!! warn "Note“
    The ~~ `<dir>` ~~ element has been deprecated in HTML 4.01. But in HTML5, the dir attribute can
    be used on any HTML element (it will validate any HTML element. But it is not necessarily useful).
    In HTML 4.01, the dir element cannot be used: `<base>`, `<br>`, `<frame>`, `<frameset>`, `<hr>`,
    `<iframe>`, `<param>`, and `<script>`.

The **`dir`** [global attribute](/en/webfrontend/HTML_Global_Attributes) is an enumerated attribute
that indicates the directionality of the element's text.

It can have the following values:

- `ltr`, which means left to right and is to be used for languages that are written from the left to
the right (like English);
- `rtl`, which means right to left and is to be used for languages that are written from the right
to the left (like Arabic);
- `auto`, which lets the user agent decide. It uses a basic algorithm as it parses the characters
inside the element until it finds a character with a strong directionality, then applies that
directionality to the whole element.

!!! warn "Don't try this at home"
    Usage notes
    This attribute is mandatory for the [`<bdo>`](/en/webfrontend/<bdo>) element where it has a
    different semantic meaning.
    1. This attribute is not inherited by the [`<bdi>`](/en/webfrontend/<bdo>) element. If not set,
    its value is auto.
    2. This attribute can be overridden by the CSS properties direction and unicode-bidi, if a CSS
    page is active and the element supports these properties.
    3. As the directionality of the text is semantically related to its content and not to its
    presentation, it is recommended that web developers use this attribute instead of the related CSS
    properties when possible. That way, the text will display correctly even on a browser that
    doesn't support CSS or has the CSS deactivated.
    4. The auto value should be used for data with an unknown directionality, like data coming from user
    input, eventually stored in a database.

## See also

- [`HTMLElement.dir`](/en/webfrontend/HTMLElement.dir) that reflects this attribute.
- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).
