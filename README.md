# HTML Headings Autonumbering via CSS

A simple CSS library for creating automatically numbered section headings in HTML.

## Table of contents

* [Description](#description)
* [Usage](#usage)
* [Examples](#examples)
  * [A simple example](#a-simple-example)
  * [An advanced example](#an-advanced-example)
* [References](#references)
* [License](#license)

## Description

The CSS `counter()` function[^1] as well as the CSS `counter-reset` property[^2] are used to create automatic numbering for the `<h2>`-`<h6>` HTML section heading tags (the `<h1>` tag is intended to be used as an article title).

[^1]: More information about the CSS `counter()` function on the [MDN website](https://developer.mozilla.org/en-US/docs/Web/CSS/counter).
[^2]: More information about the CSS `counter-reset` property on the [MDN website](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset).

The number of a section heading is appended before the heading text. The number consists of a section number, a dot and subsequent subsection numbers if available. There are two non-breaking spaces (`\00a0`) added after the last dot that ends the number component.

All the code needed for automatic numbering of HTML headings is included in the [headings-autonumbering.css](headings-autonumbering.css) file. The rest files are only for example purposes.

## Usage

Link the [headings-autonumbering.css](headings-autonumbering.css) file in your HTML document:

```html
<head>
  <link rel="stylesheet" href="headings-autonumbering.css">
</head>
```

Then just add any container with the `headings-autonumbering` class:

```html
<div class="headings-autonumbering">
</div>
```

Now any usage of the `<h2>`-`<h6>` heading tags inside the container will be preceded by subsequent section numeration.

The `<h1>` section heading tag is intended to be used as an article title (only one usage per webpage), so it is not included in CSS heading counters.

## Examples

For a detailed example please see the [example.html](example.html) file.

### A simple example

The following code:

```html
<div class="headings-autonumbering">
  <h1>Article Title</h1>

  <h2>Introduction</h2>

  <h2>Section</h3>

  <h3>Subsection</h3>

  <h2>Conclusion</h2>
</div>
```

will produce the following output:

```
Article Title

1.  Introduction

2.  Section

2.1.  Subsection

3.  Conclusion
```

### An advanced example

The following code:

```html
<div class="headings-autonumbering">
  <h1>Article Title</h1>

  <h2>First section</h2>

  <h3>First subsection of first section</h3>

  <h3>Second subsection of first section</h3>

  <h4>First subsubsection of second subsection</h4>

  <h5>First subsubsubsection of first subsubsection</h5>

  <h6>First subsubsubsubsection of first subsubsubsection</h6>

  <h6>Second subsubsubsubsection of first subsubsubsection</h6>

  <h6>Third subsubsubsubsection of first subsubsubsection</h6>

  <h2>Second section</h2>

  <h3>First subsection of second section</h3>
</div>
```

will produce the following output:

```
Article Title

1.  First section

1.1.  First subsection of first section

1.2.  Second subsection of first section

1.2.1.  First subsubsection of second subsection

1.2.1.1.  First subsubsubsection of first subsubsection

1.2.1.1.1.  First subsubsubsubsection of first subsubsubsection

1.2.1.1.2.  Second subsubsubsubsection of first subsubsubsection

1.2.1.1.3.  Third subsubsubsubsection of first subsubsubsection

2.  Second section

2.1.  First subsection of second section
```

## References

1. MDN Web Docs: [CSS counter() function](https://developer.mozilla.org/en-US/docs/Web/CSS/counter).
1. MDN Web Docs: [CSS counter-reset property](https://developer.mozilla.org/en-US/docs/Web/CSS/counter-reset).
1. MDN Web Docs: [Using CSS counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters).
1. Stack Overflow: [How do I achieve automatic numbering for headings using css](https://stackoverflow.com/questions/38157007/how-do-i-achieve-automatic-numbering-for-headings-using-css).

## License

This project is licensed under the GNU General Public License v3.0 &ndash; see the [LICENSE.txt](LICENSE.txt) file for details.
