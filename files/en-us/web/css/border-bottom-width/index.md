---
title: border-bottom-width
slug: Web/CSS/border-bottom-width
page-type: css-property
browser-compat: css.properties.border-bottom-width
sidebar: cssref
---

The **`border-bottom-width`** [CSS](/en-US/docs/Web/CSS) property sets the width of the bottom border of an element.

{{InteractiveExample("CSS Demo: border-bottom-width")}}

```css interactive-example-choice
border-bottom-width: thick;
```

```css interactive-example-choice
border-bottom-width: 2em;
```

```css interactive-example-choice
border-bottom-width: 4px;
```

```css interactive-example-choice
border-bottom-width: 2ex;
```

```css interactive-example-choice
border-bottom-width: 0;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box with a border around it.
  </div>
</section>
```

```css interactive-example
#example-element {
  background-color: palegreen;
  color: #000;
  border: 0 solid crimson;
  padding: 0.75em;
  width: 80%;
  height: 100px;
}
```

## Syntax

```css
/* Keyword values */
border-bottom-width: thin;
border-bottom-width: medium;
border-bottom-width: thick;

/* <length> values */
border-bottom-width: 10em;
border-bottom-width: 3vmax;
border-bottom-width: 6px;

/* Global keywords */
border-bottom-width: inherit;
border-bottom-width: initial;
border-bottom-width: revert;
border-bottom-width: revert-layer;
border-bottom-width: unset;
```

### Values

- `<line-width>`
  - : Defines the width of the border, either as an explicit nonnegative {{cssxref("&lt;length&gt;")}} or a keyword. If it's a keyword, it must be one of the following values:
    - `thin`
    - `medium`
    - `thick`

> [!NOTE]
> Because the specification doesn't define the exact thickness denoted by each keyword, the precise result when using one of them is implementation-specific. Nevertheless, they always follow the pattern `thin ≤ medium ≤ thick`, and the values are constant within a single document.

## Formal definition

{{CSSInfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Comparing bottom border widths

#### HTML

```html
<div>Element 1</div>
<div>Element 2</div>
```

#### CSS

```css
div {
  border: 1px solid red;
  margin: 1em 0;
}

div:nth-child(1) {
  border-bottom-width: thick;
}
div:nth-child(2) {
  border-bottom-width: 2em;
}
```

#### Result

{{EmbedLiveSample('Comparing_bottom_border_widths', '100%')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- The other border-width-related CSS properties: {{Cssxref("border-left-width")}}, {{Cssxref("border-right-width")}}, {{Cssxref("border-top-width")}}, and {{Cssxref("border-width")}}.
- The other border-bottom-related CSS properties: {{Cssxref("border")}}, {{Cssxref("border-bottom")}}, {{Cssxref("border-bottom-style")}}, and {{Cssxref("border-bottom-color")}}.
