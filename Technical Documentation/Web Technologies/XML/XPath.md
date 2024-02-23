## What is XPath?
- XPath is a major element in the XSLT standard.
- XPath can be used to navigate through elements and attributes in an XML document.
- XPath stands for XML Path Language
- XPath uses "path like" syntax to identify and navigate nodes in an XML document
- XPath contains over 200 built-in functions
- XPath is a major element in the XSLT standard
- XPath is a W3C recommendation
![[XPath.excalidraw]]

### XPath Path Expressions
- XPath uses path expressions to select nodes or node-sets in an XML document.

### XPath Standard Functions
- XPath includes over 200 built-in functions.
- There are functions for string values, numeric values, booleans, date and time comparison, node manipulation, sequence manipulation, and much more.
- Today XPath expressions can also be used in JavaScript, Java, XML Schema, PHP, Python, C and C++, and lots of other languages.

### XPath is Used in XSLT
- XPath is a major element in the XSLT standard.
- With XPath knowledge you will be able to take great advantage of your XSLT knowledge.

### XPath is a W3C Recommendation
- XPath 1.0 became a W3C Recommendation on November 16, 1999.
- XPath 2.0 became a W3C Recommendation on January 23, 2007.
- XPath 3.0 became a W3C Recommendation on April 8, 2014.

## Nodes
### XPath Terminology
#### Nodes
In XPath, there are seven kinds of nodes: element, attribute, text, namespace, processing-instruction, comment, and root nodes.
XML documents are treated as trees of nodes. The topmost element of the tree is called the root element.
Look at the following XML document:
```xml
<?xml version="1.0" encoding="UTF-8"?>  
  
<bookstore>  
  <book>  
    <title lang="en">Harry Potter</title>  
    <author>J K. Rowling</author>  
    <year>2005</year>  
    <price>29.99</price>  
  </book>  
</bookstore>
```
Example of nodes in the XML document above:
```xml
<bookstore> (root element node)  
  
<author>J K. Rowling</author> (element node)  
  
lang="en" (attribute node)
```
#### Atomic values
Atomic values are nodes with no children or parent.
Example of atomic values:
```text
J K. Rowling  
  
"en"
```
#### Items
Items are atomic values or nodes.
### Relationship of Nodes
#### Parent
Each element and attribute has one parent.
In the following example; the book element is the parent of the title, author, year, and price:
```xml
<book>  
  <title>Harry Potter</title>  
  <author>J K. Rowling</author>  
  <year>2005</year>  
  <price>29.99</price>  
</book>
```
#### Children
Element nodes may have zero, one or more children.
In the following example; the title, author, year, and price elements are all children of the book element:
```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>
```
#### Siblings
Nodes that have the same parent.
In the above example; the title, author, year, and price elements are all siblings
#### Ancestors
A node's parent, parent's parent, etc.
In the following example; the ancestors of the title element are the book element and the bookstore element:
```xml
<bookstore>  
  
<book>  
  <title>Harry Potter</title>  
  <author>J K. Rowling</author>  
  <year>2005</year>  
  <price>29.99</price>  
</book>  
  
</bookstore>
```
#### Descendants
A node's children, children's children, etc.
In the above example; descendants of the bookstore element are the book, title, author, year, and price elements

## XPath Syntax
XPath uses path expressions to select nodes or node-sets in an XML document. The node is selected by following a path or steps.
### The XML Example Document
```xml
<?xml version="1.0" encoding="UTF-8"?>

<bookstore>

<book>
  <title lang="en">Harry Potter</title>
  <price>29.99</price>
</book>

<book>
  <title lang="en">Learning XML</title>
  <price>39.95</price>
</book>

</bookstore>
```
### Selecting Nodes
- XPath uses path expressions to select nodes in an XML document. The node is selected by following a path or steps.
- The most useful path expressions are listed below:

| Expression | Description |
| - | - |
| `nodename` | Selects all nodes with the name "nodename"|
| `/` | Selects from the root node|
| `//` | Selects nodes in the document from the current node that match the selection no matter where they are|
| `.` | Selects the current node|
| `..` | Selects the parent of the current node|
| `@` | Selects attributes|

In the table below we have listed some path expressions and the result of the expressions:

| Path Expression | Result |
| - | - |
| `bookstore` | Selects all nodes with the name "bookstore" |
| `/bookstore` | Selects the root element bookstore (Note: If the path starts with a slash ( / ) it always represents an absolute path to an element!) |
| `bookstore/book` | Selects all book elements that are children of bookstore |
| `//book` | Selects all book elements no matter where they are in the document |
| `bookstore//book` | Selects all book elements that are descendant of the bookstore element, no matter where they are under the bookstore element |
| `//@lang` | Selects all attributes that are named lang |

### Predicates
- Predicates are used to find a specific node or a node that contains a specific value. Predicates are always embedded in square brackets. 
- In the table below we have listed some path expressions with predicates and the result of the expressions:

| Path Expression | Result |
| - | - |
| `/bookstore/book[1]` | <ul><li>Selects the first book element that is the child of the bookstore element.</li><li>Note: In IE 5,6,7,8,9 first node is[0], but according to W3C, it is [1]. To solve this problem in IE, set the SelectionLanguage to XPath:<li>In JavaScript: xml.setProperty("SelectionLanguage","XPath");</li></li></ul> |
| `/bookstore/book[last()]` | Selects the last book element that is the child of the bookstore element |
| `/bookstore/book[last()-1]` | Selects the last but one book element that is the child of the bookstore element |
| `/bookstore/book[position()<3]` | Selects the first two book elements that are children of the bookstore element |
| `//title[@lang]` | Selects all the title elements that have an attribute named lang |
| `//title[@lang='en']` | Selects all the title elements that have a "lang" attribute with a value of "en" |
| `/bookstore/book[price>35.00]` | Selects all the book elements of the bookstore element that have a price element with a value greater than 35.00 |
| `/bookstore/book[price>35.00]/title` | Selects all the title elements of the book elements of the bookstore element that have a price element with a value greater than 35.00 |
