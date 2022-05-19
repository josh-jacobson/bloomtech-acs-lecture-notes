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
System.out.println(Arrays.toString(b)); // [1, 2, 3, 4]
```

Sort an array in-place:
```java
Arrays.sort(a);
```

Create a sorted version of an array (without modifying the original):
```java
int[] b = Arrays.stream(a).sorted().toArray();
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

## Advanced Comparisons and Conversions
Array equality:
```java
int[] a = new int[] {1, 2, 3, 4};
int[] b = new int[] {1, 2, 3, 4};
return Arrays.equals(a,b); // true
```

String to char array: `toCharArray()` instance method
```java
    String s = "abcd"; 
    return s.toCharArray(); // ['a', 'b', 'c', 'd']
```

Does array contain a specified value?
```java
int[] arr = new int[] {6,1,4};
Arrays.sort(arr); // runtime complexity: O(n * log n)

boolean check(int value, int[] sortedArr) {
    int res = Arrays.binarySearch(sortedArr, value); // runtime complexity: O(log n)
    System.out.println(res);
    return (res >= 0);
}

return check(2, arr); // false 
// total runtime complexity: O(n + n log n) = O(n log n)
```
For some algo problems you'll perform an operation like this many times, for example removing elements from a larger array that appear in a "filter list". In this case, be sure to sort the filter list just once rather than sorting every time within the check method to avoid ballooning runtime.

## Multidimensional Arrays
```java
int[][] twoDimensional = {
  {1, 2, 3},
  {4, 5, 6},
  {7, 8, 9}
}
// access elements with [row][col]
return twoDimensional[2][1]; // 8

// print an entire row (helpful for debugging if you ever get confused!)
System.out.println(Arrays.toString(twoDimensional[0])); // [1, 2, 3]
```

To loop through a multi-dimensional array and do something for each row:
```java
// think of this loop as "for each row in the 2 dimensional array:"
for (int[] row: twoDimensional) {
   System.out.println(Arrays.toString(row));
}

```

## Moving Window Techniques
The key insight for a variable window size is knowing how to adjust your indexing.

For most problems, when we don't want the window to go "out of bounds":
Loop condition: until i < a.length - (window_size - 1)
Size of result array: a.length - (window_size - 1)


## Helpful resources
* [Java Docs - Arrays](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html)
* [Arrays stream() method in Java](https://www.geeksforgeeks.org/arrays-stream-method-in-java/)
* [Reverse an Array in Java](https://www.geeksforgeeks.org/reverse-an-array-in-java/)
