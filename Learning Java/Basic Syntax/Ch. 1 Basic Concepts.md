# Chapter 1: Basic Concepts 

### What is Java? 
Java is a high level, modern programming language designed in the early 1990s by Sun Microsystems, and currently owned by Oracle. Java is **platform independent** and has the catchphrase **Write Once, Run Everywhere.** 

### How to run a simple program in Java? 
The basic steps of running a program in Java is:

  1. The Java compiler reads Java language source (.java) files and translates the source into Java bytecodes, and places the bytecodes into class (.class) files. (command in cmd: `javac filename.java`)
  2. The class files can then be executed on the Java Virtual Machine (JVM). (command in cmd `java filename.class`)

### Hello World program 
A program that prints "Hello, World!" can be written in Java as: 

```Java
public class HelloWorld { //declares that class of the Java file
    public static void main(String[] args) { //the main method 
        System.out.println("Hello, World!"); //prints the "Hello, World!" statement onto console. 
    }
}
```

### Arithmetric operators & Increment/Decrement
Some of the arithmetric operators in Java include addition (`+`), subtraction (`-`), multiplication (`*`), division(`/`), modulo (`%`), plus-equals (`+=`), and minus-equals (`-=`). 

Also, increment (`x = x + 1`) and decrement (`x = x - 1`) can be expressed as ++x or x++ and --x or x--, respectfully. 

### Getting user input
User input on console can be retrieved in the Java language through a "scanner." Example code of retrieving user input in Java is: 

```Java
import java.util.Scanner //imports Scanner class 
// import java.io.File (if the input was a .txt file and not a input in console)
public class RetrieveInput {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in); //initialize a new Scanner instance onto the main class
        // Scanner input = new Scanner(new File(filename)); if reading a .txt file. 
        String inputIn = input.nextline(); //retrieves the nextline of the input on console (assuming it was a String). 
        System.out.println(inputIn);  //prints out the user input 
    }
}
``` 



      
