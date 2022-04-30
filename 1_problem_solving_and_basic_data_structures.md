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

### Arrays

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


## For loops

## While Loops



## More resources:
* [The ultimate guide for data structures & algorithm interviews](https://dev.to/rahhularora/the-ultimate-guide-for-data-structures-algorithm-interviews-npo)
* [Big-O Cheat Sheet](https://www.bigocheatsheet.com/)
