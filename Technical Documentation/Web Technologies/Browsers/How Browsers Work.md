1. Browser handle network, content display, data storage and content security all in a very interactive way
2. Their technical requirements are the same as those of AAA games
3. They ley web creators building any type of content

- Browsers are very complex piece of software that have drastically evolved since the 90's.
- From rendering simple text to executing fully fledged applications.
- Because the web is all about requesting documents stored on the internet, they are able to handle network connections.
	- Historically that was done using the HTTP protocol to perform simple CRUD (Create, Read, Update, Delete) operations on documents
	- But, nowadays
		- they can also create bidirectional communication channels with a server or they can even create a peer-to-peer connection with another browser
		- they have to be able to understand, render and/or execute different languages (PDF, WebAssembly, MathML, HTML, CSS, JavaScript, SVG)
		- they also have to be able to render fonts, images, audio, and videos
		- everything you see in the browser must be interactive
		- they can store data either by caching content or providing various storage mechanisms (Service Workers + Cache API, Local Storage, Session Storage, IndexedDB)
		- browsers must be able to manage data encryption and to sandbox every set of contents in order to prevent malicious code to access other contents, or worse your computer

#### Rendering multiple documents to display them to you in an interactive way
1. **Rendering**
	1. The browser **requests** all necessary documents
2. **Parsing**
	1. All documents will be parsed and turned into machine-friendly representations
		1. DOM trees, Style trees, Rendering trees, Display lists are different ways for browser to represent documents
3. **Layout**
	1. The intermediate representations are used to compute the whole page layout
4. **Painting**
	1. The browser finally paints each element of the layout on the screen