---
title: "<sup>: The Superscript element"
slug: Web/HTML/Reference/Elements/sup
page-type: html-element
browser-compat: html.elements.sup
sidebar: htmlsidebar
---

The **`<sup>`** [HTML](/en-US/docs/Web/HTML) element specifies inline text which is to be displayed as superscript for solely typographical reasons. Superscripts are usually rendered with a raised baseline using smaller text.

{{InteractiveExample("HTML Demo: &lt;sup&gt;", "tabbed-shorter")}}

```html interactive-example
<p>
  The <em>Pythagorean theorem</em> is often expressed as the following equation:
</p>

<p>
  <var>a<sup>2</sup></var> + <var>b<sup>2</sup></var> = <var>c<sup>2</sup></var>
</p>
```

```css interactive-example
p {
  font:
    1rem "Fira Sans",
    sans-serif;
}
```

## Attributes

This element only includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

## Usage notes

The `<sup>` element should only be used for typographical reasons—that is, to change the position of the text to comply with typographical conventions or standards, rather than solely for presentation or appearance purposes.

For example, to style the [wordmark](https://en.wikipedia.org/wiki/Wordmark) of a business or product which uses a raised baseline should be done using CSS (most likely {{cssxref("vertical-align")}}) rather than `<sup>`. This would be done using, for example, `vertical-align: super` or, to shift the baseline up 50%, `vertical-align: 50%`.

Appropriate use cases for `<sup>` include (but aren't necessarily limited to):

- Displaying exponents, such as "x<sup>3</sup>". It may be worth considering the use of [MathML](/en-US/docs/Web/MathML) for these, especially in more complex cases. See [Exponents](#exponents) under [Examples](#examples) below.
- Displaying [superior lettering](https://en.wikipedia.org/wiki/Superior_letter), which is used in some languages when rendering certain abbreviations. For example, in French, the word "mademoiselle" can be abbreviated "M<sup>lle</sup>"; this is an acceptable use case. See [Superior lettering](#superior_lettering) for examples.
- Representing ordinal numbers, such as "4<sup>th</sup>" instead of "fourth." See [Ordinal numbers](#ordinal_numbers) for examples.

## Examples

### Exponents

Exponents, or powers of a number, are among the most common uses of superscripted text. For example:

```html
<p>
  One of the most common equations in all of physics is <var>E</var>=<var>m</var
  ><var>c</var><sup>2</sup>.
</p>
```

#### Result

{{EmbedLiveSample("Exponents", 650, 80)}}

### Superior lettering

Superior lettering is not technically the same thing as superscript. However, it is common to use `<sup>` to present superior lettering in HTML. Among the most common uses of superior lettering is the presentation of certain abbreviations in French:

```html
<p>Robert a présenté son rapport à M<sup>lle</sup> Bernard.</p>
```

#### Result

{{EmbedLiveSample("Superior_lettering", 650, 80)}}

### Ordinal numbers

Ordinal numbers, such as "fourth" in English or "quinto" in Spanish may be abbreviated using numerals and language-specific text rendered in superscript:

```html
<p>
  The ordinal number "fifth" can be abbreviated in various languages as follows:
</p>
<ul>
  <li>English: 5<sup>th</sup></li>
  <li>French: 5<sup>ème</sup></li>
</ul>
```

#### Result

{{EmbedLiveSample("Ordinal_numbers", 650, 160)}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories"
          >Content categories</a
        >
      </th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#flow_content"
          >Flow content</a
        >,
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >, palpable content.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >Phrasing content</a
        >.
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
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories#phrasing_content"
          >phrasing content</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <code
          ><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/structural_roles#structural_roles_with_html_equivalents">superscript</a
          ></code
        >
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

- The {{HTMLElement("sub")}} HTML element that produces subscripts. Note that you cannot use `sub` and `sup` at the same time: you need to use [MathML](/en-US/docs/Web/MathML) to produce both a superscript and a subscript next to the chemical symbol of an element, representing its atomic number and its nuclear number.
- The [`<msub>`](/en-US/docs/Web/MathML/Reference/Element/msub), [`<msup>`](/en-US/docs/Web/MathML/Reference/Element/msup), and [`<msubsup>`](/en-US/docs/Web/MathML/Reference/Element/msubsup) MathML elements.
- The CSS {{cssxref("vertical-align")}} property.
