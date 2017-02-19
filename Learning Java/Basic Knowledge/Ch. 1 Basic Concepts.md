# Chapter 1: Basic Concepts 

## What is Java? 
Java is a high level, modern programming language designed in the early 1990s by Sun Microsystems, and currently owned by Oracle. Java is **platform independent** and has the catchphrase **Write Once, Run Everywhere.** 

## How to run a simple program in Java? 
The basic steps of running a program in Java is:

  1. The Java compiler reads Java language source (.java) files and translates the source into Java bytecodes, and places the bytecodes into class (.class) files. (command in cmd: `javac filename.java`)
  2. The class files can then be executed on the Java Virtual Machine (JVM). (command in cmd `java filename.class`)

## Hello World program 
A program that prints "Hello, World!" can be written in Java as: 

```Java
public class HelloWorld { //declares that class of the Java file
    public static void main(String[] args) { //the main method 
        System.out.println("Hello, World!"); //prints the "Hello, World!" statement onto console. 
    }
}
```

dd

