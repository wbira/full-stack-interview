<h1 align="center">
C# Interview Questions & Answers
</h1>
<p align="center">
    <img src="https://github.com/monkey3310/full-stack-interview/blob/master/assets/csharp.png" alt="C# Interview Questions & Answers" height="200"/>
    <i>Logo by Chris McKee</i>
</p>

_Note: Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would._

### 1. What is an Object and a Class? :star:

<details>
    <summary>
        Answer
    </summary>

**Class** is an encapsulation of properties and methods that are used to represent a real-time entity. It is a data structure that brings all the instances together in a single unit.

**Object** in an instance of a Class.

</details>

### 2. What is Managed and Unmanaged code? :star:

<details>
    <summary>
        Answer
    </summary>

**Managed** code is a code being executed by **Common Language Runtime** i.e. all applications based on .NET Platform.
**Unmanaged** code is any code being executed by other frameworks and handled by the .NET platform.

</details>

### 3. What is interface? :star:

<details>
    <summary>
        Answer
    </summary>

It contains is the declaration of methods, properties, and events. Interfaces don't contain any implementations.

</details>

### 4. What are the different types of classes in C#? :star:

<details>
    <summary>
        Answer
    </summary>

- **Partial class** – Allows its members to be divided or shared with multiple .cs files. It is denoted by the keyword `partial`.
- **Sealed class** – It is a class which cannot be inherited. To access the members of a sealed class, we need to create the object of the class. It is denoted by the keyword `sealed`.
- **Abstract class** – It is a class whose object cannot be instantiated. The class can only be inherited. It should contain at least one method. It is denoted by the keyword `abstract`.
- **Static class** – It is a class which does not allow inheritance. The members of the class are also static. It is denoted by the keyword `static`. This keyword tells the compiler to check for any accidental instances of the static class.

</details>

### 5. What are the differences between a Class and a Struct? :star:

<details>
    <summary>
        Answer
    </summary>


| Class                              | Struct                        |
| ---------------------------------- | ----------------------------- |
| Supports Inheritance               | Does not support Inheritance  |
| Pass by reference (reference type) | Pass by Copy (Value type)     |
| Members are private by default     | Members are public by default |

</details>

### 6. What is the difference between Virtual method and Abstract method? :star:

<details>
    <summary>
        Answer
    </summary>


**Virtual method** must always have a default implementation. However, it can be overridden in the derived class, though not mandatory. It can be overridden using `override` keyword. `virtual` modifier is used.

**Abstract method** does not have an implementation. It resides in the abstract class. It is mandatory that the derived class implements the abstract method. An override keyword is not necessary here though it can be used. An abstract method is implicitly a virtual method. `abstract` modifier is used.

</details>

### 7. Namespaces in C#?  :star:

<details>
    <summary>
        Answer
    </summary>


A scope that contains a set of related objects. You can use a namespace to organize code elements and to create globally unique types. The `namespace` keyword is used to declare them.

</details>

### 8. What is “using” statement in C#? :star:

<details>
    <summary>
        Answer
    </summary>


It's an import. It declares that a particular namespace is being used by the program.

</details>

### 9. What are the commonly used I/O Classes? :star:

<details>
    <summary>
        Answer
    </summary>


- `File` – Helps in manipulating a file.
- `StreamWriter` – Used for writing characters to a stream.
- `StreamReader` – Used for reading characters to a stream.
- `StringWriter` – Used for reading a string buffer.
- `StringReader` – Used for writing a string buffer.
- `Path` – Used for performing operations related to path information.

</details>

### 10. What is an Abstract Class? :star:

<details>
    <summary>
        Answer
    </summary>


Class with the `abstract` modifier in class declaration indicate that the class is intended to be only used as a base class of other classes. An instance of the class itself cannot be created. Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.

</details>

### 11. What are Boxing and Unboxing? :star::star:

<details>
    <summary>
        Answer
    </summary>


Conversion between a value and a reference type:

**Boxing:** value -> reference type

**Unboxing:** reference type -> value

</details>

### 12. What is the difference between `continue` and `break` statement? :star:

<details>
    <summary>
        Answer
    </summary>


`break` statement breaks the loop and makes the program exit the loop.
`continue` statement doesn't break the loop, it breaks the current iteration of the loop.

</details>

### 13. What is an Array? :star:

<details>
    <summary>
        Answer
    </summary>


Array are used to store multiple values of the same type. Collection is stored in a contiguous memory location.

