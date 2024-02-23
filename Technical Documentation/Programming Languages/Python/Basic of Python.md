
## NOTE
1. Common and rarely used less important concepts are omitted
## Variables
- Variables are containers for storing data values.
- Python has no command for declaring a variable. A variable is created the moment you first assign a value to it.
- Variables do not need to be declared with any particular _type_, and can even change type after they have been set.
- If you want to specify the data type of a variable, this can be done with casting.
- You can get the data type of a variable with the `type()` function.
- Variable names are case-sensitive.
```python
# This will create two different variables
a = 4  
A = "Sally"  
#A will not overwrite a
```
- Python allows you to assign values to multiple variables in one line:
```python
x, y, z = "Orange", "Banana", "Cherry"
```
- And you can assign the _same_ value to multiple variables in one line:
```python
x = y = z = "Orange"
```
- If you have a collection of values in a list, tuple etc. Python allows you to extract the values into variables. This is called **_unpacking_**.
```python
fruits = ["apple", "banana", "cherry"]  
x, y, z = fruits  
print(x)  
print(y)  
print(z)
```
- If you create a variable with the same name inside a function, this variable will be local, and can only be used inside the function. The global variable with the same name will remain as it was, global and with the original value.
```python
x = "awesome"
def myfunc():
    x = "fantastic"
    print("Inside function : " + x)
myfunc()
print("Outside function : " + x)

# Output
# Inside function : fantastic
# Outside function : awesome
```
- The **global** keyword
	- Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function. To create a global variable inside a function, you can use the `global` keyword.
	- If you use the `global` keyword, the variable belongs to the global scope:
	```python
def fun():
    global y
    y = "hello"
    print("Inside function : " + y)
fun()
print("Outside function : " + y)

# Output
# Inside function : hello
# Outside function: hello
```
	- Also, use the `global` keyword if you want to change a global variable inside a function.
	```python
z = "one"
def funz():
    global z
    z = "two"
funz()
print(z)
# Output
# two
```

## Data Types
| Category | Data Type | Example |
| - | - | - |
| Text Type | `str` | `x = "Hello World"` |
| Numeric Types | <ul><li>`int`</li><li>`float`</li><li>`complex`</li></ul> |  <ul><li>`x = 20`</li><li>`x = 20.5`</li><li>`x = 1j`</li></ul> |
| Sequence Types | <ul><li>list</li><li>tuple</li><li>range</li></ul> |  <ul><li>`x = ["apple", "banana", "cherry"]`</li><li>`x = ("apple", "banana", "cherry")`</li><li>`x = range(6)`</li></ul> |
| Mapping Type | dict | `x = {"name": "John", "age": 36}` |
| Set Types | <ul><li>set</li><li>frozenset</li></ul> | <ul><li>`x = {"apple", "banana", "cherry"}`</li><li>`x = frozenset({"apple", "banana", "cherry"})`</li></ul> |
| Boolean Type | bool | `x = True` |
| Binary Types | <ul><li>bytes</li><li>bytearray</li><li>memoryview</li></ul> |  <ul><li>`x = b"Hello"`</li><li>`x = bytearray(5)`</li><li>`x = memoryview(bytes(5))`</li></ul> |
| None Type | NoneType | `x = None` |

- If you want to specify the Data Type, you can use the following constructor functions:

| Data Type | Example |
| - | - |
| `str` | `x = str("Hello World")` |
| `int` | `x = int(20)` |
| `float` | `x = float(20.5)` |
| `complex` | `x = complex(1j)` |
| `list` | `x = list(("apple", "banana", "cherry"))` |
| `tuple` | `x = tuple(("apple", "banana", "cherry"))` |
| `range` | `x = range(6)` |
| `dict` | `x = dict(name="John", age=36)` |
| `set` | `x = set(("apple", "banana", "cherry"))` |
| `frozenset` | `x = frozenset(("apple", "banana", "cherry"))` |
| `bool` | `x = bool(5)` |
| `bytes` | `x = bytes(5)` |
| `bytearray` | `x = bytearray(5)` |
| `memoryview` | `x = memoryview(bytes(5))` |

## Strings
- You can assign a multiline string to a variable by using three quotes
- You can use `three single quotes` or `three double quotes`
```python
a = """Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua."""
b = '''Lorem ipsum dolor sit amet,  
consectetur adipiscing elit,  
sed do eiusmod tempor incididunt  
ut labore et dolore magna aliqua.'''
print(a)
print(b)
```
- **Strings are Arrays**
	- Like many other popular programming languages, strings in Python are arrays of bytes representing unicode characters.
	- However, Python does not have a character data type, a single character is simply a string with a length of 1.
	```python
a = "Hello, World!"  
print(a[1])
```
	- Looping Through a String
		```python
		for x in "banana":
			print(x)
```
	- To get the length of a string, use the `len()` function.
	- To check if a certain phrase or character is present in a string, we can use the keyword `in`.
		```python
		txt = "The best things in life are free!"  
		print("free" in txt)
```
	- Use it in an `if` statement:
		```python
		txt = "The best things in life are free!"  
		if "free" in txt:  
			print("Yes, 'free' is present.")
```
		```python
		txt = "The best things in life are free!"  
		if "expensive" not in txt:  
			print("No, 'expensive' is NOT present.")
```
- **Slicing**
	- Specify the start index and the end index, separated by a colon, to return a part of the string.
	```python
	# Get the characters from position 2 to position 5 (not included):
	b = "Hello, World!"  
	print(b[2:5])
```
	- Slicing from the start
	```python
	b = "Hello, World!"  
	print(b[:5])
```
	- Slicing to the end
	```python
	b = "Hello, World!"  
	print(b[2:])
```
	- **Negative indexing**
		- Use negative indexes to start the slice from the end of the string:
		```python
		b = "Hello, World!"  
		print(b[-5:-2])
		# Output
		# orl
```
- **Modify Strings**
	- The `upper()` method returns the string in upper case
	- The `lower()` method returns the string in lower case
	- The `strip()` method removes any whitespace from the beginning or the end
	- The `replace()` method replaces a string with another string
	- The `split()` method returns a list where the text between the specified separator becomes the list items.
