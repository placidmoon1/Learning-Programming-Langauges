### Encapsulation
There are 4 core concepts in OOP: **encapsulation**, inheritance, polymorphism, and abstraction.
The idea behind encapsulation is to ensure that implementation details are not visible to users. More specifically, the variables of one class will be hidden from the other classes, accessible only through the methods of the current class. Therefore, to achieve encapsulation in Java, declare the class's variables as *private* and the getter/setter methods as *public*. 

```java
class StudentGrades {
  private double testGrade = 0;
  public void deposit(double grade) {
    if(grade > 0) {
      testGrade += grade;
    }
  }
}
```

### Inheritance
Inheritance is the process that enables one class to acquire the properties (methods and variables) of another. The class inheriting the properties of another is the subclass (also called derived class, or child class); the class whose properties are inherited is the superclass (base class, or parent class). To inherit from the class, you need to use the **extend** keyword. Also, when one class inherits from another class, it inerhits all **non-private** (i.e. use the **protected** access modifier) variables and methods. Constructors are not member methods, and so are **not inherited** by subclasses. **However**, the constructor of the superclass is **called** when the subclass is instantiated. 

```java
class Java extends ComputerLanguage {
  //some code
}
```

### Polymorphism 
Polymorphism, which refers to the idea of "having many forms", occurs when there is a hierarchy of classes related to each other through inheritance. A call to a member method will cause a different implementation to be executed, depending on the type of the object invoking the method.

```java
class Student {
  public void GPA() {
    System.out.println("Your GPA is 3.0!");
  }
}
class Kevin extends Student { 
  public void GPA() {
    System.out.println("Your GPA is 3.75?!");
  }
}
class Paul extends Student {
  public void GPA() { 
    System.out.println("Your GPA is 4.0!");
  }
}

public static void main(String[ ] args) {
  Studnt medi = new Kevin();
  Student smart = new Paul();
}

medi.GPA() 
// outputs "Your GPA is 3.75?!"
smart.GPA() 
// outputs "Your GPA is 4.0!"
```
### Override vs. Overload 
Method Overriding (also known as Method Polymorphism) is basically a subclass defining a behavior that's specific to the subclass type, meaning that a subclass can implement a parent class method based on its requirement.

#### Rules for Method Overriding:
1. Should have the same return type and arguments
2. The access level cannot be more restrictive than the overridden method's access level (Example: If the superclass method is declared public, the overriding method in the sub class can be neither private nor protected)
3. A method declared final or static cannot be overridden
4. If a method cannot be inherited, it cannot be overridden
5. Constructors cannot be overridden

```java
class Voice {
    public void makeSound() {
        System.out.println("Ahhhhhhhh");
    }
}
class Scream extends Voice {
    public void makeSound() {
        System.out.println("AHHHHHHHHHHH!");
    }
}
```
When methods have the same name, but different parameters, you are **overloading** the method (also known as compile-time polymorphism). 
For instance, there exists 
```java
int min(int a, int b) {
  if(a < b) {
    return a;
  }
  else {
    return b;
  }
}
```
However, when I want this method to also accept double parameters, I can override this method by 
```java
double min(double a, double b) {
  if(a < b) {
    return a;
  }
  else {
    return b;
  }
}
```
**IMPORTANT**: Overloading is not inheritance-based whereas overrriding is inheritance-based. 

### Abstract Class 
Data abstraction provides the outside world with only essential information, in a process of representing essential features without including implementation details. A good real-world example is a book. When you hear the term book, you don't know the exact specifics, such as the page count, the color, or the size, but you understand the idea, or abstraction, of a book. 

#### An abstract class has three pecularities: 
1. It cannot be instantiated (i.e. an object of an abstract class cannot be created)
2. Abstract methods must be in abstract classes. 
3. To use an abstract class, you need to inherit the class into another class using the keyword *extends*. 

### Interface
An interface is a completely abstract class that contains only abstract methods (i.e. no implementation of methods). An interface is a guarentee that abstract methods present will have public interfaces. It is defined using the **interface** class and can **only** contain static final variables other than the abstract methods. Interfaces cannot contain construtors but a class can implement multiple interfaces (unlike extension). Interface and its associate methods are *implicitly* abstract; therefore, they don't require the *abstract* keyword. You use the  *implements* keyword to use interface in your class. All methods of the interface is **overrided** when implemented.

Best pratice when using an interface and abstract class is making the abstract class implement the interface and all other classes inherit the abstract class. 
```java
interface Animal {
  public void eat();
  public void makeSound();
}

class Cat implements Animal {
  public void makeSound() {
    System.out.println("Meow");
  }
  public void eat() {
    System.out.println("omnomnom");
  }
}
```
