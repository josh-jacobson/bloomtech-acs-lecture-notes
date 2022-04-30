# Sprint 1: Problem Solving and Basic Data Structures

## Data Types in Java

```java
int myNum = 5;               // Integer (whole number)
float myFloatNum = 5.99f;    // Floating point number (note the 'f' suffix on the number itself)
char myLetter = 'D';         // Character
boolean myBool = true;       // Boolean
String myText = "Hello";     // String
```

Primitive types: boolean, char, int, float, byte, short, long
Object types: String, Array, Class, Interface, etc

### Mutability
To make a variable immutable, add the `final` keyword:
```java
final String a = "Hello" // can't be changed
```

### Booleans

### Converting between data types
Primitive type to String:
```java
float f = 3.14f
String s = String.valueOf(f) // also works for int, char, boolean, others
```

Converting between primitive types:
```java
float a = 3.14f
int b = (int)f
```

String to int:
```java
String s = "123"
int i = Integer.parseInt(s)
```


## Conditional Logic
Comparators in Java: <=, >=, ==
&&, ||

Example if else statement:
```java
if (x <= 12 && y < 15) {
  System.out.println("TRUE");
} else {
  System.out.println("False");
}
```

## Strings

Length of string: `.length()`
```java
String s = "Hello";
System.out.println(s.length(); // 5
```

Slicing out individual characters: `.charAt(index)`
```java
String s = "Hello";
char firstChar = s.charAt(0);
char lastChar = s.charAt(s.length() - 1);
```

Convert the whole string to uppercase or lowercase: `.toUppercase()`, `.toLowercase()`

Concatenation: `newString = string1 + string2`

String comparison: `string1.equals(string2)` (using `==` can lead to strange results)


## Arrays
Length of an array: `a.length`

Access the nth element of an array: `a[n-1]` (indexing starts at 0)
Watch out for "off-by-one" errors that come up frequently when translating between 0-indexing and many real world contexts where indexings starts from 1. These errors are sneaky and can easily result in runtime errors when the index goes "out of bounds". In algorithm problems, it's important to test edge cases and include safety conditions in your logic.

Append a new element to the end of an array (not as easy as other languages):
```java
int[] a = {1, 2, 3};
int[] b = new int[a.length + 1]; // Create a new array, b, with one more slot than a
System.arraycopy(a, 0, b, 0, a.length); // Copy all values from a to b
b[a.length] = 4; // careful for potential off-by-one errors here!
```

Print an array:
```java
import java.util.Arrays; // at the top of your file
System.out.println(Arrays.toString(b)); // [1, 2, 3, 4]
```

## For loops
```java
for(int i = 0; i < 5; i++) {
  System.out.println(i);
}
```
The syntax is just like C++ and other languages based on C, with three clauses within the parentheses:
1. Initialization
2. Looping condition (only continue the loop if this expression evaluates to true)
3. Update expression to run after each iteration of the loop (e.g., increment an index)

If it helps, you can think about this classic for loop structure like this:
```java
for (initialization; condition; update) {
    // body of loop 
}
```

## While Loops



## More resources:
* [The ultimate guide for data structures & algorithm interviews](https://dev.to/rahhularora/the-ultimate-guide-for-data-structures-algorithm-interviews-npo)
* [Big-O Cheat Sheet](https://www.bigocheatsheet.com/)
