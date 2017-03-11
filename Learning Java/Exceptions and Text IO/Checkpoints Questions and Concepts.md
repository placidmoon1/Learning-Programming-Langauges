#Chapter 12: Exception Handling and Text I/O 

- *Runtime Errors* occur while a programing is running if the JVM detercts an operation that is impossible to carry out; these erros are thrown as exceptions. An *exception* is an object that represents an error or a condition that prevents execution from proceeding normally. If the exception is not handled, the program would terminate abnormally.
- *Compile-time Errors*, also known as checked errors are errors that need to be fixed before the code is run. 

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