- **Concatenate Strings**
	- To concatenate, or combine, two strings you can use the + operator.
- **Format Strings**
	- The `format()` method takes the passed arguments, formats them, and places them in the string where the placeholders `{}` are:
	```python
	quantity = 3  
	itemno = 567  
	price = 49.95  
	myorder = "I want {} pieces of item {} for {} dollars."  
	print(myorder.format(quantity, itemno, price))
```
	- You can use index numbers `{0}` to be sure the arguments are placed in the correct placeholders:
	```python
	quantity = 3  
	itemno = 567  
	price = 49.95  
	myorder = "I want to pay {2} dollars for {0} pieces of item {1}."  
	print(myorder.format(quantity, itemno, price))
```
- **Escape Character**
	- An escape character is a backslash `\` followed by the character you want to insert.
	```python
	txt = "We are the so-called \"Vikings\" from the north."
```
- **String Methods**

| Method | Description |
| - | - |
| `capitalize()` | `Converts the first character to upper case` |
| `casefold()` | `Converts string into lower case` |
| `center()` | `Returns a centered string` |
| `count()` | `Returns the number of times a specified value occurs in a string` |
| `encode()` | `Returns an encoded version of the string` |
| `endswith()` | `Returns true if the string ends with the specified value` |
| `expandtabs()` | `Sets the tab size of the string` |
| `find()` | `Searches the string for a specified value and returns the position of where it was found` |
| `format()` | `Formats specified values in a string` |
| `format_map()` | `Formats specified values in a string` |
| `index()` | `Searches the string for a specified value and returns the position of where it was found` |
| `isalnum()` | `Returns True if all characters in the string are alphanumeric` |
| `isalpha()` | `Returns True if all characters in the string are in the alphabet` |
| `isascii()` | `Returns True if all characters in the string are ascii characters` |
| `isdecimal()` | `Returns True if all characters in the string are decimals` |
| `isdigit()` | `Returns True if all characters in the string are digits` |
| `isidentifier()` | `Returns True if the string is an identifier` |
| `islower()` | `Returns True if all characters in the string are lower case` |
| `isnumeric()` | `Returns True if all characters in the string are numeric` |
| `isprintable()` | `Returns True if all characters in the string are printable` |
| `isspace()` | `Returns True if all characters in the string are whitespaces` |
| `istitle()` | `Returns True if the string follows the rules of a title` |
| `isupper()` | `Returns True if all characters in the string are upper case` |
| `join()` | `Joins the elements of an iterable to the end of the string` |
| `ljust()` | `Returns a left justified version of the string` |
| `lower()` | `Converts a string into lower case` |
| `lstrip()` | `Returns a left trim version of the string` |
| `maketrans()` | `Returns a translation table to be used in translations` |
| `partition()` | `Returns a tuple where the string is parted into three parts` |
| `replace()` | `Returns a string where a specified value is replaced with a specified value` |
| `rfind()` | `Searches the string for a specified value and returns the last position of where it was found` |
| `rindex()` | `Searches the string for a specified value and returns the last position of where it was found` |
| `rjust()` | `Returns a right justified version of the string` |
| `rpartition()` | `Returns a tuple where the string is parted into three parts` |
| `rsplit()` | `Splits the string at the specified separator, and returns a list` |
| `rstrip()` | `Returns a right trim version of the string` |
| `split()` | `Splits the string at the specified separator, and returns a list` |
| `splitlines()` | `Splits the string at line breaks and returns a list` |
| `startswith()` | `Returns true if the string starts with the specified value` |
| `strip()` | `Returns a trimmed version of the string` |
| `swapcase()` | `Swaps cases, lower case becomes upper case and vice versa` |
| `title()` | `Converts the first character of each word to upper case` |
| `translate()` | `Returns a translated string` |
| `upper()` | `Converts a string into upper case` |
| `zfill()` | `Fills the string with a specified number of 0 values at the beginning` |

## Operators
- **Arithmetic operators**
	- +
	- -
	- *
	- /
	- %
	- ** : Exponentiation
	- // : Floor division
- **Assignment operators**
	- =
	- +=
	- -=
	- *=
	- /=
	- %=
	- //=
	- \*\*=
	- &=
	- |=
	- ^=
	- >>=
	- <<=
- **Comparison operators**
	- ==
	- !=
	- >
	- <
	- >=
	- <=
- **Logical operators**
	- and
	- or
	- not
- **Identity operators**
	- **Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location**
		- **is** : Returns True if both variables are the same object
		- **is not** : Returns True if both variables are not the same object
		```python
		x = ["apple", "banana"]
		y = ["apple", "banana"]
		z = x
		
		print(x is z)
		
		# returns True because z is the same object as x
		
		print(x is y)
		
		# returns False because x is not the same object as y, even if they have the same content
		
		print(x == y)
		
		# to demonstrate the difference betweeen "is" and "==": this comparison returns True because x is equal to y

		# Output
		# True
		# False
		# True
```
		```python
		x = ["apple", "banana"]
		y = ["apple", "banana"]
		z = x
		
		print(x is not z)
		
		# returns False because z is the same object as x
		
		print(x is not y)
		
		# returns True because x is not the same object as y, even if they have the same content
		
		print(x != y)
		
		# to demonstrate the difference betweeen "is not" and "!=": this comparison returns False because x is equal to y

		# Output
		# False
		# True
		# False
```
- **Membership operators**
	- Membership operators are used to test if a sequence is presented in an object
		- **in** : Returns True if a sequence with the specified value is present in the object
		- **not in** : Returns True if a sequence with the specified value is not present in the object
		```python
	# returns True because a sequence with the value "banana" is in the list
	
	print("pineapple" not in x)
	
	# returns True because a sequence with the value "pineapple" is not in the list
