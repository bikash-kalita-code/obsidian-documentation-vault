Like HTML, CSS is not a programming language. It's not a markup language either. **CSS is a style sheet language.** CSS is what you use to selectively style HTML elements.

#### Anatomy of a CSS ruleset
![[CSS Ruleset.png]]
#### Modify multiple property values in one ruleset
```css
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}
```
#### Selecting Multiple Elements
```css
p,
li,
h1 {
  color: red;
}
```

### Different types of selectors
|Selector name|What does it select|Example|
|---|---|---|
|Element selector (sometimes called a tag or type selector)|All HTML elements of the specified type.|`p`  <br>selects `<p>`|
|ID selector|The element on the page with the specified ID. On a given HTML page, each id value should be unique.|`#my-id`  <br>selects `<p id="my-id">` or `<a id="my-id">`|
|Class selector|The element(s) on the page with the specified class. Multiple instances of the same class can appear on a page.|`.my-class`  <br>selects `<p class="my-class">` and `<a class="my-class">`|
|Attribute selector|The element(s) on the page with the specified attribute.|`img[src]`  <br>selects `<img src="myimage.png">` but not `<img>`|
|Pseudo-class selector|The specified element(s), but only when in the specified state. (For example, when a cursor hovers over a link.)|`a:hover`  <br>selects `<a>`, but only when the mouse pointer is hovering over the link.|

#### Fonts  and text
https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics#fonts_and_text

#### Comments
Anything in CSS between `/*` and `*/` is a **CSS comment**. The browser ignores comments as it renders the code.

### Box Model
Each box taking up space on your page has properties like:
- `padding`, the space around the content. In the example below, it is the space around the paragraph text.
- `border`, the solid line that is just outside the padding.
- `margin`, the space around the outside of the border.
![[css-box-model.png]]In this section we also use:
- `width` (of an element).
- `background-color`, the color behind an element's content and padding.
- `color`, the color of an element's content (usually text).
- `text-shadow` sets a drop shadow on the text inside an element.
- `display` sets the display mode of an element.


```css
body {
  width: 600px;
  margin: 0 auto;
  background-color: #ff9500;
  padding: 0 20px 20px 20px;
  border: 5px solid black;
}
```
There are several declarations for the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element. Let's go through these line-by-line:
- `width: 600px;` This forces the body to always be 600 pixels wide.
- `margin: 0 auto;` When you set two values on a property like `margin` or `padding`, the first value affects the element's top _and_ bottom side (setting it to `0` in this case); the second value affects the left _and_ right side. (Here, `auto` is a special value that divides the available horizontal space evenly between left and right). You can also use one, two, three, or four values, as documented in [Margin Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/margin#syntax).
- `background-color: #FF9500;` This sets the element's background color. This project uses a reddish orange for the body background color, as opposed to dark blue for the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element. (Feel free to experiment.)
- `padding: 0 20px 20px 20px;` This sets four values for padding. The goal is to put some space around the content. In this example, there is no padding on the top of the body, and 20 pixels on the right, bottom and left. The values set top, right, bottom, left, in that order. As with `margin`, you can use one, two, three, or four values, as documented in [Padding Syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/padding#syntax).
- `border: 5px solid black;` This sets values for the width, style and color of the border. In this case, it's a five-pixel–wide, solid black border, on all sides of the body.


```css
h1 {
  margin: 0;
  padding: 20px 0;
  color: #00539f;
  text-shadow: 3px 3px 1px black;
}
```
`text-shadow` applies a shadow to the text content of the element. Its four values are:
- The first pixel value sets the **horizontal offset** of the shadow from the text: how far it moves across.
- The second pixel value sets the **vertical offset** of the shadow from the text: how far it moves down.
- The third pixel value sets the **blur radius** of the shadow. A larger value produces a more fuzzy-looking shadow.
- The fourth value sets the base color of the shadow.

#### Centering the image
```css
img {
  display: block;
  margin: 0 auto;
}
```
We could use the `margin: 0 auto` trick again as we did for the body. But there are differences that require an additional setting to make the CSS work.
**The `<body>` is a block element, meaning it takes up space on the page. The margin applied to a block element will be respected by other elements on the page. In contrast, images are inline elements, for the auto margin trick to work on this image, we must give it block-level behavior using `display: block;`.**

