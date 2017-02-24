# Chapter 4: Classes and Objects

### What is OOP (Object Oriented Programming)?
Java's fundamental building blocks are objects, and each object is an unique identity. Each object has three dimensions: **identity**,  **attribute** that describes the object's current state, and **behavior** that's specific to the object's type. 

A **class** describes what the object will be, but is separate from the object itself. 

For instance, Class: Human being; Object: Man, Woman; Attribute: name, height; Behavior: walk, eat.

### Method
Methods define **behavior**. More specifically, a method is a collection of statements that are grouped together to perform an operation.  A method can be called multiple times. A method can also have parameters that takes in some data. A method can also have a **return** keyword to return a value when called. The type of the return value is defined in the method definition. If there is no return value, the type is void. 

```java
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
```
### Objects 
Objects can be created by Classname Objectname = new Classname(). For instance, Animal dog = new Animal(); To acess a method, you use the dot method; for instance dog.bark() references the bark() method onto the "dog" object. 

i.e. 
```java
// main class that the object will reference 
public class Animal {
  void bark() {
    System.out.println("Woof-Woof");
  }
}

////////////////////////////////////////////////

//creating an object 
class MyClass {
  public static void main(String[] args) {
    Animal dog = new Animal();
    dog.bark();
  }
}
// Outputs "Woof-Woof"
```

### Access Modifiers

In Java, there are four types of modifers: 
1. Public: Accessable from any other class. 
2. Protected: Provides the same access as the default access modifier, with the addition that subclasses can access protected methods and variables of the superclass 
3. Default: A variable or method declared with no access control modifier is available to any other class in the same package.
4. Private: Accessible only within the declared class itself.

### Getters & Setters 

Getter methods and Setter methods are primarially used to protect data when creating a class. For each variable, getter start with a get followed by the variable name and setter start with a set follow by the variable name. The keyword "this" is used to refer to the current object. 

```java
public class Vehicle {
  private String color;

  // Getter
  public String getColor() {
    return color;
  }

 // Setter
  public void setColor(String c) {
    this.color = c;
  }
}

public static void main(String[ ] args) {
  Vehicle v1 = new Vehicle();
  v1.setColor("Red");
  System.out.println(v1.getColor());
}

//Outputs "Red"
```

### Constructors 

Constructors are special methods that are invoked when an object is created and are used to initialize them. Therefore, a constructor can be used to provide initial values for object attributes. A construct **must** be same as its class name and **must** have no explicit return value. A constuctor can also take parameters to initalize attributes. Example of a constructor is: 
```java
public class Vehicle {
  private String color;
  Vehicle() {
    this.setColor("Red");
  }
  Vehicle(String c) {
    this.setColor(c);
  }
  // Setter
  public void setColor(String c) {
    this.color = c;
  }
}
//////////////////////////////////////
//if initalized w/out a parameter, color will be "Red"
Vehicle v1 = new Vehicle();

//color will be "Green"
Vehicle v2 = new Vehicle("Green"); 
```


 