```
- **Bitwise operators**
	- **&** : `x & y`
	- **|** : `x | y`
	- **^** : `x ^ y`
	- **~** : `x ~ y`
	- **<<** :  `x << y`
	- **>>** : `x >> y`

## Lists
- `thislist = ["apple", "banana", "cherry"]`
- List items are ordered, changeable, and allow duplicate values.
- To determine how many items a list has, use the `len()` function
- List items can be of any data type
- From Python's perspective, lists are defined as objects with the data type 'list'
- It is also possible to use the list() constructor when creating a new list
	- `thislist = list(("apple", "banana", "cherry")) # note the double round-brackets`
- To change the value of items within a specific range, define a list with the new values, and refer to the range of index numbers where you want to insert the new values:
	```python
	thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]  
	thislist[1:3] = ["blackcurrant", "watermelon"]  
	print(thislist)
	# Output
	# ['apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango']
```
- If you insert _more_ items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
	```python
	thislist = ["apple", "banana", "cherry"]  
	thislist[1:2] = ["blackcurrant", "watermelon"]  
	print(thislist)
	# Output
	# ['apple', 'blackcurrant', 'watermelon', 'cherry']
```
- **Note:** The length of the list will change when the number of items inserted does not match the number of items replaced.
- If you insert _less_ items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
	```python
	thislist = ["apple", "banana", "cherry"]  
	thislist[1:3] = ["watermelon"]  
	print(thislist)
	# Output
	# ['apple', 'watermelon']
```
- To insert a new list item, without replacing any of the existing values, we can use the `insert()` method.
	```python
	thislist = ["apple", "banana", "cherry"]  
	thislist.insert(2, "watermelon")  
	print(thislist)
	# Output
	# ['apple', 'banana', 'watermelon', 'cherry']
```
- **Add List Items**
	- To add an item to the end of the list, use the append() method
	- To insert a list item at a specified index, use the `insert()` method.
	- To append elements from _another list_ to the current list, use the `extend()` method
	- The `extend()` method does not have to append _lists_, you can add any iterable object (tuples, sets, dictionaries etc.)
	```python
	lst1 = ["apple", "ball", "cat"]
	lst1.append("dog")
	print(lst1) # ['apple', 'ball', 'cat', 'dog']
	lst1.insert(1, "aeroplane")
	print(lst1) # ['apple', 'aeroplane', 'ball', 'cat', 'dog']
	lst2 = ["elephant", "fish", "grape"]
	lst1.extend(lst2)
	print(lst1) # ['apple', 'aeroplane', 'ball', 'cat', 'dog', 'elephant', 'fish', 'grape']
	lst3 = ("hat", "ice cream", "jacket")
	lst1.extend(lst3)
	print(lst1) # ['apple', 'aeroplane', 'ball', 'cat', 'dog', 'elephant', 'fish', 'grape', 'hat', 'ice cream', 'jacket']
```
- **Remove Specified Items**
	- The `remove()` method removes the specified item.
		- If there are more than one item with the specified value, the `remove()` method removes the first occurrence
	- The `pop()` method removes the specified index
		- If you do not specify the index, the `pop()` method removes the last item
	- The `del` keyword also removes the specified index
	- The `del` keyword can also delete the list completely
	- The `clear()` method empties the list
```python
thislist = ["apple", "banana", "cherry", "banana", "kiwi"]  
thislist.remove("banana")  
print(thislist) # ['apple', 'cherry', 'banana', 'kiwi']
thislist.pop(2) # returns 'banana'
print(thislist) # ['apple', 'cherry', 'kiwi']
thislist.pop()
print(thislist) # ['apple', 'cherry']
thislist.extend(('mango', 'guava', 'papaya'))
print(thislist) # ['apple', 'cherry', 'mango', 'guava', 'papaya']
del thislist[0]
print(thislist) # ['cherry', 'mango', 'guava', 'papaya']
del thislist
print(thislist) # NameError: name 'thislist' is not defined
thislist = ['apple', 'banana', 'cherry']
thislist.clear()
print(thislist) # []
```
- **Loop Lists**
	```python
	thislist = ["apple", "banana", "cherry"]  
	for x in thislist:  
	  print(x)
```
	- Use the `range()` and `len()` functions to create a suitable iterable.
	```python
	thislist = ["apple", "banana", "cherry"]  
	for i in range(len(thislist)):  
	  print(thislist[i])
```
	- loop through the list items by using a `while` loop
	```python
	thislist = ["apple", "banana", "cherry"]  
	i = 0  
	while i < len(thislist):  
	  print(thislist[i])  
	  i = i + 1
```
	- **Looping Using List Comprehension** : List Comprehension offers the shortest syntax for looping through lists
		```python
		thislist = ["apple", "banana", "cherry"]  
		[print(x) for x in thislist]
```
- **List Comprehension**
	- List comprehension offers a shorter syntax when you want to create a new list based on the values of an existing list
	```python
	# Without using List Comprehension
	fruits = ["apple", "banana", "cherry", "kiwi", "mango"]  
	newlist = []  
	  
	for x in fruits:  
	  if "a" in x:  
	    newlist.append(x)  
	  
	print(newlist)

	# Using List Comprehension
	fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
	newlist = [x for x in fruits if 'a' in x]
	print(newlist) # ['apple', 'banana', 'mango']
```
	- **SYNTAX**
		- `newlist = [expression for item in iterable if condition == True]`
		- The return value is a new list, leaving the old list unchanged
		- The _condition_ is optional and can be omitted
			- `newlist = [x for x in fruits]`
		- The _iterable_ can be any iterable object, like a list, tuple, set etc
		- The _expression_ is the current item in the iteration, but it is also the outcome, which you can manipulate before it ends up like a list item in the new list
		- `newlist = [x if x != "banana" else "orange" for x in fruits]`
