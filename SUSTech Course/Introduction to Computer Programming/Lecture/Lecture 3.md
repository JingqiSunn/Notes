#### Lecture 3

**Endless Loop**

```java
int product = 3;
while ( product <= 100 ) {
	int x = 3 * product;
}
```

**Find the Average Scores**

> ```java
> import java.util.Scanner;
> public class ClassAverage {
>     public static void main(String[] args) {
>         Scanner input = new Scanner(System.in);
>         int total;
>         int gradeCounter;
>         int grade;
>         int average;
>         total = 0;
>         gradeCounter = 1;\\Counter-Controlled Repetition
>         while(gradeCounter <= 10) {
>             System.out.print("Enter grade: ");
>             grade = input.nextInt();
>             total += grade;
>             gradeCounter += 1;
>         }
>         average = total / 10;
>         System.out.printf("\nTotal of all 10 grades is %d\n", total);
>         System.out.printf("Class average is %d\n", average);
>     }
> }
> ```
>
> ```
> Enter grade: 5
> Enter grade: 4
> Enter grade: 78
> Enter grade: 4
> Enter grade: 5
> Enter grade: 1
> Enter grade: 56
> Enter grade: 45
> Enter grade: 58
> Enter grade: 25
> 
> Total of all 10 grades is 281
> Class average is 28
> ```

**Find the Average Scores Don't Know the Time**

> ```java
> import java.util.Scanner;
> public class ClassAverage2 {
>     public static void main(String[] args) {
>         Scanner input = new Scanner(System.in);
>         int total;
>         int gradeCounter;
>         int grade;
>         double average;
>         total = 0;
>         gradeCounter = 0;//Sentinel-Controlled Repetition
>         System.out.print("Enter grade or -1 to quit: ");
>         grade = input.nextInt();
>         while(grade != -1) {
>             total += grade;
>         	gradeCounter += 1;
>             System.out.print("Enter grade or -1 to quit: ");
>         	grade = input.nextInt();
>         }
>         if (gradeCounter != 0) {
>             average = (double) total/ gradeCounter;
>             System.out.printf("\nTotal of the %d grades entered is 
> 			%d\n", gradeCounter, total);
>  			System.out.printf("Class average is %.2f\n", average);
>         } else {
>             System.out.println("No grades were entered");
>         }
>     }
> }
> ```
>
> ```
> Enter grade or -1 to quit: -1
> No grades were entered
> ```
>
> ```
> Enter grade or -1 to quit: 4
> Enter grade or -1 to quit: 7
> Enter grade or -1 to quit: 5
> Enter grade or -1 to quit: 8
> Enter grade or -1 to quit: 2
> Enter grade or -1 to quit: 4
> Enter grade or -1 to quit: -1
> 
> Total of the 6 grades entered is 30
> Class average is 5.00
> ```

**Type Cast**

```java
int total;
int gradeCounter;
double average;
average = (double) total / gradeCounter;
\\ the cast operator (double) is superior to binary arithmetic operators, and it will change the type of the total temporary, but it will save it into another copy, so the original value and the type of the total will not be changed and they will be saved in just the same space.
\\ The two side of the binary operator in Java have to be in the same type. So here we will have a implicit conversion, which will change the value type of the gradeCounter to the double. This is called the widening.
```

**Type Promotion**

1. If you define a function that foo(double), if you give a int input, the type of the value will be automatically changed into double.
2. If the binary operator with two different types of input, the compiler will do the widening automatically.

> [!CAUTION]
>
> The target data type will always be wider than the initial data type.
>
> |  Type   |               Valid promotions                |
> | :-----: | :-------------------------------------------: |
> | double  |                     None                      |
> |  float  |                    double                     |
> |  long   |                 float, double                 |
> |   int   |              long, float, double              |
> |  chart  |           int, long, float, double            |
> |  short  |    int, long, float, double(but not char)     |
> |  byte   | short, int, long, float, double(but not char) |
> | boolean |                     None                      |

**Compound Operator**

| Sample Expression |      Explanation       |
| :---------------: | :--------------------: |
|      c += 7       |       c = c + 7        |
|      d -= 4       |       d = d - 4        |
|      e *= 5       |       e = e * 5        |
|      f /= 3       |       f = f / 3        |
|      g %= 9       |       g = g % 9        |
|     b = ++ a      | new a = a+1; b = new a |
|      b = a++      |  b = a; new a = a + 1  |

**Standard Counter-Controlled Repetition with While**

```java
public class WhileCounter {
 public static void main(String[] args) {
 int counter = 1;
 while ( counter <= 10 ) {
 	System.out.printf("%d", counter);
 	++counter;
 }
 System.out.println();
 }
}
```

**Standard Form of For Statement**

```java 
for(initialize the control variable, Loop-Continuation Condition, Increment of control variable){
    Statement;
}
```

**The Standard Form of the Do...While Statement**

```java
do {
    Statements;
} while (Controlling Condition);
\\ Pay attetion to the Semi-colon.
\\ The loop body will be executed at least once.
```

**The Standard Form of the Switch Statement**

```java
switch(Target Variable){
        case'Value of the target variable':
        	Statements;
        case'Value of the target variable'
            Statements;
    	default:
        	Statements;
}
\\ You can it in seperated cases.
\\ Do not forget the break if you need, which is very dangerous, because the compiler will think that all the statements are true.
\\ The part of default is not necessary.
```

