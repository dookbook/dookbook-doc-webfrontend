TOPICS: <acronym>
        <applet>
        <basefont>
        <bgsound>
        <big>
        <blink>
        <center>
        <command>
        <content>
        <dir>
        <element>
        <font>
        <frame>
        <frameset>
        <image>
        <isindex>
        <keygen>
        <listing>
        <marquee>
        <menuitem>
        <multicol>
        <nextid>
        <nobr>
        <noembed>
        <noframes>
        <plaintext>
        <shadow>
        <spacer>
        <strike>
        <tt>
        <xmp>

# Obsolete and Deprecated HTML Elements

!!! error ""
    Warning: These are old HTML elements which are deprecated and should not be used. You should never
    use them in new projects, and should replace them in old projects as soon as you can. They are listed
    here for informational purposes only.

| Element | Description |
| :------ | :---------- |
| **`<acronym>`** | HTML acronym element. Indicate a sequence of characters that compose an **acronym** or **abbreviation** for a word. In HTML 5, use **[`<abbr>`](/en/webfrontend/<abbr>)** instead. |
| **`<applet>`** | HTML Applet element. Embeds a **Java applet** into the document; this element has been deprecated in favor of **[`<object>`](/en/webfrontend/<object>)**. |
| `<basefont>` | The obsolete HTML Base Font element (`<basefont>`) sets a default font face, size, and color for the other elements which are descended from its parent element. |
| `<bgsound>` | The Internet Explorer only HTML Background Sound element (`<bgsound>`) sets up a sound file to play in the background while the page is used; use [`<audio>`](/en/webfrontend/<audio>) instead. |
| `<big>` | The obsolete **HTML Big Element (`<big>`)** renders the enclosed text at a font size one level larger than the surrounding text (`medium` becomes `large`, for example).|
| `<blink>` | The **HTML Blink Element (`<blink>`)** is a non-standard element which causes the enclosed text to flash slowly. |
| `<center>` | The obsolete **HTML Center Element (`<center>`)** is a block-level element that displays its block-level or inline contents centered horizontally within its containing element. |
| `<command>` | The **HTML Command element (`<command>`)** represents a command which the user can invoke. Commands are often used as part of a context menu or toolbar. |
| `<content>` | The **HTML `<content>` element**—an obsolete part of the Web Components suite of technologies—was used inside of Shadow DOM as an insertion point, and wasn't meant to be used in ordinary HTML. |
| **`<dir>`** | HTML directory element. Used as a **container for a directory** of files and/or folders, potentially with styles and icons applied by the user agent. Use **[`<ul>`](/en/webfrontend/<ul>)** instead. |
| `<element>` | The obsolete **HTML `<element>` element** was part of the Web Components specification; it was intended to be used to define new custom DOM elements. |
| `<font>` | The **HTML Font Element (`<font>`)** defines the font size, color and face for its content. |
| **`<frameset>`** | Define a frameset. It is used to organize one or more **`<frame>`** elements. In HTML5, use **[`<iframe>`](/en/webfrontend/<iframe>)** instead. |
| **`<frame>`** | Define child windows (frames) in **`<frameset>`**. In HTML5, use **[`<iframe>`](/en/webfrontend/<iframe>)** instead. |
| **`<noframes>`** | The obsolete HTML No Frames or frame fallback element, provides content to be presented in browsers that don't support (or have disabled support for) the **`<frame>`** element. Completely outdated in HTML5 |
| **`<image>`** | HTML image element. An obsolete remnant of an ancient version of HTML lost in the mists of time; use the standard **[`<img>`](/en/webfrontend/<img>)** element instead. |
| **`<isindex>`** | It is used to make the browser display a **dialog**, prompting the user to enter **single line of text**. In HTML5, use **[`<input>`](/en/webfrontend/<input>)** instead. |
| **`<keygen>`** | HTML key generation element. Facilitate **generation of key** material, and **submission of the public key** as part of an *HTML form*. This mechanism is designed for use with Web-based certificate management systems. It is expected that it will be used in an HTML form along with other information needed to construct a certificate request, and that the result of the process will be a signed certificate. |
| **`<listing>`** | HTML listing element. Render text between the start and end tags without interpreting the HTML in between and using a *`monospaced`* font. The HTML 2 standard recommended that lines shouldn't be broken when not greater than 132 characters. Use **[`<pre>`](/en/webfrontend/<pre>)** or **[`<samp>`](/en/webfrontend/<samp>)** element instead. |
| `<marquee>` | The HTML `<marquee>` element is used to insert a scrolling area of text. You can control what happens when the text reaches the edges of its content area using its attributes. |
| **`<menuitem>`** | HTML menu item element. Represent a command that a user is able to invoke through a **popup menu**. More details to refer to **[`<menu>`](/en/webfrontend/<menu>)**. |
| `<multicol>` | The HTML Multi-Column Layout element (`<multicol>`) was an experimental element designed to allow multi-column layouts and must not be used. |
| `<nextid>` | `<nextid>` is an obsolete HTML element that served to enable the NeXT web designing tool to generate automatic NAME labels for its anchors. |
| `<nobr>` | The non-standard, obsolete HTML `<nobr>` element prevents the text it contains from automatically wrapping across multiple lines, potentially resulting in the user having to scroll horizontally to see the entire width of the text. |
| `<noembed>` | The `<noembed>` element is an obsolete, non-standard way to provide alternative, or "fallback", content for browsers that do not support the [`<embed>`](/en/webfrontend/<embed>) element or do not support the type of embedded content an author wishes to use. |
| **`<plaintext>`** | HTML plaintext element. Render everything following the start tag as **raw text** (**plaintext**), ignoring any following HTML. Use **[`<pre>`](/en/webfrontend/<pre>)** instead. |
| `<shadow>` | The **HTML `<shadow>` element**—an obsolete part of the Web Components technology suite—was intended to be used as a shadow DOM insertion point. |
| **`<spacer>`** | HTML space element. Allow insertion of **empty spaces** on pages. Use HTML **`&nbsp;`** or [[CSS]] instead. |
| **`<strike>`** | HTML strike-through element. For deleted text, use **[`<del>`](/en/webfrontend/<del>)** instead; For style (horizontal line) over text, use CSS property **`text-decoration: line-through`** instead; For text that are no longer relevant or no longer accurate, use **[`<s>`](/en/webfrontend/<s>)** instead. |
| **`<tt>`** | HTML Teletype Text element. Create inline text which is presented using the user agent's default *`monospace`* font face. Use [[CSS]] instead. |
| **`<xmp>`** | HTML Example Element. Render text between the start and end tags **without interpreting the HTML** in between and using a *`monospaced`* font. The *HTML 2* specification recommended that it should be rendered wide enough to allow *80* characters per line. Use **[`<pre>`](/en/webfrontend/<pre>)** or **[`<samp>`](/en/webfrontend/<samp>)** instead. |
