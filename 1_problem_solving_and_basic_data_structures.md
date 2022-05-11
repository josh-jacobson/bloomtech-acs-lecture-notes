# Sprint 1: Problem Solving and Basic Data Structures

## Data Types in Java

```java
int myNum = 5;               // Integer (whole number)
float myFloatNum = 5.99f;    // Floating point number (note the 'f' suffix on the number itself)
char myLetter = 'D';         // Character
boolean myBool = true;       // Boolean
String myText = "Hello";     // String
```

Primitive types (aka literals): boolean, char, int, float, byte, short, long

Object types: String, Array, Class, Interface, etc

### Wrapper classes
Each primitive type has a corresponding "wrapper class" for use in Collections and other advanced data structures (primitive types cannot be used in these directly).

* Primitive types: byte, short, int, long, float, double, boolean, char
* Wrapper classes: Byte, Short, Integer, Long, Float, Double, Boolean, Character

Note that primitive types have a default value, but wrapper class objects are null until assigned a value. You'll find that many common operations in algorithm problems (e.g., sorting an array) will require explicit or implicit conversion between primitive types and wrapper classes.

When this wrapping / unwrapping behavior is done by the Java compiler automatically, it's called "Autoboxing" and "Unboxing". Be aware of the memory and performance implications of this, as it can unexpectedly add a lot of overhead to your programs!

### Mutability
To make a variable immutable, add the `final` keyword:
```java
final String a = "Hello" // can't be changed
```

### Booleans

### Converting between data types
Number to String:
```java
float f = 3.14f
String s = String.valueOf(f) // also works for int, char, boolean, others
// Or this also works:
String s2 = Float.toString(f);
```

Converting between number types:
```java
// float to int (rounding rather truncation):
float a = 3.14f;
int b = Math.round(a); // 3
// int to double (convert before division and other arithemtic ops that can be lossy with integers)
int i = 3
int j = 4
double threeFourths = (double)i / (double)j // returns 0.75 (with integer division would truncate to 0!)

```

### String to int:
```java
String s = "123"
int i = Integer.parseInt(s)
```

### String to float:
```java
String s = "1.34"
float f = Float.parseFloat(s)
// or:
float f2 = Float.valueOf(s)
```

### char to String:
There are quite a few different ways to do this, some more efficient than others! The `String.valueOf` class method is the best way, and `Character.toString` works similarly well. Here are all the ways to do this, from best to worst:
```java
char c = 'a';
String s = String.valueOf(c);             // fastest + most memory efficient
String s = Character.toString(c);
String s = new String(new char[]{c});
String s = String.valueOf(new char[]{c});
String s = new Character(c).toString();
String s = "" + c;                        // slowest + least memory efficient
```

## Conditional Logic
Comparators in Java: <=, >=, ==

When comparing objects, use `.equals()` instead of `==`

Logical and/or: &&, ||

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
Length of an array of primitives (int, float, boolean, etc): `a.length`
Length of an array of objects (String, Integer, etc): `a.length()`

Access the nth element of an array: `a[n-1]` (indexing starts at 0)

Watch out for "off-by-one" errors that come up often when translating between 0-indexing and many real world contexts where indexings starts from 1. These errors are sneaky and can easily result in runtime errors when the index goes "out of bounds". In algorithm problems, it's important to test edge cases and include safety conditions in your logic.

Append a new element to the end of an array (not as easy as other languages):
```java
int[] a = {1, 2, 3};
int[] b = new int[a.length + 1]; // Create a new array, b, with one more slot than a
System.arraycopy(a, 0, b, 0, a.length); // Copy all values from a (starting at index 0) to b (starting at index 0) 
b[a.length] = 4; // careful for potential off-by-one errors here!
```

Print an array:
```java
import java.util.Arrays; // at the top of your file
System.out.println(Arrays.toString(b)); // [1, 2, 3, 4]
```

Array filtering (use an array stream with built-in filter method)
Example: filter array a to only include even elements.
```java
int b[] = Arrays.stream(b).filter(n -> (n % 2 == 1)).toArray();
```


ArrayList (dynamic array)
```java
// Make an ArrayList from an Integer array:
ArrayList<Integer> arrayList = new ArrayList<Integer>(Arrays.asList(a));
```

Array delete:
```java
int[] solution(int[] a, int index) {
  int b[] = new int[a.length -1];
  
  for (int i=0, j=0; i<a.length; i++) {
    if (i != index) {
      b[j++] = a[i];
    }
  }
  return b;
}
```

### min and max values of an int array
This is not straightforward in Java as it is in higher-level languages like Python, Ruby and JavaScript.
You could write a for loop to look through and manually find the max/min value. But these one-liners are helpful to pop into a CodeSignal algo problem and save some time!
```java
int[] array = {16, 1, 4, 8}
int min = Arrays.stream(array).min().getAsInt(); // 1
int max = Arrays.stream(array).max().getAsInt(); // 16
```

Remember to import the Arrays utility library with `import java.util.Arrays;` at the top of your file (not necessary in a sandbox env like CodeSignal)

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
```java
// initialize variables outside the loop
int i = 0;
int n = 5;
// Loop while condition is true
while(i<5) {
  System.out.println(i);
  i++;
}
```

## More resources:
* [The ultimate guide for data structures & algorithm interviews](https://dev.to/rahhularora/the-ultimate-guide-for-data-structures-algorithm-interviews-npo)
* [Big-O Cheat Sheet](https://www.bigocheatsheet.com/)
* [15 Useful Code Snippets for Java Developers](https://jaxenter.com/15-useful-code-snippets-java-developers-131796.html)
* [Java Algorithms](https://www.programiz.com/java-programming/algorithms)
* [Java: Understanding Primitive Types and Wrapper Objects](https://medium.com/@bpnorlander/java-understanding-primitive-types-and-wrapper-objects-a6798fb2afe9#:~:text=Java%20defines%20eight%20primitive%20data,a%20fixed%20value%20in%20memory.)
* [Java ParseInt vs ValueOf](https://www.youtube.com/watch?v=GJroayuTM4E&ab_channel=LemubitAcademy)
