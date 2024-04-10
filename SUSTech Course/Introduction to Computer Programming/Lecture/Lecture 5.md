#### Lecture 5

**Reference Rules in Array**

```java
int[] list1 = {1,2,3,4,5};
int[] list2 = {6,7,8,9};
list2 = list1;
System.out.print("Arrays.toString(list2)");
list1[1] = 90;
System.out.print("Arrays.toString(list2)");
```

```
[1,2,3,4,5]
[1.90,3,4,5]
```

**Two-Dimensional Arrays**

```java
int[][] newArray = new int[rows][Columns];
int[][] gradeBook = new int[50][6];
gradeBook[1][2] = 77;
int[][] a = new int[][]{{1,2}{3,4}};
a[0] = {1,2}; // It is telling to give out the first row.
a[0].length; // It is coming out with the value of the number of the columns.
int[][] newArray = new int[][]{{1}{2,3}{3,4,5}}; // It allows each rows to have difference numbers of columns, it can be called the Ragged Arrays.
```

**Computing Average Score for Each Student**

```java
public static void main(String[] args) {
 int[][] gradebook = {
 {87, 96, 70, 68, 92},
 {85, 75, 83, 81, 52},
 {69, 77, 96, 89, 72},
 {78, 79, 82, 85, 83}
 };
 for(int[] grades : gradebook) {
 int sum = 0;
 for(int grade : grades) {
 sum += grade;
 }
 System.out.printf("%.1f\n", ((double) sum)/grades.length);
 }
}
```

**Three-Dimensional Arrays**

```java
int[][][] a = new int[3][4][5];
```

**The Standard Form of a Method**

```java
Modifier ReturnType MethodName (Parameters) {
    Statements;
    Return ReturnType;
}
```

**Example of Method**

```java
public static void main(String[] args) {
 int a = 3;
 System.out.println("Before: " + a);
 triple(a);
 System.out.println("After: " + a);
}
public static void triple(int x) {
 x *= 3;
}
```

**Example of Method Two**

```java
public static void main(String[] args) {
 int[] a = {1, 2, 3};
 System.out.println("Before: " + Arrays.toString(a));
 
 triple(a);
 System.out.println("After: " + Arrays.toString(a));
}
public static void triple(int[] x) {
for(int i = 0; i < x.length; i++) 
x[i] *= 3;
}
```

```
Before: [1,2,3]
After: [3,6,9]
```

**Ellipse**

```java
public static double average(double... numbers) {
 double total = 0.0;
 for(double d : numbers) total += d;
 return total / numbers.length;
}
public static void main(String[] args) {
 double d1 = 10.0, d2 = 20.0, d3 = 30.0;
 System.out.printf("average of d1 and d2: %f\n", average(d1, d2));
 System.out.printf("average of d1 ~ d3: %f\n", average(d1, d2, d3));
}
```

The compiler will look numbers as an array.