# Java Pro Tips & Interesting Quirks 

## Table of Contents: 

1. [Single vs Double Operators](#single-vs-double-operators)
2. [Breaking (with labels)](#breaking-with-labels)
3. [Java types and default values](#java-types-and-default-values)
4. [Lists of Exceptions (and How to Handle Them)](#lists-of-exceptions)
5. [The SOLID Principle](#the-solid-principle)
6. [Do subclasses inherit private fields?](#do-subclasses-inherit-private-fields)
7. [.equals() method vs. ==](#equals-method-vs-)
8. [Covariant Method Overriding!](#covariant-method-overriding)

### Single vs Double Operators

Java provides the single amperand (&) and vertical bar (|) for an unconditional evalution of both operands. Therefore, **&** is referred as the *unconditional AND* operator, and **|** is referred as the *unconditional OR* operator. In some rare siutations when needed, one can use the single **&** or **|** to guarantee that the right-hand operand is evaluated regardless of whether the left-hand operand is **true** or **false**. 

On the other hand, the double amperand (&&) and vertical bar (||) are *short circuit* operators; that is, it won't necessarily evaluate all operands if the precedent operand returns false (for &&) or precedent operand returns true (for ||). 

> If possible, avoid using the **&** and **|** operators; the benefits of such opeartors are marginal. Furthermore, if one uses the single amerpand (&) and if the left operand returns false, it would result into a runtime error. 

### Breaking (with labels) 

Every statement in Java can have an optional label as an indentifier, normaally associated with loops. One can use a **break** statement with a label to break out of the labeled loop, and a **continue** statement with a label to break out of the current iteration of the labeled loop. 

Code Snippet #1 (Break):

```java
outer:
 for (int i = 1; i < 10; i++) {
 inner:
    for (int j = 1; j < 10; j++) {
      if (i * j > 100)
        break outer;
      System.out.println(i * j);
     }
  }
// loop ends when i * j > 100.
```

Code Snippet #2 (Continue): 

```java 
outer:
 for (int i = 1; i < 10; i++) {
 inner:
    for (int j = 1; j < 10; j++) {
     if (i * j > 50)
        continue outer;
     System.out.println(i * j);
    }
 } 
// The following continue statement breaks out of the inner
// loop if (i * j > 50) and starts a new iteration of the outer
// loop if i < 10 is true after i is incremented by 1. 
 ```
 
### Java types and default values
 
 Java has 8 primitive types used to represent simple data types that represents integers, real numbers, characters, and Boolean types. Those types are: boolean (default: `false`), byte (default: `0`), char (default: `\u0000`), short (default: `0`), int (default: `0`), long (default: `0L`), float (default: `0.0f`) and double (deefault: 0). Default values are default values for instantiated variables when no value is assigned. Primitive values do not need the **new** keyword to be initialized because they are initalized as literals (i.e. not objects created from a class; rather, a source code representation of a fixed value).  
 
The compiler does not assign default values to local variables (i.e. variables defined in a body of a method). Therefore, one must initialize variables beforehand to avoid compile-time error for accessing an uninitialized local variables. 
 
 Java also has the Object type (i.e. String) defaulted as null (null is a *literal*).
 
### Lists of Exceptions 

1. **NullPointerExcpetion**: Throws when one invoke a method on a reference variable with a **null** value. To avoid such exception, make sure to assign an object reference to the variable before invoking the method throught the reference variable. 
2. **IndexOutOfBoundsException**: Thrown to indicate that an index of some sort (such as to an array, to a string, or to a vector) is out of range. (Subtypes: *String*IndexOutOfBounds or *Array*IndexOutOfBounds Exception).
3. **ArithmeticException**: Thrown when an unexpected/exceptional arithmetric condition has occurred (i.e. a variable divided by 0).
4. **NumberFormatException**: Thrown when a non-parsable String or Object tries to be parsed into a type int, double or any numeric variable. 
5. **ClassCastException**: Thrown when one tries to cast a superclass into its subclass. 

How to handle excpetions? Use *try-catch* blocks or use the *throws* keword: 

(syntax) 
```java
try { 
//some code; if an exception occcurs in the code, goes to catch block.
  catch (IndexOutOfBoundsException e) { //or any exceptions
    System.err.println("ExceptionTypeName: " + e.getMessage()); //System.err is the standard error printstream.
  }
}
```
### The SOLID Principle

The SOLID design principles denotes the five fundamental principles that every object-oriented language based code should abide.

- **S**ingle Responsibility Principle (SRP): 

The principle that denotes that a class should have only a single responsibility. Essentially, this prinicple suggests the use of many smaller classes, each with a very specific purpose over the use of larger, broader classes to make the code more modular, reusable, and extensible.

- **O**pen/Closed Principle (OCP): 

The principle that denotes thtat a class should be **closed** for modification but **open** for extension. When one wants to add a new feature to the class, one should subclass the existing class. 

- **L**iskov Substitution Principle (LSP): 

The principle that denotes anywhere an instance of a super class is expected, an instance of one of its subclasses should be able to be substituted. The subclass must not broaden the preconditions or relax the postconditions when the subclass overrides the superclass. 

- **I**nterface Segregation Principle (ISP): 

- **D**ependency Injection Principle (DIP): 

### Do Subclasses inherit private fields? 

Based on this Quora Question [link](http://stackoverflow.com/questions/4716040/do-subclasses-inherit-private-fields) and my question on the extent of applicability of private data fields: 

Per [JLS](https://docs.oracle.com/javase/specs/jls/se8/html/jls-8.html#jls-8.3.1.1) (Java Language Specification): Members of a class that are declared private **are not inherited** by subclasses of that class. Only members of a class that are declared protected or public are inherited by subclasses declared in a package other than the one in which the class is declared. However, the **objects** of the subclasses contain private fields (but they cannot be accessed unless through public getter methods and mutated unless through public setter methods). 

### .equals() method vs == 

In the most simplest sense, .equals() method, located in java.lang.Object, determines whether the two comparing objects' **value** inside String instances are **logically same** and == operator compares the value of **two object references** to see whether they refer to the **same String instance (memory address)**. The .equals() method can be overridden by the coder to allow objects to be compared by any trait they choose (ex. comparing people by their name instance variable).

Use the == operator to determine whether an object has the same memory address as an another object (i.e. to determine whether the objects are **aliases** of each other). 

To override the inherited .equals() method, these concepts must be true: 

1. Reflexive: Any object returns true for this.equals(this) comparing itself with the .equals() method. 
2. Symmetric: If a.equals(b) is true then b.equals(a) must be true. 
3. Transitive: If a.equals(b) and b.equals(c) are true, then a.equals(c) must be true. 
4. Consistent: If a and b do not change between invocations of a.equals(b) or b.equals(a) then each invocation must return the same result
5. Null: a.equals(null) must always return false
6. The compared object must have the same type as the object to return true. (i.e. the a.equals(b) when int a is 5 and double b is 5.0, it returns false). 
7. Hashcode. 

### Covariant Method Overriding! 

First introduced in JDK Version 5, covariant method overriding allows to override methods if the return type of the subclass is the subclass type of the superclass' method whose return type is Non-Primitive.

```java 
```
