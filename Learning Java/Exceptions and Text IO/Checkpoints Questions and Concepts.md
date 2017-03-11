# Chapter 12: Exception Handling and Text I/O 

- *Runtime Errors* occur while a programing is running if the JVM detercts an operation that is impossible to carry out; these erros are thrown as exceptions. An *exception* is an event that represents an error or a condition that prevents execution from proceeding normally. If the exception is not handled, the program would terminate abnormally.
- *Compile-time Errors*, also known as checked errors are errors that need to be fixed before the code is run. 

### Exception Handling
Excpetion-Handling can be done through if loops, methods, or others.

i.e. to handle ArithmetricException one can do: 

```java
//if loop example, assume there is already a codeblock and the variable number is defined already

if (int number != 0) {
  System.out.println (2/number); 
} else { 
   System.out.println("Divisor cannot be zero.");
}

//method example 

public static int quotient(int number1, int number2) {
  if (number == 0) {
    System.out.println("Divisor cannot be zero");
    System.exit(1);
  }
}
```

However, the good looking way of handing exceptions are using the `try-catch` block or `throw(s)` keyword. If an exception occurs, one can `throw new exceptiontype("Some Words").` When an exception is thrown, the normal execution is interuptted. Or one can use the try-catch block by using **try** to catch a code and when an excpetion occurs, and **catch** the specific exception to do something about it. When a catch is triggered, the program control would execute the code inside the catch block and move on to the next line. 

An example template of a try-catch-thro block is: 
```java
try {
  //Some code to run that might throw an exception 
}
catch (someType ex) { 
  Code to process when an exception of type someType is thrown 
}
```
- What is the advantage of using exception handling? 

 It enables a method to throw an exception to its caller. The caller can handle this exception. Without this capability, the called method itself must handle the exception or terminate the program. Often the called method does not know how to handle the exception. So it needs to pass the exception to its caller for handling.
 
 - What would happen when a value is added to a max value of a numeric type?
 
 No exceptions will be thrown; rather, it would result into a numeric overflow. Basically, it would wrap around the number and start as a negative. 
 
 
### Exception Types 

The throwable class (subclass of java.lang.Object) is the superclass for exceptions (can be handled by try-catch blocks) and errors (**can't** be handled by codes; **must** be fixed before code runs. The **run-time exception** is a subclass of exceptions and is an unchecked exception in compilation. 

### More on Exception Handling 

Exception-handling model of Java is based on three operations: declaring an exception, throwing an exception, and catching an exception. 

```java 
//EXAMPLE OF EXCEPTION HANDLING 

method1() {
  try {
    invoke method2; 
  }
  catch (Exceptiontype ex) {
    Process Exception; 
  }
}

method2() throws Exception{ 
  if (an error occurs) { 
    throw new Exception();
  }
}
```

The *throws* keyword indicates that a method might throw an exception. It is defined in the header of the method. If it might throw multiple exceptions, separate them using commas. e.g. `public void myMethod() throws Exception1, Exception2, ..., ExceptionN`. The *throw* keyword is the keyword to throw an exception. 

A program that detects an error can create **an instance** of an appropriate exception type and throw it. 
For example, 

```java
IllegalArgumentException ex = 
  new IllegalArgumentException("Wrong Argument"); 
throw ex; 
//////////////////////////////////////////////////
//the shorter way 
throw new IllegalArgumentException("Wrong Argument");  
```
