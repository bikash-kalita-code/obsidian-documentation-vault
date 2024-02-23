# Java Basics

Platform: Any hardware or software environment in which a program runs, is known as a platform. Since Java has a runtime environment (JRE) and API, it is called a platform.

### Types of Java Applications

4 main types:

1.  **_Standalone Application_** : Standalone applications are also known as desktop applications or window-based applications.
2.  **_Web Application_** : An application that runs on the server side and creates a dynamic page is called a web application.
3.  **_Enterprise Application_** : An application that is distributed in nature, such as banking applications, etc. is called an enterprise application.
4.  **_Mobile Application_** : An application which is created for mobile devices is called a mobile application.

### Java Platforms / Editions

4 platforms or editions of Java:

1.  **_Java SE (Java Standard Edition)_** : It is a Java programming platform. It includes Java programming APIs such as java.lang, java.io, java.net, java.util, java.sql, java.math etc. It includes core topics like OOPs, String, Regex, Exception, Inner classes, Multithreading, I/O Stream, Networking, AWT, Swing, Reflection, Collection, etc.
2.  **_Java EE (Java Enterprise Edition)_** : It is an enterprise platform that is mainly used to develop web and enterprise applications. It is built on top of the Java SE platform. It includes topics like Servlet, JSP, Web Services, EJB, JPA, etc.
3.  **_Java ME (Java Micro Edition)_** : It is a micro platform that is dedicated to mobile applications.
4.  **_JavaFX_** : It is used to develop rich internet applications. It uses a lightweight user interface API.

### What happens at compile time?

At compile time, the .java file is compiled by Java Compiler (it does not interact with OS) and converts the Java code into bytecode.

Java Code (Simple.java) -----------> Compiler ---------------> Byte Code(Simple.class)

### What happens at runtime?

At runtime, the following steps are performed.

```
Hardware\
    ^\
    |\
Runtime\
    ^\
    |\
Interpreter\
    ^\
    |\
Bytecode Verified\
    ^\
    |\
Classloader\
    ^\
    |\
Class File\
```

**_Classloader_** : It is the subsystem of JVM that is used to load class files.
**_Bytecode Verifier_** : Checks the code fragments for illegal code that can violate access rights to objects.
**_Interpreter_** : Read bytecode stream then execute the instructions.

### Can you save a Java source file by another name than the class name?

Yes, if the class is not public.
For example, filename : **Hard.java**

