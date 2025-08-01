---
title: "<progress>: The Progress Indicator element"
slug: Web/HTML/Reference/Elements/progress
page-type: html-element
browser-compat: html.elements.progress
sidebar: htmlsidebar
---

The **`<progress>`** [HTML](/en-US/docs/Web/HTML) element displays an indicator showing the completion progress of a task, typically displayed as a progress bar.

{{InteractiveExample("HTML Demo: &lt;progress&gt;", "tabbed-standard")}}

```html interactive-example
<label for="file">File progress:</label>

<progress id="file" max="100" value="70">70%</progress>
```

```css interactive-example
label {
  padding-right: 10px;
  font-size: 1rem;
}
```

## Attributes

This element includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

- [`max`](/en-US/docs/Web/HTML/Reference/Attributes/max)
  - : This attribute describes how much work the task indicated by the `progress` element requires. The `max` attribute, if present, must have a value greater than `0` and be a valid floating point number. The default value is `1`.
- `value`
  - : This attribute specifies how much of the task that has been completed. It must be a valid floating point number between `0` and `max`, or between `0` and `1` if `max` is omitted. If there is no `value` attribute, the progress bar is indeterminate; this indicates that an activity is ongoing with no indication of how long it is expected to take.

> [!NOTE]
> Unlike the {{htmlelement("meter")}} element, the minimum value is always 0, and the `min` attribute is not allowed for the `<progress>` element.

> [!NOTE]
> The {{cssxref(":indeterminate")}} pseudo-class can be used to match against indeterminate progress bars. To change the progress bar to indeterminate after giving it a value you must remove the value attribute with {{domxref("Element.removeAttribute", "element.removeAttribute('value')")}}.

## Accessibility

### Labelling

In most cases you should provide an accessible label when using `<progress>`. While you can use the standard ARIA labelling attributes [`aria-labelledby`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-labelledby) or [`aria-label`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-label) as you would for any element with `role="progressbar"`, when using `<progress>` you can alternatively use the {{htmlelement("label")}} element.

> [!NOTE]
> Text placed between the element's tags is not an accessible label, it is only recommended as a fallback for old browsers that do not support this element.

#### Examples

```html
<label>
  Uploading Document: <progress value="70" max="100">70 %</progress>
</label>

<!-- OR -->
<br />

<label for="progress-bar">Uploading Document</label>
<progress id="progress-bar" value="70" max="100">70 %</progress>
```

#### Result

{{EmbedLiveSample('Labelling')}}

### Describing a particular region

If the `<progress>` element is describing the loading progress of a section of a page, use [`aria-describedby`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-describedby) to point to the status, and set [`aria-busy="true"`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-busy) on the section that is being updated, removing the `aria-busy` attribute when it has finished loading.

#### Examples

```html
<div aria-busy="true" aria-describedby="progress-bar">
  <!-- content is for this region is loading -->
</div>

<!-- ... -->

<progress id="progress-bar" aria-label="Content loading…"></progress>
```

##### Result

{{EmbedLiveSample('Describing a particular region')}}

## Examples

```html
<progress value="70" max="100">70 %</progress>
```

### Result

{{ EmbedLiveSample("Examples", 200, 50) }}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories">Content categories</a>
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content">Flow content</a>,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content">phrasing content</a>, labelable content,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#palpable_content">palpable content</a>.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content">Phrasing content</a>, but there must be no <code>&#x3C;progress></code> element among its
        descendants.
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
      <td><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/progressbar_role"><code>progressbar</code></a></td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>No <code>role</code> permitted</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLProgressElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Creating vertical form controls](/en-US/docs/Web/CSS/CSS_writing_modes/Vertical_controls)
- {{htmlelement("meter")}}
- {{ cssxref(":indeterminate") }}
- {{ cssxref("-moz-orient") }}
- {{ cssxref("::-moz-progress-bar") }}
- {{ cssxref("::-webkit-progress-bar") }}
- {{ cssxref("::-webkit-progress-value") }}
- {{ cssxref("::-webkit-progress-inner-element") }}
