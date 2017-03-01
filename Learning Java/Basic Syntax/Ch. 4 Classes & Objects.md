# Chapter 4: Classes and Objects

### What is OOP (Object Oriented Programming)?
Java's fundamental building blocks are objects, and each object is an unique identity. Each object has three dimensions: **identity**,  **attribute** that describes the object's current state, and **behavior** that's specific to the object's type. 

A **class** describes what the object will be, but is separate from the object itself. Basically, a class is a template for objects. It defines the properties of objects and provides constructors for creating objects and methods for manipulating them.

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
An object is an instance of a class. You use the new operator to create an object. For instance, an object can be created by Classname Objectname = new Classname(). Or, Animal dog = new Animal(). To acess a method, you use the dot operator (.); for instance dog.bark() references the bark() method onto the "dog" object. 

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

### Access Modifiers (In Java, there are four types of modifers)
2.  Public: Accessable from any other class. 
3. Protected: Provides the same access as the default access modifier, with the addition that subclasses can access protected methods and variables of the superclass 
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

### Math class
The JDK (Java Development Kit) defines a number of useful classes, one of them being the Math class, which provides predefined methods for mathematical operations.
Example of methods corresponding to the Math class are: 
```java
Math.abs() //gives absolute values
Math.ceil() //rounds a floating point value up to the nearest integer value
Math.floor() //rounds a floating point value down to the nearest integer value.
Math.max() // returns the largest of its parameters (param can be more than 2).
Math.min() /returns the smallest parameter
Math.pow() //takes two parameters and returns the first parameter raised to the power of the second parameter.
// and number of other methods such as sin(), cos(), sqrt(), and others exist in the Math class. 
```

### Static keyword
A static variable is a variable shared by all instances of the same class. A static method is a method that can be invoked without using instances. 

 ```java
 public class Student{
   public static int numStu=0;
   Student(){
       numStu++;
   }
   Student(int num){
       numStu += num;
   }
}

public class MyClass {
    public static void main(String[ ] args) {
       Student Kevin = new Student();
       Student Matt = new Student();
       Student couple = new Student(2);
    System.out.println(Student.numStu);
    }
}
```
### Final keyword 
The final keyword is used to mark a variable constant, so that it can be assigned only once.

```java
class WhatIsPi {
  public static final double PI = 3.14; 
  public static void main(String[] args) {
    System.out.println(PI);
  }
}
