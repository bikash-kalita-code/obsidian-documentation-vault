### Sources
1. https://developer.mozilla.org/en-US/docs/Web/HTML

## Contents
1. [[What is HTML|What is HTML?]]
2. 

**NOTE**
- The convention and recommended practice is to write HTML tags in lowercase.
- Browsers, web servers, and programming languages do not handle spaces consistently. For example, if you use spaces in your filename, some systems may treat the filename as two filenames. Some servers will replace the spaces in your filenames with "%20" (the character code for spaces in URLs), resulting in all your links being broken. **It's better to separate words with hyphens, rather than underscores: `my-file.html` vs. `my_file.html`.**
	- The short answer is that you should use a hyphen for your file names. The Google search engine treats a hyphen as a word separator but does not regard an underscore that way. For these reasons, it is best to get into the habit of writing your folder and file names in lowercase with no spaces and with words separated by hyphens, at least until you know what you're doing. That way you'll bump into fewer problems down the road.
- The Windows file system tends to use backslashes, not forward slashes, e.g. `C:\Windows`. This doesn't matter in HTML — even if you are developing your website on Windows, you should still use forward slashes in your code.
- **The element:** The opening tag, the closing tag, and the content together comprise the element.
- Simple attribute values that don't contain [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII) whitespace (or any of the characters `"` `'` `` ` `` `=` `<` `>`) can remain unquoted, but it is recommended that you quote all attribute values, as it makes the code more consistent and understandable.
- Don't use heading elements to make text bigger or bold, because they are used for [accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/HTML#text_content) and [other reasons such as SEO](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#why_do_we_need_structure). Try to create a meaningful sequence of headings on your pages, without skipping levels.
