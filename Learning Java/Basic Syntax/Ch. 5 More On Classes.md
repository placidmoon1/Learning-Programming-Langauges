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

i.e. class Java extend ComputerLanguage {
  //some code
}

### Polymorphism 