- **Sort Lists**
	- List objects have a `sort()` method that will sort the list alphanumerically, ascending, by default:
		- `thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]`  `thislist.sort()`
	- To sort descending, use the keyword argument `reverse = True`
		- `thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]`
		  `thislist.sort(reverse = True)`
	- **Customize Sort Function**
		- customize your own function by using the keyword argument `key = _function_`
			```python
			def myfunc(n):  
			  return abs(n - 50)  
			  
			thislist = [100, 50, 65, 82, 23]  
			thislist.sort(key = myfunc)  
			print(thislist)
```
	- **Case Insensitive Sort**
		- By default the `sort()` method is case sensitive, resulting in all capital letters being sorted before lower case letters
		- So if you want a case-insensitive sort function, use `str.lower` as a key function
			```python
			thislist = ["banana", "Orange", "Kiwi", "cherry"]  
			thislist.sort(key = str.lower)  
			print(thislist)
```
		- The `reverse()` method reverses the current sorting order of the elements
			```python
			thislist = ["banana", "Orange", "Kiwi", "cherry"]  
			thislist.reverse()  
			print(thislist)
```
- **Copy a List**
	- You cannot copy a list simply by typing `list2 = list1`, because: `list2` will only be a _reference_ to `list1`, and changes made in `list1` will automatically also be made in `list2`.
	- There are ways to make a copy, one way is to use the built-in List method `copy()`
		```python
		thislist = ["apple", "banana", "cherry"]  
		mylist = thislist.copy()  
		print(mylist)
```
	- Another way to make a copy is to use the built-in method `list()`
		```python
		thislist = ["apple", "banana", "cherry"]  
		mylist = list(thislist)  
		print(mylist)
```
- **Join Lists**
	- **Join Two Lists**
		- One of the easiest ways are by using the `+` operator.
		```python
		list1 = ["a", "b", "c"]  
		list2 = [1, 2, 3]  
		  
		list3 = list1 + list2  
		print(list3)
```
		- Another way to join two lists is by appending all the items from list2 into list1, one by one
		```python
		list1 = ["a", "b" , "c"]  
		list2 = [1, 2, 3]  
		  
		for x in list2:  
		  list1.append(x)  
		  
		print(list1)
```
		- Or you can use the `extend()` method, where the purpose is to add elements from one list to another list
		```python
		list1 = ["a", "b" , "c"]  
		list2 = [1, 2, 3]  
		  
		list1.extend(list2)  
		print(list1)
```
- **List Methods**

| Method | Description |
| - | - |
| `append()` | Adds an element at the end of the list |
| `clear()` | Removes all the elements from the list |
| `copy()` | Returns a copy of the list |
| `count()` | Returns the number of elements with the specified value |
| `extend()` | Add the elements of a list (or any iterable), to the end of the current list |
| `index()` | Returns the index of the first element with the specified value |
| `insert()` | Adds an element at the specified position |
| `pop()` | Removes the element at the specified position |
| `remove()` | Removes the item with the specified value |
| `reverse()` | Reverses the order of the list |
| `sort()` | Sorts the list |

## Tuples
- Tuples are used to store multiple items in a single variable.
- A tuple is a collection which is ordered and **unchangeable**.
- Tuples are written with round brackets.
```python
thistuple = ("apple", "banana", "cherry")  
print(thistuple)
```
- Tuple items are **ordered, unchangeable, and allow duplicate values**
- To determine how many items a tuple has, use the `len()` function
- **To create a tuple with only one item, you have to add a comma after the item, otherwise Python will not recognize it as a tuple.**
```python
t1 = ("hello")
t2 = ("hello",)
print(t1) # hello
print(t2) # ('hello',)
print(type(t1)) # <class 'str'>
print(type(t2)) # <class 'tuple'>
```
- Tuple items can be of any data type
- A tuple can contain different data types
- Type: `<class 'tuple'>`
- It is also possible to use the `tuple()` constructor to make a tuple
```python
# using the tuple() method to make a tuple
thistuple = tuple(("apple", "banana", "cherry")) # note the double round-brackets  
print(thistuple)
```
- You can access tuple items by referring to the index number, inside square brackets
```python
thistuple = ("apple", "banana", "cherry")  
print(thistuple[1])
```
- Negative indexing
	```python
	thistuple = ("apple", "banana", "cherry")  
	print(thistuple[-1])
```
```python
	thistuple = ("apple", "banana", "cherry", "orange", "kiwi", "melon", "mango")  
	print(thistuple[2:5])
```
- **Access Tuples** : Same as for Lists
- Tuples are unchangeable, meaning that you cannot change, add, or remove items once the tuple is created
	- **But there are some workarounds**
	- You can convert the tuple into a list, change the list, and convert the list back into a tuple
	```python
	x = ("apple", "banana", "cherry")  
	y = list(x)  
	y[1] = "kiwi"  
	x = tuple(y)  
	  
	print(x) # ('apple', 'kiwi', 'cherry')
```
- Since tuples are immutable, they do not have a built-in `append()` method, but there are other ways to add items to a tuple:
	- **Convert into a list**: Just like the workaround for _changing_ a tuple, you can convert it into a list, add your item(s), and convert it back into a tuple
	```python
	thistuple = ("apple", "banana", "cherry")  
	y = list(thistuple)  
	y.append("orange")  
	thistuple = tuple(y)
```
	- **Add tuple to a tuple**. You are allowed to add tuples to tuples, so if you want to add one item, (or many), create a new tuple with the item(s), and add it to the existing tuple
	```python
	thistuple = ("apple", "banana", "cherry")  
	y = ("orange",)  
	thistuple += y  
	  
	print(thistuple)
```
	- Tuples are **unchangeable**, so you cannot remove items from it, but you can use the same workaround as we used for changing and adding tuple items
		- Convert the tuple into a list, remove the element, and convert it back into a tuple
		```python
		thistuple = ("apple", "banana", "cherry")  
		y = list(thistuple)  
		y.remove("apple")  
		thistuple = tuple(y)
```
		- Or you can delete the tuple completely
		```python
		thistuple = ("apple", "banana", "cherry")  
		del thistuple  
		print(thistuple) #this will raise an error because the tuple no longer exists
```
	- **Unpacking a Tuple**
		- When we create a tuple, we normally assign values to it. This is called "packing" a tuple
		- Example of **packing a tuple** :  `fruits = ("apple", "banana", "cherry")`
		- Example of unpacking a tuple
		```python
		fruits = ("apple", "banana", "cherry")  
		  
		(green, yellow, red) = fruits  
		  
		print(green)  
		print(yellow)  
		print(red)
```
		- Using Asterisk\* : If the number of variables is less than the number of values, you can add an `*` to the variable name and the values will be assigned to the variable as a list
		```python
		fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")  
		  
		(green, yellow, *red) = fruits  
		  
		print(green)  
		print(yellow)  
		print(red)
```
		- If the asterisk is added to another variable name than the last, Python will assign values to the variable until the number of values left matches the number of variables left
		```python
		fruits = ("apple", "mango", "papaya", "pineapple", "cherry")  
  
		(green, *tropic, red) = fruits  
		  
		print(green)  
		print(tropic)  
		print(red)
```
- **Loop through tuples** : Same as List
- **Join tuples** :
	- To join two or more tuples you can use the `+` operator
	```python
	tuple1 = ("a", "b" , "c")  
	tuple2 = (1, 2, 3)  
	  
	tuple3 = tuple1 + tuple2  
	print(tuple3)
```
	- **Multiple Tuples** : If you want to multiply the content of a tuple a given number of times, you can use the `*` operator
	```python
	fruits = ("apple", "banana", "cherry")  
	mytuple = fruits * 2  
	  
	print(mytuple)
```
- **Tuple Methods**
	- **count()** : Returns the number of times a specified value occurs in a tuple
	- **index()** :	Searches the tuple for a specified value and returns the position of where it was found
