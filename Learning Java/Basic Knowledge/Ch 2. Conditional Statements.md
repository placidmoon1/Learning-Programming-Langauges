# Chapter 2: Conditional Statements in Java

### if loop

```java 
if (condition1) { //condition1 is a type boolean 
	//Executes when condition1 is true
} elseif (condition2) { 
	//Executes when condition2 is true
} else { 
   //Executes when both condition1 and condition2 is false
}
```
Logical operators for the condition for the if loop includes more than (`>`), less than (`<`), more than or equal to (`>=`), less than or equal to (`<=`), not equal (`!=`), equal (`==`), and (&&), and or (||). 

### switch loop 

```java
switch (expression) { //expression's type can only be integers, convertable integers (byte, short, char), strings and enums.
	case value 1: 
		//code
		break; //break is optional; breaks the switch loop so that the flow of control of the switch loop does not extend to the next case 
	case value 2: 
		//code
		break;
	default //default is optional; returns code only if expression does not equal to any of the cases. 
		//code
}
```

### while loop 

```java 
while(condition) {
	//run code until condition is false (infinite loops can occur if condition doesn't become false) 
} 
```

### for loop

```java
for (initializing variable; termination condition; increment){
	//run code while terminating condition isn't met
}
```

### do-while loop 

```java
do {
	//some code; guarenteed this loop is ran at least once
} while (a condition); 
```

### Loop Control Statements

1. Continue: Causes the loop to skip the remainder of its body and then immediately retest its condition prior to iterating. 
2. Break: Terminates the loop and transfers execution process to the statement that immediately follows the loop. 
