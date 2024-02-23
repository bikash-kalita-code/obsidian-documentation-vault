**NOTES**
- Python is an object oriented programming language.
- Almost everything in Python is an object, with its properties and met hods.
- A Class is like an object constructor, or a "blueprint" for creating objects.
## Classes/Objects
- **Creating a Class**
```python
class MyClass:  
  x = 5
```
- **Creating an Object**
```python
p1 = MyClass()  
print(p1.x)
```
- **The __init__() function**
	- **All classes have a function called \_\_init\_\_(), which is always executed when the class is being initiated.**
	- Use the \_\_init\_\_() function to assign values to object properties, or other operations that are necessary to do when the object is being created
	```python
	# Create a class named Person, use the __init__() function to assign values for name and age:
	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age
	
	p1 = Person("John", 36)
	
	print(p1.name)
	print(p1.age)
```
- **Note:** The `__init__()` function is called automatically every time the class is being used to create a new object.
- **The __str__() Function**
	- **The \_\_str\_\_() function controls what should be returned when the class object is represented as a string**.
	- If the __str__() function is not set, the string representation of the object is returned
	```python
	# The string representation of an object WITHOUT the __str__() function
	class Person:
	  def __init__(self, name, age):
	    self.name = name
	    self.age = age
	
	p1 = Person("John", 36)
	
	print(p1)
	# Output
	# <__main__.Person object at 0x0000022540EBD550>
```
	```python
	# The string representation of an object WITH the __str__() function
	class Person:  
	  def __init__(self, name, age):  
	    self.name = name  
	    self.age = age  
	  
	  def __str__(self):  
	    return f"{self.name}({self.age})"  
	  
	p1 = Person("John", 36)  
	  
	print(p1)
# Output
# John(36)
```
- **Object Methods**
	- Methods in objects are functions that belong to the object
	```python
	class Person:  
	  def __init__(self, name, age):  
	    self.name = name  
	    self.age = age  
	  
	  def myfunc(self):  
	    print("Hello my name is " + self.name)  
	  
	p1 = Person("John", 36)  
	p1.myfunc()
```
	- **Note: The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.**
- **The self Parameter**
	- The `self` parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class
	- It does not have to be named `self` , you can call it whatever you like, but it has to be the first parameter of any function in the class
	```python
	class Person:  
	  def __init__(mysillyobject, name, age):  
	    mysillyobject.name = name  
	    mysillyobject.age = age  
	  
	  def myfunc(abc):  
	    print("Hello my name is " + abc.name)  
	  
	p1 = Person("John", 36)  
	p1.myfunc()
```
- **Modify Object Properties**
	- `p1.age = 40`
- **Delete Object Properties**
	- `del p1.age`
- **Delete Objects**
	- `del p1`
- **The pass Statement**
	- `class` definitions cannot be empty, but if you for some reason have a `class` definition with no content, put in the `pass` statement to avoid getting an error
	```python
	class Person:  
	  pass
```

## Inheritance
- Inheritance allows us to define a class that inherits all the methods and properties from another class.
- **Parent class** is the class being inherited from, also called base class.
- **Child class** is the class that inherits from another class, also called derived class.
- **Create a Parent Class**
	```python
	class Person:  
	  def __init__(self, fname, lname):  
	    self.firstname = fname  
	    self.lastname = lname  
	  
	  def printname(self):  
	    print(self.firstname, self.lastname)  
	  
	#Use the Person class to create an object, and then execute the printname method:  
	  
	x = Person("John", "Doe")  
	x.printname()
```
- **Create a Child Class**
	```python
	class Student(Person):
	  pass
	x = Student("Mike", "Olsen")
	x.printname()
	# Output
	# Mike Olsen
```
- **Note:** Use the `pass` keyword when you do not want to add any other properties or methods to the class.
- **Add the \_\_init\_\_() Function**
	- **Note:** The `__init__()` function is called automatically every time the class is being used to create a new object.
	- When you add the `__init__()` function, the child class will no longer inherit the parent's `__init__()` function.
	```python
	class Student(Person):  
	  def __init__(self, fname, lname):  
	    #add properties etc.
```
	- **Note: The child's \_\_init\_\_() function overrides the inheritance of the parent's \_\_init\_\_() function.**
	- **To keep the inheritance of the parent's `__init__()` function, add a call to the parent's `__init__()` function**
	```python
	class Student(Person):  
	  def __init__(self, fname, lname):  
	    Person.__init__(self, fname, lname)
```
- **Use the super() Function**
	- Python also has a `super()` function that will make the child class inherit all the methods and properties from its parent
	```python
	class Student(Person):  
	  def __init__(self, fname, lname):  
	    super().__init__(fname, lname)
```
	- **By using the `super()` function, you do not have to use the name of the parent element, it will automatically inherit the methods and properties from its parent.**