## Sets
- Sets are used to store multiple items in a single variable
- `myset = {"apple", "banana", "cherry"}`
- A set is a collection which is  unordered ,  unchangeable* , and  unindexed  and do not allow duplicate values
	- **Note:** Set  items  are unchangeable, but you can remove items and add new items
- Sets are written with curly brackets
- **Note: The values True and 1 are considered the same value in sets, and are treated as duplicates**
```python
thisset = {"apple", "banana", "cherry", True, 1, 2}  
  
print(thisset)

# Output
# {'banana', True, 2, 'apple', 'cherry'}
```
- **Note: The values False and 0 are considered the same value in sets, and are treated as duplicates**
```python
thisset = {"apple", "banana", "cherry", False, True, 0}  
  
print(thisset)

# Output
# {False, True, 'cherry', 'apple', 'banana'}
```
- To determine how many items a set has, use the `len()` function
- A set can contain different data types
- `type()` : `<class 'set'>`
- It is also possible to use the set() constructor to make a set
```python
thisset = set(("apple", "banana", "cherry")) # note the double round-brackets  
print(thisset)
```
- **Access Items**
	- You cannot access items in a set by referring to an index or a key
	- But you can loop through the set items using a `for` loop, or ask if a specified value is present in a set, by using the `in` keyword
	```python
	thisset = {"apple", "banana", "cherry"}

	for x in thisset:
	  print(x)
```
	```python
	thisset = {"apple", "banana", "cherry"}

	print("banana" in thisset)
```
- **Add items**
	- Once a set is created, you cannot change its items, but you can add new items
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	thisset.add("orange")  
	  
	print(thisset)
```
	- To add items from another set into the current set, use the `update()` method
	```python
	thisset = {"apple", "banana", "cherry"}  
	tropical = {"pineapple", "mango", "papaya"}  
	  
	thisset.update(tropical)  
	  
	print(thisset)
```
	- The object in the `update()` method does not have to be a set, it can be any iterable object (tuples, lists, dictionaries etc.)
	```python
	thisset = {"apple", "banana", "cherry"}  
	mylist = ["kiwi", "orange"]  
	  
	thisset.update(mylist)  
	  
	print(thisset)
```
- **Remove Set items**
	- To remove an item in a set, use the `remove()`, or the `discard()` method
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	thisset.remove("banana")  
	  
	print(thisset)
```
	- **If the item to remove does not exist, `remove()` will raise an error**
	- If the item to remove does not exist, `discard()` will **NOT** raise an error
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	thisset.discard("banana")  
	  
	print(thisset)
```
	- You can also use the `pop()` method to remove an item, but this method will remove a random item, so you cannot be sure what item that gets removed
	- The return value of the `pop()` method is the removed item
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	x = thisset.pop()  
	  
	print(x)  
	  
	print(thisset)
```
	- Sets are _unordered_, so when using the `pop()` method, you do not know which item that gets removed
	- The `clear()` method empties the set
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	thisset.clear()  
	  
	print(thisset)
```
	- The `del` keyword will delete the set completely
	```python
	thisset = {"apple", "banana", "cherry"}  
  
	del thisset  
	  
	print(thisset)
```
- **Loop Sets** : Same as Lists using for loop
- **Join Sets**
	- You can use the `union()` method that returns a new set containing all items from both sets, or the `update()` method that inserts all the items from one set into another
	- The `union()` method returns a new set with all items from both sets
	```python
	set1 = {"a", "b" , "c"}  
	set2 = {1, 2, 3}  
	  
	set3 = set1.union(set2)  
	print(set3)
```
	- The `update()` method inserts the items in set2 into set1
	```python
	set1 = {"a", "b" , "c"}  
	set2 = {1, 2, 3}  
	  
	set1.update(set2)  
	print(set1)
```
	- **Note: Both union() and update() will exclude any duplicate items.**
	- Keep ONLY the Duplicates
		- The `intersection_update()` method will keep only the items that are present in both sets
			- Keep the items that exist in both set `x`, and set `y`:
			```python
			x = {"apple", "banana", "cherry"}  
			y = {"google", "microsoft", "apple"}  
			  
			x.intersection_update(y)  
			  
			print(x) # {'apple'}
```
		- The `intersection()` method will return a _new_ set, that only contains the items that are present in both sets
			```python
			x = {"apple", "banana", "cherry"}  
			y = {"google", "microsoft", "apple"}  
			  
			z = x.intersection(y)  
			  
			print(z)