```
class Simple {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

Hard.java ----------> Compile -----------> Simple.class

To compile:\
`javac Hard.java`\
To execute:\
`java Simple`

## Difference between JDK, JRE, and JVM

[Read the source blog here for JDK, JRE, and JVM](https://www.javatpoint.com/difference-between-jdk-jre-and-jvm)

### JVM

JVM (Java Virtual Machine) is an abstract machine. It is called a virtual machine because it doesn't physically exist. It is a specification that provides a runtime environment in which Java bytecode can be executed. It can also run those programs which are written in other languages and compiled to Java bytecode.

JVMs are available for many hardware and software platforms. JVM, JRE, and JDK are platform dependent because the configuration of each OS is different from each other. However, Java is platform independent. There are three notions of the JVM: specification, implementation, and instance.

The JVM performs the following main tasks:

- Loads code
- Verifies code
- Executes code
- Provides runtime environment

[For explanation click here](https://www.javatpoint.com/internal-details-of-jvm)

### JRE

JRE is an acronym for Java Runtime Environment. It is also written as Java RTE. The Java Runtime Environment is a set of software tools which are used for developing Java applications. It is used to provide the runtime environment. It is the implementation of JVM. It physically exists. It contains a set of libraries + other files that JVM uses at runtime.

The implementation of JVM is also actively released by other companies besides Sun Micro Systems.

### JDK

JDK is an acronym for Java Development Kit. The Java Development Kit (JDK) is a software development environment which is used to develop Java applications and applets. It physically exists. It contains JRE + development tools.

JDK is an implementation of any one of the below given Java Platforms released by Oracle Corporation:

- Standard Edition Java Platform
- Enterprise Edition Java Platform
- Micro Edition Java Platform

The JDK contains a private Java Virtual Machine (JVM) and a few other resources such as an interpreter/loader (java), a compiler (javac), an archiver (jar), a documentation generator (Javadoc), etc. to complete the development of a Java Application.

## JVM (Java Virtual Machine) Architecture

[Read from blog here](https://www.javatpoint.com/jvm-java-virtual-machine)

### Java Variables

**_Types of Variables_**
There are three types of variables in Java:

- `local variable` - A variable declared inside the body of the method is called local variable. You can use this variable only within that method and the other methods in the class aren't even aware that the variable exists. A local variable cannot be defined with "static" keyword.
- `instance variable` - A variable declared inside the class but outside the body of the method, is called an instance variable. It is not declared as static. It is called an instance variable because its value is instance-specific and is not shared among instances.
- `static variable` - A variable that is declared as static is called a static variable. It cannot be local. You can create a single copy of the static variable and share it among all the instances of the class. Memory allocation for static variables happens only once when the class is loaded in the memory.

```
public class A
{
    static int m=100;//static variable
    void method()
    {
        int n=90;//local variable
    }
    public static void main(String args[])
    {
        int data=50;//instance variable
    }
}//end of class
```

**Example: Type Casting - Widening**

```
public class Simple{
    public static void main(String[] args){
        int a=10;
        float f=a;
        System.out.println(a);
        System.out.println(f);
    }
}
```

**Example: Type Casting - Narrowing**

```
public class Simple{
public static void main(String[] args){
float f=10.5f;
//int a=f;//Compile time error
int a=(int)f;
System.out.println(f);
System.out.println(a);
}}
```

**Example: Overflow**

```
class Simple{
    public static void main(String[] args){
        //Overflow
        int a=130;
        byte b=(byte)a;
        System.out.println(a);
        System.out.println(b);
    }
}
```

**Example: Adding Lower Type**

```
class Simple{
    public static void main(String[] args){
        byte a=10;
        byte b=10;
        //byte c=a+b;//Compile Time Error: because a+b=20 will be int
        byte c=(byte)(a+b);
        System.out.println(c);
    }
}
```

### Java Data Types

There are two types of data types in Java:

1.  **Primitive data types**: The primitive data types include boolean, char, byte, short, int, long, float and double.
2.  **Non-primitive data types**: The non-primitive data types include Classes, Interfaces, and Arrays.

There are 8 types of primitive data types:

- boolean data type
- byte data type
- char data type
- short data type
- int data type
- long data type
- float data type
- double data type

## Unicode System

Unicode is a universal international standard character encoding that is capable of representing most of the world's written languages.

Before Unicode, there were many language standards:

- ASCII (American Standard Code for Information Interchange) for the United States.
- ISO 8859-1 for Western European Language.
- KOI-8 for Russian.
- GB18030 and BIG-5 for chinese, and so on.

### Java Operators

[Click here to read more](https://www.javatpoint.com/operators-in-java)

**Example: ++ and --**

```
public class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 10;
        System.out.println(a++ + ++a);
        System.out.println(b++ + b++);
    }
}
```

**Example: ~ and !**

```
class OperatorExample{
    public static void main(String args[]){
        int a=10;
        int b=-10;
        boolean c=true;
        boolean d=false;
        System.out.println(~a);//-11 (minus of total positive value which starts from 0)
        System.out.println(~b);//9 (positive of total minus, positive starts from 0)
        System.out.println(!c);//false (opposite of boolean value)
        System.out.println(!d);//true
    }
}
```

### Java Keywords

- abstract: Java abstract keyword is used to declare an abstract class. An abstract class can provide the implementation of the interface. It can have abstract and non-abstract methods.
- boolean: Java boolean keyword is used to declare a variable as a boolean type. It can hold True and False values only.
- break: Java break keyword is used to break the loop or switch statement. It breaks the current flow of the program at specified conditions.
- byte: Java byte keyword is used to declare a variable that can hold 8-bit data values.
- case: Java case keyword is used with the switch statements to mark blocks of text.
- catch: Java catch keyword is used to catch the exceptions generated by try statements. It must be used after the try block only.
- char: Java char keyword is used to declare a variable that can hold unsigned 16-bit Unicode characters
- class: Java class keyword is used to declare a class.
- continue: Java continue keyword is used to continue the loop. It continues the current flow of the program and skips the remaining code at the specified condition.
- default: Java default keyword is used to specify the default block of code in a switch statement.
- do: Java do keyword is used in the control statement to declare a loop. It can iterate a part of the program several times.
- double: Java double keyword is used to declare a variable that can hold 64-bit floating-point number.
- else: Java else keyword is used to indicate the alternative branches in an if statement.
- enum: Java enum keyword is used to define a fixed set of constants. Enum constructors are always private or default.
- extends: Java extends keyword is used to indicate that a class is derived from another class or interface.
- final: Java final keyword is used to indicate that a variable holds a constant value. It is used with a variable. It is used to restrict the user from updating the value of the variable.
- finally: Java finally keyword indicates a block of code in a try-catch structure. This block is always executed whether an exception is handled or not.
- float: Java float keyword is used to declare a variable that can hold a 32-bit floating-point number.
- for: Java for keyword is used to start a for loop. It is used to execute a set of instructions/functions repeatedly when some condition becomes true. If the number of iteration is fixed, it is recommended to use for loop.
- if: Java if keyword tests the condition. It executes the if block if the condition is true.
- implements: Java implements keyword is used to implement an interface.
- import: Java import keyword makes classes and interfaces available and accessible to the current source code.
- instanceof: Java instanceof keyword is used to test whether the object is an instance of the specified class or implements an interface.
- int: Java int keyword is used to declare a variable that can hold a 32-bit signed integer.
- interface: Java interface keyword is used to declare an interface. It can have only abstract methods.
- long: Java long keyword is used to declare a variable that can hold a 64-bit integer.
- native: Java native keyword is used to specify that a method is implemented in native code using JNI (Java Native Interface).
- new: Java new keyword is used to create new objects.
- null: Java null keyword is used to indicate that a reference does not refer to anything. It removes the garbage value.
- package: Java package keyword is used to declare a Java package that includes the classes.
- private: Java private keyword is an access modifier. It is used to indicate that a method or variable may be accessed only in the class in which it is declared.
- protected: Java protected keyword is an access modifier. It can be accessible within the package and outside the package but through inheritance only. It can't be applied with the class.
- public: Java public keyword is an access modifier. It is used to indicate that an item is accessible anywhere. It has the widest scope among all other modifiers.
- return: Java return keyword is used to return from a method when its execution is complete.
- short: Java short keyword is used to declare a variable that can hold a 16-bit integer.
- static: Java static keyword is used to indicate that a variable or method is a class method. The static keyword in Java is mainly used for memory management.
- strictfp: Java strictfp is used to restrict the floating-point calculations to ensure portability.
- super: Java super keyword is a reference variable that is used to refer to parent class objects. It can be used to invoke the immediate parent class method.
- switch: The Java switch keyword contains a switch statement that executes code based on test value. The switch statement tests the equality of a variable against multiple values.
- synchronized: Java synchronized keyword is used to specify the critical sections or methods in multithreaded code.
- this: Java this keyword can be used to refer the current object in a method or constructor.
- throw: The Java throw keyword is used to explicitly throw an exception. The throw keyword is mainly used to throw custom exceptions. It is followed by an instance.
- throws: The Java throws keyword is used to declare an exception. Checked exceptions can be propagated with throws.
- transient: Java transient keyword is used in serialization. If you define any data member as transient, it will not be serialized.
- try: Java try keyword is used to start a block of code that will be tested for exceptions. The try block must be followed by either catch or finally block.
- void: Java void keyword is used to specify that a method does not have a return value.
- volatile: Java volatile keyword is used to indicate that a variable may change asynchronously.
- while: Java while keyword is used to start a while loop. This loop iterates a part of the program several times. If the number of iteration is not fixed, it is recommended to use the while loop.

### Java Comments

There are three types of comments in Java:

1.  Single Line Comment
```
// This is a single line comment
```
2.  Multi Line Comment

```
/*
   This is a,
   multi-line comment
*/
```

3.  Documentation Comment

```
/**
*
* This is a,
* documentation comment
*
/
```

### Examples:

1.  Java Enum in Switch Statement

```
class Main {
    public enum Day {
        Sun, Mon, Tue, Wed, Thu, Fri, Sat
    };

    public static void main(String[] args) {
        Day[] DayNow = Day.values();
        for (Day Now : DayNow) {
            switch (Now) {
                case Sun:
                    System.out.println("Sunday");
                    break;
                case Mon:
                    System.out.println("Monday");
                    break;
                case Tue:
                    System.out.println("Tuesday");
                    break;
                case Wed:
                    System.out.println("Wednesday");
                    break;
                case Thu:
                    System.out.println("Thursday");
                    break;
                case Fri:
                    System.out.println("Friday");
                    break;
                case Sat:
                    System.out.println("Saturday");
                    break;
            }
        }
    }
}
```

2.  Java for-each Loop

```
public class ForEachExample {
    public static void main(String[] args) {
        //Declaring an array
        int arr[]={12,23,44,56,78};
        //Printing array using for-each loop
        for(int i:arr){
            System.out.println(i);
        }
    }
}
```

3.  Java Labeled For Loop
    We can have a name of each Java for loop. To do so, we use label before the for loop. It is useful while using the nested for loop as we can break/continue specific for loop.

```
class LabeledForExample {
    public static void main(String[] args) {
        // Using Label for outer and for loop
        aa: for (int i = 1; i <= 3; i++) {
            bb: for (int j = 1; j <= 3; j++) {
                if (i == 2 && j == 2) {
                    break aa;
                }
                System.out.println(i + " " + j);
            }
        }
    }
}
```
