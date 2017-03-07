#Checkpoint Questions for Ch. 9: Objects and Classes 

1. Describe the relationship between an object and its defining class: 

An object is an instance of the defining class. Therefore, an object is initialized by calling the class's constructor. 

2. How do you define a class? 

The syntax for defining a class is: 
```java
public class className {
}
```

3. How do you declare an object's reference variable? 

One can declare an object's reference variable by: 
```java
className object()
``` 

4. How do you create an object? 

One can create a new object by: 
```java
new className(); //invokes the no-args constrcutor 
new className(someType a); //invokes the constructor with parameters of someType. 
``` 

5. What are the differences betweeen constructors and methods?
A constructor **must** have the *same name* as the class itself; constructors do not have a return type (not even *void*); and constructors are invoked using the **new** operator when an object is created. Basically, a constructor can initialize objects. 

6. When will a class have a default constructor? 
A constructor has a default constructor when no constructor is **explicitly** defined in the class. In this case, a public no-arg constructor with an empty body is implicity defined in the class. 

7. 