```
	- **Keep All, But NOT the Duplicates**
		- The `symmetric_difference_update()` method will keep only the elements that are NOT present in both sets
		```python
		x = {"apple", "banana", "cherry"}  
		y = {"google", "microsoft", "apple"}  
		  
		x.symmetric_difference_update(y)  
		  
		print(x)
```
		- The `symmetric_difference()` method will return a new set, that contains only the elements that are NOT present in both sets
		```python
		x = {"apple", "banana", "cherry"}  
		y = {"google", "microsoft", "apple"}  
		  
		z = x.symmetric_difference(y)  
		  
		print(z)
```
		- **Note:** The values `True` and `1` are considered the same value in sets, and are treated as duplicates
		```python
		x = {"apple", "banana", "cherry", True}  
		y = {"google", 1, "apple", 2}  
		  
		z = x.symmetric_difference(y)  
		  
		print(z) # {2, 'banana', 'cherry', 'google'}
```
	- **Set Methods**

| Method | Description |
| - | - |
| `add()` | Adds an element to the set |
| `clear()` | Removes all the elements from the set |
| `copy()` | Returns a copy of the set |
| `difference()` | Returns a set containing the difference between two or more sets |
| `difference_update()` | Removes the items in this set that are also included in another, specified set |
| `discard()` | Remove the specified item |
| `intersection()` | Returns a set, that is the intersection of two other sets |
| `intersection_update()` | Removes the items in this set that are not present in other, specified set(s) |
| `isdisjoint()` | Returns whether two sets have a intersection or not |
| `issubset()` | Returns whether another set contains this set or not |
| `issuperset()` | Returns whether this set contains another set or not |
| `pop()` | Removes an element from the set |
| `remove()` | Removes the specified element |
| `symmetric_difference()` | Returns a set with the symmetric differences of two sets |
| `symmetric_difference_update()` | inserts the symmetric differences from this set and another |
| `union()` | Return a set containing the union of sets |
| `update()` | Update the set with the union of this set and others |

## Dictionaries
- A dictionary is a collection which is ordered*, changeable and do not allow duplicates. 
	- `As of Python version 3.7, dictionaries are _ordered_. In Python 3.6 and earlier, dictionaries are _unordered_.`
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}
print(thisdict)
print(thisdict["brand"])
```
- Dictionary items are ordered, changeable, and does not allow duplicates.
- Dictionary items are presented in key:value pairs, and can be referred to by using the key name.
- To determine how many items a dictionary has, use the `len()` function:
- `type` :  `<class 'dict'>`
- It is also possible to use the `dict()` constructor to make a dictionary.
```python
thisdict = dict(name = "John", age = 36, country = "Norway")  
print(thisdict)
```
- You can access the items of a dictionary by referring to its key name, inside square brackets
- There is also a method called `get()` that will give you the same result
	```python
	x = thisdict.get("model")
```
- The `keys()` method will return a list of all the keys in the dictionary
- The `values()` method will return a list of all the values in the dictionary
- The `items()` method will return each item in a dictionary, as tuples in a list
	```python
	car = {  
	"brand": "Ford",  
	"model": "Mustang",  
	"year": 1964  
	}  
	  
	x = car.items()  
	  
	print(x) #before the change 
	#  dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])
	  
	car["year"] = 2020  
	  
	print(x) #after the change
	# dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 2020)])
```
- To determine if a specified key is present in a dictionary use the `in` keyword
	```python
	thisdict = {  
	  "brand": "Ford",  
	  "model": "Mustang",  
	  "year": 1964  
	}  
	if "model" in thisdict:  
	  print("Yes, 'model' is one of the keys in the thisdict dictionary")
```
- **Change Values**
	- Change the value of a specific item by referring to its key name
		```python
		thisdict = {  
		  "brand": "Ford",  
		  "model": "Mustang",  
		  "year": 1964  
		}  
		thisdict["year"] = 2018
```
	- The update() method will update the dictionary with the items from the given argument. The argument must be a dictionary, or an iterable object with key:value pairs.
		```python
		thisdict = {  
		  "brand": "Ford",  
		  "model": "Mustang",  
		  "year": 1964  
		}  
		thisdict.update({"year": 2020})
```
- **Adding Items**
	- Adding an item to the dictionary is done by using a new index key and assigning a value to it
	- The `update()` method will update the dictionary with the items from a given argument. If the item does not exist, the item will be added
- **Remove Items**
	- There are several methods to remove items from a dictionary
		- The `pop()` method removes the item with the specified key name
			```python
			thisdict = {  
			  "brand": "Ford",  
			  "model": "Mustang",  
			  "year": 1964  
			}  
			thisdict.pop("model")  
			print(thisdict)
```
		- The `popitem()` method removes the last inserted item
		- The `del` keyword removes the item with the specified key name
		```python
		thisdict = {  
		  "brand": "Ford",  
		  "model": "Mustang",  
		  "year": 1964  
		}  
		del thisdict["model"]  
		print(thisdict)
```
		- **The `del` keyword can also delete the dictionary completely**
		```python
		thisdict = {  
		  "brand": "Ford",  
		  "model": "Mustang",  
		  "year": 1964  
		}  
		del thisdict  
		print(thisdict) #this will cause an error because "thisdict" no longer exists.
```
		- The `clear()` method empties the dictionary
