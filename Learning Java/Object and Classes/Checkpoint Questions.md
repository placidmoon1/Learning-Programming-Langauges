#Checkpoint Questions for Ch. 9: Objects and Classes 

- Describe the relationship between an object and its defining class: 

An object is an instance of the defining class. Therefore, an object is initialized by calling the class's constructor. 

- How do you define a class? 

The syntax for defining a class is: 
```java
public class className {
}
```

- How do you declare an object's reference variable? 

One can declare an object's reference variable by: 
```java
className object()
``` 

- How do you create an object? 

One can create a new object by: 
```java
new className(); //invokes the no-args constrcutor 
new className(someType a); //invokes the constructor with parameters of someType. 
``` 

- What are the differences betweeen constructors and methods?

A constructor **must** have the *same name* as the class itself; constructors do not have a return type (not even *void*); and constructors are invoked using the **new** operator when an object is created. Basically, a constructor can initialize objects. 

- When will a class have a default constructor? 

A constructor has a default constructor when no constructor is **explicitly** defined in the class. In this case, a public no-arg constructor with an empty body is implicity defined in the class. 

- Which operator is used to access a data field or invoke a method from an object? 

The member access operator is used to access a data field or invoke a method from an object.

- What is an anonymous object? 

An anonymous object is an object that doesn't have a reference variable referencing it. 

- What is **NullPointerException**? 

NullPointerException is an excpetion that occurs when a null reference variable is used to access a member of an object. 

- Is an array an object or a primitive type value? Can an array contain elements of an object type? Describe the default value for the elements of an array.

An array is an object that is created through the *new* keyword. An array can contain elements of an object type. The default value for the elements of an array is 0 for numeric, false for boolean, '\u0000' for char, and null for object element type.
