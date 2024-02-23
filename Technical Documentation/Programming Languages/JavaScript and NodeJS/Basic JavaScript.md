## Using JavaScript to change HTML Content
```html
<div id="demo1"></div>
<div id="demo2"></div>

<script>
	document.getElementById("demo1").innerHTML = "<h1>Hello Javascript 1</h1>";
	document.getElementById("demo2").innerText = "<h1>Hello Javascript 2</h1>";
</script>
```
## Using JavaScript to change HTML Attribute Values
```html
<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>

<img id="myImage" src="pic_bulboff.gif" style="width:100px">

<button onclick="document.getElementById('myImage').src='pic_bulboff.gif'">Turn off the light</button>
```
## Using JavaScript to change HTML Styles (CSS)
```html
<p id="demo">Hello World</p>
<button onclick='document.getElementById("demo").style.fontSize="24px"'>Click to increase text size</button>
```
## Using JS to hide HTML Elements
```html
<p id="demo">Hello World</p>
<button onclick='document.getElementById("demo").style.display="none"'>
Click here to hide 'Hello World' text
</button>
```
## Using JS to show HTML elements
```html
<p id="demo">Hello World</p>
<button onclick='document.getElementById("demo").style.display="none"'>
Click here to hide 'Hello World' text</button>

<button onclick="document.getElementById('demo').style.display='block'">Click here to show 'Hello World' text</button>
```

## `<script>` tag
In HTML, JavaScript code is inserted between `<script>` and `</script>` tags.

## JavaScript in `<head>` or `<body>`
- You can place any number of scripts in an HTML document.
 - Scripts can be placed in the `<body>`, or in the `<head>` section of an HTML page, or in both.
### JavaScript in `<head>`
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script>
        function myFunction() {
            document.getElementById("demo").innerHTML = "Paragraph changed";
        }
    </script>
</head>

<body>
    <h2>Demo JS in Head</h2>
    <p id="demo">
        A paragraph
    </p>
    <button type="button" onclick="myFunction()">Try it</button>
</body>

</html>
```
### JavaScript in `<body>`
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <h2>Demo JS in Body</h2>

    <p id="demo">A paragraph</p>

    <button type="button" onclick="myFunction()">Try it</button>

    <script>

        function myFunction() {
            document.getElementById("demo").innerHTML = "Paragraph changed.";
        }
    </script>
</body>

</html>
```
**NOTE:** **Placing scripts at the bottom of the `<body>` element improves the display speed, because script interpretation slows down the display.**

### External JavaScript
External scripts are practical when the same code is used in many different web pages.
To use an external script, put the name of the script file in the `src` (source) attribute of a `<script>` tag:
You can place an external script reference in `<head>` or `<body>` as you like.
The script will behave as if it was located exactly where the `<script>` tag is located.
External scripts cannot contain `<script>` tags.
Inside, `myScript.js`:
```js
function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
}
```
Inside, `index.html`:
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <h2>Demo JS in Body</h2>

    <p id="demo">A paragraph in Test6</p>

    <button type="button" onclick="myFunction()">Try it</button>

    <script src="myScript.js"></script>
</body>

</html>
```
Placing scripts in external files has some advantages:
- It separates HTML and code
- It makes HTML and JavaScript easier to read and maintain
- Cached JavaScript files can speed up page loads

To add several script files to one page  - use several script tags:
```html
<script src="myScript1.js"></script>
<script src="myScript2.js"></script>
```

### External References
An external script can be referenced in 3 different ways:
- With a full URL (a full web address)
- With a file path (like /js/)
- Without any path
This example uses a **full URL** to link to `myScript.js`:
```html
<script src="https://www.w3schools.com/js/myScript.js"></script>
```
This example uses a **file path** to link to myScript.js:
```html
<script src="/js/myScript.js"></script>
```
This example uses no path to link to myScript.js:
```html
<script src="myScript.js"></script>
```
## JavaScript Output
### JavaScript Display Possibilities
JavaScript can "display" data in different ways:
- Writing into an HTML element, using `innerHTML`.
- Writing into the HTML output using `document.write()`.
- Writing into an alert box, using `window.alert()`.
- Writing into the browser console, using `console.log()`.
### Using innerHTML
- To access an HTML element, JavaScript can use the `document.getElementById(id)` method.
```html
<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<p id="demo"></p>

<script>
	document.getElementById("demo").innerHTML = 5 + 6;
</script>
```
### Using document.write()
```html
<h1>My First Web Page</h1>
<p>My First Paragraph</p>

<script>
	document.write(5 + 6)
</script>
```
**NOTE:** Using document.write() after an HTML document is loaded, will **delete all existing HTML**:
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>
<p>My first paragraph.</p>

<button type="button" onclick="document.write(5 + 6)">Try it</button>

</body>
</html>
```
**NOTE:** The document.write() method should only be used for testing.
### Using window.alert()
You can use an alert box to display data:
```html
<h1>My First Web Page</h1>  
<p>My first paragraph.</p>  
  
<script>  
window.alert(5 + 6);  
</script>
```
You can skip the `window` keyword.

In JavaScript, the window object is the global scope object. This means that variables, properties, and methods by default belong to the window object. This also means that specifying the `window` keyword is optional.
### Using console.log()
For debugging purposes, you can call the `console.log()` method in the browser to display data.
```html
<script>
console.log(5 + 6);
</script>
```
### JavaScript Print
JavaScript does not have any print object or print methods.
You cannot access output devices from JavaScript.
The only exception is that you can call the `window.print()` method in the browser to print the content of the current window.
```html
<!DOCTYPE html>
<html>
<body>

<button onclick="window.print()">Print this page</button>

</body>
</html>
```
## JavaScript Statements
- When separated by semicolons, multiple statements on one line are allowed:
`a = 5; b = 6; c = a + b;`
- JavaScript statements can be grouped together in code blocks, inside curly brackets {...}.
