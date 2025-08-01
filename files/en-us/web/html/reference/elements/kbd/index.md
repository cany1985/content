---
title: "<kbd>: The Keyboard Input element"
slug: Web/HTML/Reference/Elements/kbd
page-type: html-element
browser-compat: html.elements.kbd
sidebar: htmlsidebar
---

The **`<kbd>`** [HTML](/en-US/docs/Web/HTML) element represents a span of inline text denoting textual user input from a keyboard, voice input, or any other text entry device. By convention, the {{Glossary("user agent")}} defaults to rendering the contents of a `<kbd>` element using its default monospace font, although this is not mandated by the HTML standard.

{{InteractiveExample("HTML Demo: &lt;kbd&gt;", "tabbed-shorter")}}

```html interactive-example
<p>
  Please press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd> to re-render an
  MDN page.
</p>
```

```css interactive-example
kbd {
  background-color: #eee;
  border-radius: 3px;
  border: 1px solid #b4b4b4;
  box-shadow:
    0 1px 1px rgb(0 0 0 / 0.2),
    0 2px 0 0 rgb(255 255 255 / 0.7) inset;
  color: #333;
  display: inline-block;
  font-size: 0.85em;
  font-weight: 700;
  line-height: 1;
  padding: 2px 4px;
  white-space: nowrap;
}
```

`<kbd>` may be nested in various combinations with the {{HTMLElement("samp")}} (Sample Output) element to represent various forms of input or output based on visual cues.

## Attributes

This element only includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

## Usage notes

Other elements can be used in tandem with `<kbd>` to represent more specific scenarios:

- Nesting a `<kbd>` element within another `<kbd>` element represents an actual key or other unit of input as a portion of a larger input. See [Representing keystrokes within an input](#representing_keystrokes_within_an_input) below.
- Nesting a `<kbd>` element inside a {{HTMLElement("samp")}} element represents input that has been echoed back to the user by the system. See [Echoed input](#echoed_input), below, for an example.
- Nesting a `<samp>` element inside a `<kbd>` element, on the other hand, represents input which is based on text presented by the system, such as the names of menus and menu items, or the names of buttons displayed on the screen. See the example under [Representing onscreen input options](#representing_onscreen_input_options) below.

> [!NOTE]
> You can define a custom style to override the browser's default font selection for the `<kbd>` element, although the user's preferences may potentially override your CSS.

## Examples

### Basic example

```html
<p>
  Use the command <kbd>help my-command</kbd> to view documentation for the
  command "my-command".
</p>
```

#### Result

{{ EmbedLiveSample('Basic_example', 350, 80) }}

### Representing keystrokes within an input

To describe an input comprised of multiple keystrokes, you can nest multiple `<kbd>` elements, with an outer `<kbd>` element representing the overall input and each individual keystroke or component of the input enclosed within its own `<kbd>`.

#### Unstyled

First, let's look at what this looks like as just plain HTML.

##### HTML

```html
<p>
  You can also create a new document using the
  <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd> keyboard shortcut.
</p>
```

This wraps the entire key sequence in an outer `<kbd>` element, then each individual key within its own, in order to denote the components of the sequence.

> [!NOTE]
> You don't need to do all this wrapping; you can choose to simplify it by leaving out the external `<kbd>` element. In other words, simplifying this to just `<kbd>Ctrl</kbd>+<kbd>N</kbd>` would be perfectly valid.
>
> Depending on your style sheet, though, you may find it useful to do this kind of nesting.

##### Result

The output looks like this without a style sheet applied:

{{EmbedLiveSample("Unstyled", 650, 80)}}

#### With custom styles

We can make more sense of this by adding some CSS:

##### CSS

We add a new selector for nested `<kbd>` elements, `kbd>kbd`, which we can apply when rendering keyboard keys:

```css
kbd > kbd {
  border-radius: 3px;
  padding: 1px 2px 0;
  border: 1px solid black;
}
```

##### HTML

Then we update the HTML to use this class on the keys in the output to be presented:

```html
<p>
  You can also create a new document by pressing the
  <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd> shortcut.
</p>
```

##### Result

The result is just what we want!

{{EmbedLiveSample("With_custom_styles", 650, 80)}}

### Echoed input

Nesting a `<kbd>` element inside a {{HTMLElement("samp")}} element represents input that has been echoed back to the user by the system.

```html
<p>
  If a syntax error occurs, the tool will output the initial command you typed
  for your review:
</p>
<blockquote>
  <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
</blockquote>
```

#### Result

{{EmbedLiveSample("Echoed_input", 650, 100)}}

### Representing onscreen input options

Nesting a `<samp>` element inside a `<kbd>` element represents input which is based on text presented by the system, such as the names of menus and menu items, or the names of buttons displayed on the screen.

For example, you can explain how to choose the "New Document" option in the "File" menu using HTML that looks like this:

```html-nolint
<p>
  To create a new file, choose the <kbd><kbd><samp>File</samp></kbd>
  ⇒<kbd><samp>New Document</samp></kbd></kbd> menu option.
</p>

<p>
  Don't forget to click the <kbd><samp>OK</samp></kbd> button to confirm once
  you've entered the name of the new file.
</p>
```

This does some interesting nesting. For the menu option description, the entire input is enclosed in a `<kbd>` element. Then, inside that, both the menu and menu item names are contained within both `<kbd>` and `<samp>`, indicating an input which is selected from a screen widget.

#### Result

{{EmbedLiveSample("Representing_onscreen_input_options", 650, 120)}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories">Content categories</a>
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content">Flow content</a>,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content">phrasing content</a>, palpable content.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content">Phrasing content</a>.
      </td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>None, both the starting and ending tag are mandatory.</td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>
        Any element that accepts
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content">phrasing content</a>.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <a href="https://w3c.github.io/html-aria/#dfn-no-corresponding-role">No corresponding role</a>
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{htmlelement("code")}}
