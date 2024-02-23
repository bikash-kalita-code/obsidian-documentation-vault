Hyperlinks allow us to link documents to other documents or resources, link to specific parts of documents, or make apps available at a web address.

**Note: A URL can point to HTML files, text files, images, text documents, video and audio files, or anything else that lives on the Web. If the web browser doesn't know how to display or handle the file, it will ask you if you want to open the file (in which case the duty of opening or handling the file is passed to a suitable native app on the device) or download the file (in which case you can try to deal with it later on).**

## Anatomy of a link
A basic link is created by wrapping the text or other content inside an [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) element and using the [`href`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href) attribute, also known as a **Hypertext Reference**, or **target**, that contains the web address.
```html
<p>
  I'm creating a link to
  <a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>
```
### Block Level Links