- **Add Properties**
	```python
	class Student(Person):  
	  def __init__(self, fname, lna8me, year):  
	    super().__init__(fname, lname)  
	    self.graduationyear = year  
	  
	x = Student("Mike", "Olsen", 2019)
```
- **Add Methods**
	```python
	class Student(Person):  
	  def __init__(self, fname, lname, year):  
	    super().__init__(fname, lname)  
	    self.graduationyear = year  
	  
	  def welcome(self):  
	    print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)
```
	- **If you add a method in the child class with the same name as a function in the parent class, the inheritance of the parent method will be overridden.**

## Iterators
- An iterator is an object that contains a countable number of values.
- An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.
- Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`.
- **Iterator vs Iterable**
	- Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable _containers_ which you can get an iterator from.
	- All these objects have a `iter()` method which is used to get an iterator:
	```python
	mytuple = ("apple", "banana", "cherry")  
	myit = iter(mytuple)  
	  
	print(next(myit))  
	print(next(myit))  
	print(next(myit))
```
	- Even strings are iterable objects, and can return an iterator
	```python
	mystr = "banana"  
	myit = iter(mystr)  
	  
	print(next(myit))  
	print(next(myit))  
	print(next(myit))  
	print(next(myit))  
	print(next(myit))  
	print(next(myit))
```
- **Looping Through an Iterator**
	- We can also use a `for` loop to iterate through an iterable object
	```python
	# Iterate the values of a tuple
	mytuple = ("apple", "banana", "cherry")  
	  
	for x in mytuple:  
	  print(x)
```
	```python
	mystr = "banana"  
	  
	for x in mystr:  
	  print(x)
```
	- The `for` loop actually creates an iterator object and executes the next() method for each loop.
- **Create an Iterator**
	- To create an object/class as an iterator you have to implement the methods `__iter__()` and `__next__()` to your object.
	- The `__iter__()` method acts similar `__init__()`, you can do operations (initializing etc.), but must always return the iterator object itself
	- The `__next__()` method also allows you to do operations, and must return the next item in the sequence.
	```python
	class MyNumbers:  
	  def __iter__(self):  
	    self.a = 1  
	    return self  
	  
	  def __next__(self):  
	    x = self.a  
	    self.a += 1  
	    return x  
	  
	myclass = MyNumbers()  
	myiter = iter(myclass)  
	  
	print(next(myiter))  
	print(next(myiter))  
	print(next(myiter))  
	print(next(myiter))  
	print(next(myiter))
```
- **StopIteration**
	- To prevent the iteration from going on forever, we can use the `StopIteration` statement.
	- In the `__next__()` method, we can add a terminating condition to raise an error if the iteration is done a specified number of times:
	```python
	class MyNumbers:  
	  def __iter__(self):  
	    self.a = 1  
	    return self  
	  
	  def __next__(self):  
	    if self.a <= 20:  
	      x = self.a  
	      self.a += 1  
	      return x  
	    else:  
	      raise StopIteration  
	  
	myclass = MyNumbers()  
	myiter = iter(myclass)  
	  
	for x in myiter:  
	  print(x)
```

## Polymorphism
- The word "polymorphism" means "many forms", and in programming it refers to methods/functions/operators with the same name that can be executed on many objects or classes.
### Function Polymorphism
- An example of a Python function that can be used on different objects is the `len()` function.
```python
# Using len() on string
x = "Hello World!"  
print(len(x))

