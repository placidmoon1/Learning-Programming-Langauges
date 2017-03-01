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
class Java extend ComputerLanguage {
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

