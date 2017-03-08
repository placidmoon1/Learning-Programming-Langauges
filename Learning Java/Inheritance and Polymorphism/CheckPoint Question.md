#CheckPoint Q. for Ch. 11: Inheritance and Polymorphism

- True or false? A subclass is a subset of a superclass. 

False; a subclass is not a subset of its superclass. In fact, a subclass usually contains more information and methods than its superclass.

- What keyword do you use to defiine a subclass? 

The *extends* keyword is used to define a subclass. 

- What is signle inheritance? What is multiple inheritance? Does Java support multiple inheitance. 

Single inheritance allows a subclass to extend only one superclass. Multiple inheritance allows a subclass to extend multiple classes. Java does not allow multiple inheritance.

- Problem that arises with the following code: 

```java
class A {
  public A(int x) {
  }
}
class B extends A {
  public B() {
  }
}
public class C {
  public static void main(String[] args) {
    B b = new B();
  }
}
```

Though there is no explicit no-args constructor in class A, A defines a constructor with a parameter. Moreover, the default constructor of B tries to implicitly invokes the no-args super constrcutor for A. Therefore, it results into a compile-time error. 

- How does a subclass invoke its superclass’s constructor? 

A subclass can implicitly invoke its superclass's no-args constrcutor when no **super(someType someParam)** is explicitly invoked. If a subclass wants to invoke its superclass's constructor with a certain param, it uses the *super()* keyword. 

- True or false? When invoking a constructor from a subclass, its superclass’s no-arg constructor is always invoked.

False (if explicitly defined). A subclass's constructor explicitly invokes a superclass's constructor; if one does this, the superclass's no-arg constructor is not invoked.

- Explain the difference between method overloading and method overriding.

Method overloading defines methods of the same name in a class. Method overriding modifies the methods that are defined in the superclasses. Method overriding should have the same parameters, same method name, and should be covariant.

- What is the benefit of using the @Override annotation?

It forces the compiler to check the signature of the overridden method to ensure that the method is defined correctly.