```cs
var numbers = new double[10];
var withDefaultValues = new int[4] {1, 2, 3, 4}

var moreThanOneDimension = new int[3,2] { {1, 11}, {2, 21}, {3, 31}} 
```

</details>

### 14. What is a Jagged Array? :star:

<details>
    <summary>
        Answer
    </summary>

Jagged array is an array whose elements are arrays. Array of arrays.

</details>

### 15. What is a Delegate? :star::star:

<details>
    <summary>
        Answer
    </summary>

It is a type that represents references to methods with a particular parameter list and return type. When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type. You can invoke (or call) the method through the delegate instance.

Delegates are used to pass methods as arguments to other methods. 

Types of delegates available:
* Single Delegate
* Multicast Delegate
* Generic Delegate
  * `Func`
  * `Action`
  * `Predicate`

</details>

### 16. What are Events? :star::star:

<details>
    <summary>
        Answer
    </summary>

An event is a message sent by an object to signal the occurrence of an action. 
A class that raises an event is called a publisher and a class which responds/receives the event is called a subscriber. An Event should have at least one subscriber else that event is never raised.

Delegates are used to declare Events.

</details>

### 17. What is Reflection? :star::star:

<details>
    <summary>
        Answer
    </summary>
    
Reflection provides objects (of type `Type`) that describe assemblies, modules and types. You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties. If you are using attributes in your code, reflection enables you to access them.

</details>

### 18. What is a Generic Class? :star::star:

<details>
    <summary>
        Answer
    </summary>
    
Generic classes encapsulate operations that are not specific to a particular data type. The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on. Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.

</details>

### 19. What is the difference between “out” and “ref” parameters

<details>
    <summary>
        Answer
    </summary>
    
`ref` parameters are for the data that is both input and output of a method - it indicates that the data can be modified by the method call. When using `ref` the variable passed must be initialized.

`out` parameters are for the data that is an output only of the method - caller doesn't need to initialized this variable as it's to be handled by the method.

</details>

### 20. Can we use “this” inside a static method?

<details>
    <summary>
        Answer
    </summary>
    
No, because there is no instance that `this` would refer to.

</details>

### 21. What is the difference between “StringBuilder” and “String” in C#?

<details>
    <summary>
        Answer
    </summary>
    
`StringBuilder` is mutable, which means once object for `StringBuilder` is created, it later be modified either using `Append`, `Remove` or `Replace`.
`String` is immutable and it means we cannot modify the string object and will always create new object in memory of `string` type.

</details>

### 22. What is Nullable Types

<details>
    <summary>
        Answer
    </summary>
    
Value types that also can hold a null values (simiar to reference types.)

```cs
int? nullableInt = null
```

</details>

### 23. What is the difference between `as` and `is` operators

<details>
    <summary>
        Answer
    </summary>
    
`as` is used for casting objects.
`is` is used for checking if object is of a type and returns a `bool` value

</details>

### 24. What loop types are available in C#?

<details>
    <summary>
        Answer
    </summary>
    
`for`, `while`, `do...while`

</details>

### 25. What are Attributes?

<details>
    <summary>
        Answer
    </summary>
    
Method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth). After an attribute is associated with a program entity, the attribute can be queried at run time by using __reflection__.

</details>

### 26. Access modifiers in C#?

<details>
    <summary>
        Answer
    </summary>
    
`public` – can be accessed from any code in the project.
`private` - can be accessed by any code within the containing class only. If an attribute or class is defined without access modifiers, it's default access modifier will be `private`.
`protected` - can be accessed by any method in the inherited classes and any method within the same class. Cannot be applied to `classes` and `interfaces`. Methods and fields in a `interface` can't be declared `protected`.
`internal` – access is restricted to classes within the current project assembly.
`protected internal` – access is restricted to classes within the current project assembly and types derived from the containing class. 

</details>

### 27. What is method overloading?

<details>
    <summary>
        Answer
    </summary>
    
When method is created with the same name but different signature (different set of parameters). Constructors, methods, functions and operators can be overloaded.

</details>

### 28. What is method overriding?

<details>
    <summary>
        Answer
    </summary>
    
It's providing new implementation for the method in a derived class that will be used instead of the method from the base class.

</details>

### 29. Examples of Polymorphism in C#?

<details>
    <summary>
        Answer
    </summary>
    
**Compile time** polymorphism: Overloading
**Runtime** polymorphism: Overriding

</details>
