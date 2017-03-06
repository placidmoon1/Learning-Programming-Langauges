# Java Pro Tips & Interesting Quirks 

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
/** The following continue statement breaks out of the inner
* loop if (i * j > 50) and starts a new iteration of the outer
*/ loop if i < 10 is true after i is incremented by 1. 

 ```
 
 