- **Loop Dictionaries**
	- You can loop through a dictionary by using a `for` loop
	```python
	# Print all key names in the dictionary, one by one
	for x in thisdict:  
	  print(x)
```
	```python
	# Print all _values_ in the dictionary, one by one
	for x in thisdict:  
	  print(thisdict[x])
```
	```python
	for x in thisdict.values():  
	  print(x)
```
	```python
	for x in thisdict.keys():  
	  print(x)
```
	- Loop through both _keys_ and _values_, by using the `items()` method
	```python
	for x, y in thisdict.items():  
	  print(x, y)
```
- **Copy Dictionaries**
	- You cannot copy a dictionary simply by typing `dict2 = dict1`, because: `dict2` will only be a _reference_ to `dict1`, and changes made in `dict1` will automatically also be made in `dict2`
	- There are ways to make a copy, one way is to use the built-in Dictionary method `copy()`
	```python
	# Make a copy of a dictionary with the `copy()` method
	thisdict = {  
	  "brand": "Ford",  
	  "model": "Mustang",  
	  "year": 1964  
	}  
	mydict = thisdict.copy()  
	print(mydict)
```
	- Another way to make a copy is to use the built-in function `dict()`
	```python
	# Make a copy of a dictionary with the `dict()` function
	thisdict = {  
	  "brand": "Ford",  
	  "model": "Mustang",  
	  "year": 1964  
	}  
	mydict = dict(thisdict)  
	print(mydict)
```
- **Dictionary Methods**

| Method | Dictionary |
| - | - |
| `clear()` |  Removes all the elements from the dictionary |
| `copy()` |  Returns a copy of the dictionary |
| `fromkeys()` |  Returns a dictionary with the specified keys and value |
| `get()` |  Returns the value of the specified key |
| `items()` |  Returns a list containing a tuple for each key value pair |
| `keys()` |  Returns a list containing the dictionary's keys |
| `pop()` |  Removes the element with the specified key |
| `popitem()` |  Removes the last inserted key-value pair |
| `setdefault()` |  Returns the value of the specified key. If the key does not exist: insert the key, with the specified value |
| `update()` |  Updates the dictionary with the specified key-value pairs |
| `values()` |  Returns a list of all the values in the dictionary |

## If ... Else
- `if`, `elif`, `else`
```python
a = 200  
b = 33  
if b > a:  
  print("b is greater than a")  
elif a == b:  
  print("a and b are equal")  
else:  
  print("a is greater than b")
```
- Short Hand If
	- If you have only one statement to execute, you can put it on the same line as the if statement.
	```python
	if a > b: print("a is greater than b")
```
- Short Hand If ... Else
	- This technique is known as **Ternary Operators**, or **Conditional Expressions**.
	```python
	a = 2  
	b = 330  
	print("A") if a > b else print("B")
```
	- You can also have multiple else statements on the same line
	```python
	a = 330  
	b = 330  
	print("A") if a > b else print("=") if a == b else print("B")
```
	- The `and` keyword is a logical operator, and is used to combine conditional statements
	- The `or` keyword is a logical operator, and is used to combine conditional statements
	- The `not` keyword is a logical operator, and is used to reverse the result of the conditional statement
	- `if` statements cannot be empty, but if you for some reason have an `if` statement with no content, put in the `pass` statement to avoid getting an error
- **While Loops**
	- With the break statement we can stop the loop even if the while condition is true
	- With the continue statement we can stop the current iteration, and continue with the next
	- **With the `else` statement we can run a block of code once when the condition no longer is true**
	```python
	i = 1  
	while i < 6:  
	  print(i)  
	  i += 1  
	else:  
	  print("i is no longer less than 6")
```
- **For Loops**
	```python
	fruits = ["apple", "banana", "cherry"]  
	for x in fruits:  
	  print(x)
```
	- Even strings are iterable objects, they contain a sequence of characters
	```python
	for x in "banana":  
	  print(x)
```
	```python
# Using break statement with 'for' loop
fruits = ["apple", "banana", "cherry"]  
for x in fruits:  
  print(x)  
  if x == "banana":  
    break
```
	```python
# Using continue statement with 'for' loop
fruits = ["apple", "banana", "cherry"]  
for x in fruits:  
  if x == "banana":  
    continue  
  print(x)
```
	- The range() function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.
	```python
for x in range(6):  
  print(x)
```
	- The range() function defaults to 0 as a starting value, however it is possible to specify the starting value by adding a parameter: range(2, 6), which means values from 2 to 6 (but not including 6)
	- The range() function defaults to increment the sequence by 1, however it is possible to specify the increment value by adding a third parameter: range(2, 30, **3**)
	```python
for x in range(2, 30, 3):  
  print(x)
```
	- **Else in For Loop**
		- The `else` keyword in a `for` loop specifies a block of code to be executed when the loop is finished
		```python
		for x in range(6):  
		  print(x)  
		else:  
		  print("Finally finished!")
```
		- **Note: The `else` block will NOT be executed if the loop is stopped by a `break` statement.**
		```python
		for x in range(6):  
		  if x == 3: break  
		  print(x)  
		else:  
		  print("Finally finished!")
		# Output
		# 0
		# 1
		# 2
```
	- `for` loops cannot be empty, but if you for some reason have a `for` loop with no content, put in the `pass` statement to avoid getting an error
## Functions
- In Python a function is defined using the def keyword
```python
def my_function():  
  print("Hello from a function")  
  
my_function()
```
- A parameter is the variable listed inside the parentheses in the function definition.
- An argument is the value that is sent to the function when it is called.
```python
def my_function(fname, lname):  
  print(fname + " " + lname)  
  
my_function("Emil", "Refsnes")
```
- **Arbitrary Arguments, \*args**
	- If you do not know how many arguments that will be passed into your function, add a `*` before the parameter name in the function definition.
	- This way the function will receive **a _tuple_ of arguments**, and can access the items accordingly
	```python
	def my_function(*kids):  
	  print("The youngest child is " + kids[2])  
	  
	my_function("Emil", "Tobias", "Linus")
```
	- **Arbitrary Arguments are often shortened to \*args in Python documentations.**
- **Keyword Arguments**
	- You can also send arguments with the _key_ = _value_ syntax.
	```python
	def my_function(child3, child2, child1):  
	  print("The youngest child is " + child3)  
	  
	my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```
	- **The phrase _Keyword Arguments_ are often shortened to _kwargs_ in Python documentations.**
