## Primitive types

***Primitives are immutable***: they can't be altered. It is important not to confuse a primitive itself with a variable assigned a primitive value. The variable may be reassigned a new value, but the existing value can't be changed in the ways that objects, arrays, and functions can be altered.

In JavaScript, a primitive value is data that is not an object and has no methods. There are 7 primitive data types:
- string 
	- Example: `'hello world'`
- number 
	- Example: `123`
- bigint
	- This data type can represent numbers greater than 2<sup>53</sup>-1 which helps to perform operations on large numbers. The number is specified by writing ‘n’ at the end of the value
- boolean
	- Example: `true`
- undefined
	- The meaning of undefined is ‘value is not assigned’.
	- Example: `typeof(x) // Output: undefined`
- null
	- Example:
	  `let x = null;`
	  `console.log(x) // null`
- symbol
	- This data type is used to create objects which will always be unique. these objects can be created using `Symbol` constructor.
	- Example:
	  `let sym = Symbol("Hello");`
	  `console.log(typeof(sym)); // symbol`
	  `console.log(sym); // Symbol(Hello)`