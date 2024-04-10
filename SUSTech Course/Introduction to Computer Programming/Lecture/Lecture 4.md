#### Lecture 4

**The Break Statement**

```java
public class BreakTest {
 public static void main(String[] args) {
 int count;
 for(count = 1; count <= 10; count++) {
 if(count == 5) {
break; 
 }
 System.out.printf("%d ", count);
 }
 System.out.printf("\nBroke out of loop at count = %d\n", count);
 }
}
```

**The Continue Statement**

```java
public class ContinueTest {
 public static void main(String[] args) {
 for(int count = 1; count <= 10; count++) { // loop 10 times
 if(count == 5) {
continue; // skip remaining code in the loop if count == 5
 }
 System.out.printf("%d ", count);
 }
 System.out.println("\nUsed continue to skip printing 5");
 }
}
```

The continue statement will skip the later part of the loop for this time  and directly start the next time.

**Logical Operators**

| Operator |     Name     |     Description     |
| :------: | :----------: | :-----------------: |
|    !     |     not      |  logical negation   |
|    &&    |     and      | logical conjunction |
|   \|\|   |      or      | logical disjunction |
|    ^     | exclusive or |  logical exclusion  |

*And* has a higher precedence than the *Or* operator.

Normally it will be activated from left to right.

**Short Circuit Evaluation of && and ||**

**No Short Circuit Evaluation of & and |**

**Print Zero**

```java
int b = 0, c = 0;
if(true || b == (c = 6)) { 
 System.out.println(c); // what's c's value?
}
```

**Print** **Six**

```java
int b = 0, c = 0;
if(true | b == (c = 6)) {
 System.out.println(c); // what's c's value?
}
```

**Array**

Each array is a object rather than a simple value, which is called a reference types.

**The Standard Form of Array**

ElementType[] variableName;

**Examples**

```java
int[] intArray;

double[] doubleArray;

String[] stringArray;
```

**Examples of Creating an Array**

```java
int[] c = new int[12];
int[] n = new int[]{ 10, 20, 30, 40, 50 };

```

when you create a array, the element inside of it will be initialized to be the default value of that type of the element.

**Example of Using Array**

```java
import java.util.Random;
public class DiceRolling {
 public static void main(String[] args) {
 Random generator = new Random();
 int[] frequency = new int[6];
 // roll 6000 times; use dice value as frequency index
 for(int roll = 1; roll <= 6000; roll++) {
 int face = generator.nextInt(6);
 frequency[face]++;
 }
 System.out.printf("%s%10s\n", "Face", "Frequency");
 // output the frequency of each face
 for(int face = 0; face < frequency.length; face++) {
 System.out.printf("%4d%10d\n", face+1, frequency[face]);
 }
 }
}
```

**For Each Statement is very important for the array statement**