# Using len() on tuple
mytuple = ("apple", "banana", "cherry") 
print(len(mytuple))

# Using len() on dictionary
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
print(len(thisdict))
```
### Class Polymorphism
- Polymorphism is often used in Class methods, where we can have multiple classes with the same method name.
```python
class Car:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Drive!")

class Boat:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Sail!")

class Plane:
  def __init__(self, brand, model):
    self.brand = brand
    self.model = model

  def move(self):
    print("Fly!")

car1 = Car("Ford", "Mustang")       #Create a Car class
boat1 = Boat("Ibiza", "Touring 20") #Create a Boat class
plane1 = Plane("Boeing", "747")     #Create a Plane class

for x in (car1, boat1, plane1):
  x.move()
```
### Inheritance Class Polymorphism
- The child classes inherits parent class's methods but can override them.
```python
class Vehicle:  
  def __init__(self, brand, model):  
    self.brand = brand  
    self.model = model  
  
  def move(self):  
    print("Move!")  
  
class Car(Vehicle):  
  pass  
  
class Boat(Vehicle):  
  def move(self):  
    print("Sail!")  
  
class Plane(Vehicle):  
  def move(self):  
    print("Fly!")  
  
car1 = Car("Ford", "Mustang") #Create a Car object  
boat1 = Boat("Ibiza", "Touring 20") #Create a Boat object  
plane1 = Plane("Boeing", "747") #Create a Plane object  
  
for x in (car1, boat1, plane1):  
  print(x.brand)  
  print(x.model)  
  x.move()
```

## Python Scope
- A variable is only available from inside the region it is created. This is called **scope**.
### Local Scope
- A variable created inside a function belongs to the _local scope_ of that function, and can only be used inside that function.
- **Function Inside Function**
	- A variable `x` is not available outside the function where it was created, but it is available for any function inside the function
	```python
	def myfunc():
	  x = 300
	  def myinnerfunc():
	    print(x)
	  myinnerfunc()
	
	myfunc()
```
### Global Scope
- A variable created in the main body of the Python code is a global variable and belongs to the global scope.
- Global variables are available from within any scope, global and local.
### Global Keyword
- The `global` keyword makes the variable global.
- Also, use the `global` keyword if you want to make a change to a global variable inside a function.
```python
def myfunc():  
  global x  
  x = 300  
  
myfunc()  
  
print(x)
```

## Modules
- Consider a module to be the same as a code library.
- A file containing a set of functions you want to include in your application.
### Create a Module
- To create a module just save the code you want in a file with the file extension `.py`
```python
# Save this code in a file named `mymodule.py`
def greeting(name):  
  print("Hello, " + name)
```
### Use a Module
- **Note:** When using a function from a module, use the syntax: _module_name.function_name_.
```python
# Import the module named mymodule, and call the greeting function:
import mymodule  
mymodule.greeting("Jonathan")
```
### Variables in Module
```python
# Inside mymodule.py
person1 = {  
  "name": "John",  
  "age": 36,  
  "country": "Norway"  
}

# Inside another file
import mymodule  
a = mymodule.person1["age"]  
print(a)
```
### Naming a Module
You can name the module file whatever you like, but it must have the file extension `.py`
### Re-naming a Module
You can create an alias when you import a module, by using the `as` keyword
```python
import mymodule as mx  
  
a = mx.person1["age"]  
print(a)
```
### Built-in Modules
```python
import platform  
  
x = platform.system()  
print(x)
```
### Using the dir() Function
- There is a built-in function to list all the function names (or variable names) in a module. The `dir()` function:
```python
import platform  
  
x = dir(platform)  
print(x)
```
### Import From Module
- You can choose to import only parts from a module, by using the `from` keyword.
- **Note:** When importing using the `from` keyword, do not use the module name when referring to elements in the module. Example: `person1["age"]`, **not** `mymodule.person1["age"]`
```python
# Inside file : mymodule.py
def greeting(name):  
  print("Hello, " + name)  
  
person1 = {  
  "name": "John",  
  "age": 36,  
  "country": "Norway"  
}

# Inside another file
from mymodule import person1  
print (person1["age"])
```

## Datetime
