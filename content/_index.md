---
title: Home
seo:
  page_title:
  meta_description:
  featured_image:
  featured_image_alt:
hero:
  heading:
  body:
  hero_image:
    image: /uploads/featured-image.jpg
    image_alt:
  button:
    button_url:
    button_text:
---

{{< column >}}
---
## Table of Contents
{{< /column >}}

{{< column >}}
{{< /column >}}

{{< column >}}
### HTML

* HTML syntax
* HTML5 doctype
* Language attribute
* Character encoding
* CSS and JavaScript includes
* Practicality over purity
* Attribute order
* Reduce markup
* Editor preferences

{{< /column >}}

{{< column >}}
### CSS

* CSS syntax
* Declaration order
* Colors
* Logical properties
* Avoid @import`s
* Media query placement
* Single declarations
* Shorthand notation
* Nesting in preprocessors
* Operators in preprocessors
* Comments
* Class names
* Selectors
* Child and descendant selectors
* Organization

{{< /column >}}

{{< column >}}
---
## Golden rule

Enforce these, or your own, agreed upon guidelines at all times. Small or large, call out what’s incorrect.

Every line of code should appear to be written by a single person, no matter the number of contributors.
{{< /column >}}

{{< column >}}
{{< /column >}}

{{< column >}}
---
## HTML
{{< /column >}}

{{< column >}}
{{< /column >}}


{{< column >}}
## Syntax

* Don’t capitalize tags, including the doctype.
* Nested elements should be indented once.
* Always use double quotes, never single quotes, on attributes.
* Don’t include a trailing slash in self-closing elements—the HTML5 spec says they’re optional.
* Don’t omit optional closing tags (e.g. </li> or </body>).
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<!doctype html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
</html>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## HTML5 doctype

Enforce standards mode and more consistent rendering in every browser possible with this simple doctype at the beginning of every HTML page. In keeping with the suggested syntax, keep it lowercase.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<!doctype html>
<html>
  <head>
    <!-- ... -->
  </head>
  <body>
    <!-- ... -->
  </body>
</html>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## Language attribute

From the HTML5 spec:

Authors are encouraged to specify a lang attribute on the root html element, giving the document’s language. This aids speech synthesis tools to determine what pronunciations to use, translation tools to determine what rules to use, and so forth.

Read more about the lang attribute in the spec. Head to the IANA for a list of language codes.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<html lang="en">
  <!-- ... -->
</html>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## Character encoding

Ensure proper content rendering by declaring an explicit character encoding. This also allows you to use regular characters instead of their HTML entities, like — instead of &emdash;, provided their encoding matches that of the document. For some reserved XML characters—like ampersand, non-breaking spaces, less/greater than, and quotes—you may still need to use the HTML character entities.

UTF-8 is the recommended encoding.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<head>
  <meta charset="utf-8">
</head>
<body>
  <p>Use an em dash like so—no HTML entity required.</p>
</body>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## CSS and JavaScript includes

Per HTML5 spec, typically there is no need to specify a type when including CSS and JavaScript files as text/css and text/javascript are their respective defaults.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<!-- External CSS -->
<link rel="stylesheet" href="code-guide.css">
<!-- In-document CSS -->
<style>
  /* ... */
</style>
<!-- JavaScript -->
<script src="code-guide.js"></script>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## Practicality over purity

Strive to maintain HTML standards and semantics, but not at the expense of practicality. Use the least amount of markup with the fewest intricacies whenever possible.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<!-- Good -->
<button>...</button>
```
```
<!-- Not good -->
<div class="btn" onClick="...">...</div>
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## Attribute order

HTML attributes should come in this particular order for easier reading of code.

* class
* id, name
* data-*
* src, for, type, href, value
* title, alt
* role, aria-*
* tabindex
* style

Attributes that are most commonly used for identifying elements should come first—class, id, name, and data attributes. Miscellaneous attributes unique to specific elements come second, followed by accessibility and style related attributes.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<a class="..." id="..." data-toggle="modal" href="#">
  Example link
</a>
<input class="form-control" type="text">
<img src="..." alt="...">
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
## Reduce markup

Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML.
{{< /column >}}


{{< column >}}
{{< code-html >}}
```
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>
```
```
<!-- Better -->
<img class="avatar" src="...">
```
{{< /code-html >}}
{{< /column >}}

{{< column >}}
---
## CSS
{{< /column >}}

{{< column >}}
{{< /column >}}

{{< column >}}
### Syntax

* When grouping selectors, keep individual selectors to a single line.
* Include one space before the opening brace of declaration blocks for legibility.
* Place closing braces of declaration blocks on a new line.
* Include one space after : for each declaration.
* Each declaration should appear on its own line for more accurate error reporting.
* End all declarations with a semi-colon. The last declaration’s is optional, but your code is more error prone without it.
* Comma-separated property values should include a space after each comma (e.g., box-shadow).
* Use space-separated values for color properties (e.g., color: rgb(0 0 0 / .5)). See the Colors section for more information.
* Don’t prefix property values or color parameters with a leading zero (e.g., .5 instead of 0.5 and -.5px instead of -0.5px).
* Lowercase all hex values, e.g., #fff. Lowercase letters are much easier to discern when scanning a document as they tend to have more unique shapes.
* Use shorthand hex values where available, e.g., #fff instead of #ffffff.
* Quote attribute values in selectors, e.g., input[type="text"]. They’re only optional in some cases, and it’s a good practice for consistency.
* Avoid specifying units for zero values, e.g., use margin: 0; instead of margin: 0px;.
{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Bad CSS
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}
```
```
// Good CSS
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgb(0 0 0 / .5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Declaration order

Property declarations should be grouped together in the following order:

* Positioning
* Box model
* Typographic
* Visual
* Misc

Positioning comes first because it can remove an element from the normal document flow and override box model related styles. The box model—whether it’s flex, float, grid, or table—follows as it dictates a component’s dimensions, placement, and alignment. Everything else takes place inside the component or without impacting the previous two sections, and thus they come last.

While ```border``` is part of the box model, most systems globally reset the ```box-sizing``` to ```border-box``` so that ```border-width``` doesn’t affect overall dimensions. This, combined with keeping ```border``` near ```border-radius```, is why it’s under the Visual section instead.

Preprocessor mixins and functions should appear wherever most appropriate. For example, a ```border-top-radius()``` mixin would go in place of ```border-radius``` properties, while a ```responsive-font-size()``` function would go in place of ```font-size``` properties.
{{< /column >}}

{{< column >}}
{{< code-css >}}
```
.declaration-order {
  // Positioning
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;
  // Box model
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 100px;
  // Typography
  font: normal 14px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;
  text-decoration: underline;
  // Visual
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;
  // Misc
  opacity: 1;
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Logical properties

Logical properties are alternatives to directional and dimensonal properties based on abstract terms like block and inline. By default, block refers to the vertical direction (top and bottom) while inline refers to the horizontal direction (right and left). You can begin to use these values in your CSS in all modern, evergreen browsers.

**Why use logical properties?** Not every language flows left-ro-right like English, so the writing mode needs to be flexible. With logical properties, you can easily support languages that can be written horizontally or vertically (like Chinese, Japanese, and Korean). Plus, they’re usually shorter and simpler to write.

Additional reading:

[CSS Logical Properties and Values – MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Logical_Properties)

[CSS Logical Properties and Values — CSS Tricks](https://css-tricks.com/css-logical-properties-and-values/)

[CSS Writing Modes – MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Writing_Modes)
{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Without logical properties
.element {
  margin-right: auto;
  margin-left: auto;
  border-top: 1px solid #eee;
  border-bottom: 1px solid #eee;
}
```
```
// With logical properties
.element {
  margin-inline: auto;
  border-block: 1px solid #eee;
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Colors

With the support of [CSS Color Levels 4](https://www.w3.org/TR/css-color-4/) in [all major browsers](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb#space-separated_values), ```rgba()``` and ```hsla()``` are now aliases for ```rgb()``` and ```hsl()```, meaning you can modify alpha values in ```rgb()``` and ```hsl()```. Along with this comes support for new space-separated syntax for color values. For compability with future CSS color functions, use this new syntax.

Regardless of your color values and syntax, always ensure your color choices meet WCAG minimum contrast ratios (4.5:1 for 16px and smaller, 3:1 for larger).

Additional reading:

[Smashing Magazine - A Guide To Modern CSS Colors](https://www.smashingmagazine.com/2021/11/guide-modern-css-colors/)

[rgb() - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgb)

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
.element {
  color: rgb(255 255 255 / .65);
  background-color: rgb(0 0 0 / .95);
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Media query placement

Place media queries as close to their relevant rule sets whenever possible. Don’t bundle them all in a separate stylesheet or at the end of the document. Doing so only makes it easier for people to miss them in the future.

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
.element { ... }
.element-avatar { ... }
.element-selected { ... }
@media (min-width: 480px) {
  .element { ... }
  .element-avatar { ... }
  .element-selected { ... }
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Shorthand notation

Limit shorthand declaration usage to instances where you must explicitly set all available values. Frequently overused shorthand properties include:

* padding
* margin
* font
* background
* border
* border-radius

Usually we don’t need to set all the values a shorthand property represents. For example, HTML headings only set top and bottom margin, so when necessary, only override those two values. A 0 value implies an override of either a browser default or previously specified value.

Excessive use of shorthand properties leads to sloppier code with unnecessary overrides and unintended side effects.

The Mozilla Developer Network has a great article on [shorthand properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties) for those unfamiliar with notation and behavior.

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Bad example
.element {
  margin: 0 0 10px;
  background: red;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}
```
```
// Good example
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Comments

Code is written and maintained by people. Ensure your code is descriptive, well commented, and approachable by others. Great code comments convey context or purpose. Do not simply reiterate a component or class name. Use the // syntax when writing CSS with preprocessors. When shipping CSS to production, remove all comments.

Be sure to write in complete sentences for larger comments and succinct phrases for general notes.

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Bad example
// Modal header
.modal-header {
  ...
}
```
```
// Good example
// Wrapping element for .modal-title and .modal-close
.modal-header {
  ...
}
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Class names

* Keep classes lowercase and use dashes (not underscores or camelCase). Dashes serve as natural breaks in related class (e.g., ```.btn``` and ```.btn--primary```).
* Avoid excessive and arbitrary shorthand notation. ```.btn``` is useful for button, but ```.s``` doesn’t mean anything.
* Use class names that make it easy to understand what styles are being applied.
* Keep classes as short and succinct as possible.
* Use meaningful names; use structural or purposeful names over presentational.
* Keep naming conventions consistent so that it's easier to internalize and understand class names. Use the [BEM naming](https://getbem.com/naming/) approach here.
* Use ```.js-*``` classes to denote behavior (as opposed to style), but keep these classes out of your CSS.

It’s also useful to apply many of these same rules when creating custom properties and preprocessor variable names.

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Bad example
.t { ... }
.red { ... }
.header { ... }
```
```
// Good example
.tweet { ... }
.important { ... }
.tweet-header { ... }
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Class names

Components should follow the [Block Element Modifier (BEM)](https://getbem.com/naming/) model in terms of structure.

**Block:** Encapsulates a standalone entity that is meaningful on its own. While blocks can be nested and interact with each other, semantically they remain equal; there is no precedence or hierarchy. Holistic entities without DOM representation (such as controllers or models) can be blocks as well. A block includes all of the base styles you want shared across every variation of a component. Minimal thematic styling should be applied to blocks, particularly when variations of a component include visual variations. Apply additional styles with modifiers rather than overriding base styles.

**Element:** An element is part of a component. Elements should work together with other elements and can have modifiers. Element styles should not override block styles - this often results in applying more styles directly to elements rather than having styles flow down from the parent level.

**Modifier:** A modifier is a variation that can be applied to the base component or to an element within the component. Modifiers shouldn't override block styles, they should add onto them.

{{< /column >}}

{{< column >}}
{{< code-html >}}
```
<!-- Bad -->
<div class="block--mod">...</div>
```
```
<!-- Good -->
<div class="block block--mod">...</div>
<div class="block block--size-big block--shadow-yes">...</div>
```
```
<!-- Example -->
<form class="form form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```
{{< /code-html >}}
{{< code-css >}}
```
.form { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Selectors

* Use classes over generic element tags for more explicit and reliable styling that isn’t dependent on your markup.
* Avoid using several attribute selectors (e.g., [class^="..."]) on commonly occuring components. Browser performance is known to be impacted by these.
* Keep selectors short and strive to limit the number of elements in each selector to three.
* Scope classes to the closest parent only when necessary (e.g., when not using prefixed classes).

Additional reading:

[Scope CSS classes with prefixes](https://markdotto.com/2012/02/16/scope-css-classes-with-prefixes/)

[Stop the cascade](https://markdotto.com/2012/03/02/stop-the-cascade/)

{{< /column >}}

{{< column >}}
{{< code-css >}}
```
// Bad example
span { ... }
.page-container #stream .stream-item .tweet .tweet-header .username { ... }
.avatar { ... }
```
```
// Good example
.avatar { ... }
.tweet-header .username { ... }
.tweet .avatar { ... }
```
{{< /code-css >}}
{{< /column >}}

{{< column >}}
### Organization

* Organize sections of code by component using a dedicated SCSS file per component.
* Develop a consistent commenting hierarchy.
* Use consistent white space to your advantage when separating sections of code for scanning larger documents.
* When using multiple CSS files, break them down by component instead of page. Pages can be rearranged and components moved.

{{< /column >}}

{{< column >}}
{{< /column >}}