- **Arbitrary Keyword Arguments, **kwargs**
	- If you do not know how many keyword arguments that will be passed into your function, add two asterisk: `**` before the parameter name in the function definition.
	- This way the function will receive a _dictionary_ of arguments, and can access the items accordingly
	- *Arbitrary Kword Arguments* are often shortened to  \*\*kwargs  in Python documentations.
- **Default Parameter Values**
	- If we call the function without argument, it uses the default value
	```python
	def my_function(**country = "Norway"**):  
	  print("I am from " + country)  
	  
	my_function("Sweden")  
	my_function("India")  
	my_function()  
	my_function("Brazil")
```
- **Passing a List as an Argument**
	- You can send any data types of argument to a function (string, number, list, dictionary etc.), and it will be treated as the same data type inside the function.
	```python
	def my_function(food):  
	  for x in food:  
	    print(x)  
	  
	fruits = ["apple", "banana", "cherry"]  
	  
	my_function(fruits)
```
- To let a function return a value, use the `return` statement
- `function` definitions cannot be empty, but if you for some reason have a `function` definition with no content, put in the `pass` statement to avoid getting an error

## Lambda
**- A lambda function is a small anonymous function**
- **A lambda function can take any number of arguments, but can only have one expression**
- **SYNTAX :** `lambda arguments : expression`
```python
x = lambda a : a + 10  
print(x(5))
```
- Multiply argument `a` with argument `b` and return the result
```python
x = lambda a, b : a * b  
print(x(5, 6))
```
```python
x = lambda a, b, c : a + b + c
print(x(10, 20, 30))
```
- **The power of lambda is better shown when you use them as an anonymous function inside another function.**
```python
def myfunc(n):  
  return lambda a : a * n  
  
mydoubler = myfunc(2)  
  
print(mydoubler(11))
```
```python
def myfunc(n):  
  return lambda a : a * n  
  
mydoubler = myfunc(2)  
mytripler = myfunc(3)  
  
print(mydoubler(11))  
print(mytripler(11))
```
- Use lambda functions when an anonymous function is required for a short period of time

## Array

| Method | Description |
| - | - |
| `append()` | Adds an element at the end of the list |
| `clear()` | Removes all the elements from the list |
| `copy()` | Returns a copy of the list |
| `count()` | Returns the number of elements with the specified value |
| `extend()` | Add the elements of a list (or any iterable), to the end of the current list |
| `index()` | Returns the index of the first element with the specified value |
| `insert()` | Adds an element at the specified position |
| `pop()` | Removes the element at the specified position |
| `remove()` | Removes the first item with the specified value |
| `reverse()` | Reverses the order of the list |
| `sort()` | Sorts the list |

## Generators and Decorators
### Generators
- Generators in python are a special routine that can be used to control the iteration behavior of a loop. A generator is similar to a function returning an array. A generator has a parameter, which we can call and it generates a sequence of numbers. But unlike functions, which return a whole array, a generator yields one value at a time which requires less memory.
- Any python function with the keyword “yield” may be called a generator.
- A normal python function starts execution from the first line and continues until we got a return statement or an exception or end of the function however, any of the local variables created during the function scope are destroyed and not accessible further.
- A normal python function starts execution from the first line and continues until we got a return statement or an exception or end of the function however, any of the local variables created during the function scope are destroyed and not accessible further.
- While in the case of the generator when it encounters a yield keyword the state of the function is frozen and all the variables are stored in memory until the generator is called again.
- We can use a generator in accordance with an iterator or can be explicitly called using the “**next**” keyword.
- **Generators** are functions that return an **iterable** generator object. Because the values from the generator object are fetched one at a time rather than the entire list at once, you can use a for-loop, next(), or list() function to get the actual values.
- **Reading yield values from the generator**
	- A list(), for-loop, and next() method can be used to read values from a generator object.
- **Reading values from a generator object using next()**
```python
# creating a function that accepts a number as an argument
def oddNumbers(num):
   # traversing till that number passed
   for i in range(num):
      # checking whether the iterator index value is an odd number
      if (i%2!=0):
         # getting the iterator index value if the condition is true using the yield keyword
         yield i
# calling the above function to get the odd numbers below 8
result = oddNumbers(8)
# calling the next items in the result list
print(next(result))
print(next(result))
print(next(result))
print(next(result))
# throws an error since the list has no more elements
print(next(result))

# Output
# 1
# 3
# 5
# 7
# 
# ---------------------------------------------------------------------------
# StopIteration                             Traceback (most recent call last)
# Cell In[17], line 16
#      14 print(next(result))
#      15 # throws an error since the list has no more elements
# ---> 16 print(next(result))
# 
# StopIteration:
```
### Decorators
- Python offers an amazing tool called **decorators** to add functionality to an existing code.
- This is also known as **metaprogramming** since a part of the program attempts to modify another portion of the program during the compile time.
- Decorators use functions as arguments in another function, which is then invoked inside the wrapper function.
```python
# defining a decorator
def python_decorator(func):
   def wrapper():
      print("Text before calling the function")
      func()
      print("Text after calling the function")
   return wrapper
def tutorials_decorator():
   print("Hello tutorials Point!!!")
tutorials_decorator = python_decorator(tutorials_decorator)
tutorials_decorator()

# Output:
# Text before calling the function
# Hello tutorials Point!!!
# Text after calling the function
```
### Syntactic Decorator
- The decorator pattern described above became popular in the Python community, but it was a little complex. We must write the function name three times, and the decoration is hidden beneath the function definition.
- As a result, Python added a new way to use decorators by including syntactic sugar with the **@ symbol**.
```python
# defining a decorator
def python_decorator(func):
   def wrapper():
      print("Text before calling the function")
      func()
      print("Text after calling the function")
   return wrapper
@python_decorator
def tutorials_decorator():
   print("Hello tutorials Point!!!")
tutorials_decorator()

# Output:
# Text before calling the function
# Hello tutorials Point!!!
# Text after calling the function
```
- It is the same as the previous example, the only difference is that we use **@python_decorator** instead of
	- `tutorials_decorator = python_decorator(tutorials_decorator)`