# Sprint 2: Array and Looping Techniques

## Arrays in Java
```java
int[] a = {1, 2, 3};
int length = a.length;
int secondElement = a[1] // 2
```

Arrays are fixed-length in Java, so adding/removing elements or any other operations that would change the overall array length require building an entirely new array.

For example, to append a new element to the end of an array:
```
int[] a = {1, 2, 3};
int[] b = new int[a.length + 1]; // Create a new array, b, with one more slot than a
System.arraycopy(a, 0, b, 0, a.length); // Copy all values from a (starting at index 0) to b (starting at index 0) 
b[a.length] = 4; // careful for potential off-by-one errors here!
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

Print an array:
```java
import java.util.Arrays; // at the top of your file
System.out.println(Arrays.toString(b)); // [1, 2, 3, 4]
```

Array filtering (use an array stream with built-in filter method) Example: filter array a to only include even elements.
```java
int b[] = Arrays.stream(b).filter(n -> (n % 2 == 1)).toArray();
```
## ArrayList (dynamic array)
```java
// Make an ArrayList from an Integer array:
ArrayList<Integer> arrayList = new ArrayList<Integer>(Arrays.asList(a));
```

## Streams

## Comparators
Array equality:
```java
int[] a = new int[] {1, 2, 3, 4};
int[] b = new int[] {1, 2, 3, 4};
return Arrays.equals(a,b); // true
```

## Advanced type conversions:
String to char array: `toCharArray()` instance method
```java
    String s = "abcd"; 
    return s.toCharArray(); // ['a', 'b', 'c', 'd']
```

## Multidimensional Arrays

## Moving Window Techniques

## Helpful resources
* [Math is Fun - Number Bases](https://www.mathsisfun.com/numbers/bases.html)
* [ASCII Table](https://www.ascii-code.com/)
* 
