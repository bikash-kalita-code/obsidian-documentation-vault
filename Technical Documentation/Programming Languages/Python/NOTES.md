1. In Python, variables are created when you assign a value to it.
	1. Python has no command for declaring a variable.
2. Since Python will ignore string literals that are not assigned to a variable, you can add a multiline string (triple quotes) in your code, and place your comment inside it:
	1. As long as the string is not assigned to a variable, Python will read the code, but then ignore it, and you have made a multiline comment.
```python
"""  
This is a comment  
written in  
more than just one line  
"""  
print("Hello, World!")
```
3. Python also has many built-in functions that return a boolean value, like the `isinstance()` function, which can be used to determine if an object is of a certain data type:
```python
x = 200  
print(isinstance(x, int))
```
4. **There are four collection data types in the Python programming language**
	1. **List**
	2. **Tuple**
	3. **Set**
	4. **Dictionary**