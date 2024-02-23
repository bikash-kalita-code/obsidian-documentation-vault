Example:
```js
const person = {  
  firstName: "John",  
  lastName : "Doe",  
  id       : 5566,  
  fullName : function() {  
    return this.firstName + " " + this.lastName;  
  }  
};
```

- In JavaScript, the `this` keyword refers to an **object**.
- The `this` keyword refers to different objects depending on how it is used:
	- In an object method, `this` refers to the **object**.
	- Alone, `this` refers to the **global object**.
	- In a **function**, `this` refers to the **global object**.
	- In a function, in strict mode, `this` is `undefined`.
	- In an event, `this` refers to the **element** that received the event.
	- Methods like `call()`, `apply()`, and `bind()` can refer `this` to **any object**.
- `this` is not a variable. It is a keyword. You cannot change the value of `this`.

### `this` in a Method
- When used in an object method, `this` refers to the **object**.
- In the example above, `this` refers to the **person** object.

### `this` Alone
- When used alone, `this` refers to the **global object**.
- Because `this` is running in the global scope.
- In a browser window the global object is `[object Window]`:
	- `let x = this;`
-  In **strict mode**, when used alone, `this` also refers to the **global object**:
	- `"use strict";`
	- `let x = this;

### `this` in a Function (Default)
- In a function, the **global object** is the default binding for `this`.
- In a browser window the global object is `[object Window]`:
```js
function myFunction() {  
  return this;  
}
```

### `this` in a Function (Strict)
- JavaScript **strict mode** does not allow default binding.
- So, when used in a function, in strict mode, `this` is `undefined`.
```js
"use strict";  
function myFunction() {  
  return this;  
}
```
