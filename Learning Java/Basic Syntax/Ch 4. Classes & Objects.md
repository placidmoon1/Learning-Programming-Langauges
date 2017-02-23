# Chapter 4: Classes and Objects

### What is OOP (Object Oriented Programming)?
Java's fundamental building blocks are objects, and each object is an unique identity. Each object has three dimensions: **identity**,  **attribute** that describes the object's current state, and **behavior** that's specific to the object's type. 

A **class** describes what the object will be, but is separate from the object itself. 

For instance, Class: Human being; Object: Man, Woman; Attribute: name, height; Behavior: walk, eat.

### Method
Methods define **behavior**. More specifically, a method is a collection of statements that are grouped together to perform an operation.  A method can be called multiple times. A method can also have parameters that takes in some data. A method can also have a **return** keyword to return a value when called. The type of the return value is defined in the method definition. If there is no return value, the type is void. 

``java
class MyClass {
  static void sayHello(String name) {
    System.out.println("Hello World! " + name);
  }
  static int sum(int val1, int val2) {
    return val1 + val2;
  public static void main(String[ ] args) {
    sayHello("Amy");
    sayHello("David");
    int x = sum(2,5) 
    System.out.println("The sum is " + x + ".")
  }
}
// Outputs 
//Hello World! Amy
//Hello World! David
//The sum is 7. 
``


