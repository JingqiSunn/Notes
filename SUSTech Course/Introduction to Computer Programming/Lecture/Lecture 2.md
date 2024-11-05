#### Lecture 2

**If Single -Selection Statement**

```java
if(grade >= 60) {
    System.out.println("Passed");
}
```

**If-Else Double-Selection Statement**

```java
if(grade >= 60) {
    System.out.println("Passed");
} else {
    System.out,println("Failed");
}
```

**The Shorthand of If-Else Double-Selection Statement**

```java
string result = studentGrade >= 60? "Passed" : "Failed";
```

**Nested If Statement**

```java
if(score >= 90.0) {
    System.out.print("A");
} else {
    if(score >= 80.0) {
        System.out.print("B");
    } else {
        if(score >= 70.0) {
            System.out.print("C");
        } else {
            if(score >= 60.0) {
                System.out.print("D");
            } else {
                System.out.print("F");
            }
        }
    }
}
```

**A More Elegant Version of Multi-If Statement**

```java
if(score >= 90.0) {
    System.out.println("A");
} else if(score >= 80.0) {
    System.out.println("B");
} else if(score >= 70) {
    System.out.println("C");
} else if(score >= 60) {
    System.out.println("D");
} else {
    System.out.println("F");
}
```

**while Repetition Statement**

```java
int product = 3;
while(product <= 100) {
    product = 3 * product;
}
System.out.println("The number of the product is " + product)
```

**Class Average**

```java
import java.util.Scanner;
public class ClassAverage {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double totalGrade = 0;
        int gradeCounter = 1;
        double average;
        While(gradeCounter <= 10) {
            System.out.println("The Grade: ");
            grade = input.nextInt();
            totalGrade += grade;
            gradeCounter += 1;
        }
        average = totalGrade / 10 + totalGrade % 10;
        System.out.printf("\n The Total score of the class is %d", totalGrade);
        System.out.printf("\n The average grade of the class is %d \n", average);
    }
}
```

**Class Average Official Version**

```java
import java.util.Scanner;
public class ClassAverage {
    public static void main(String[] args) {
        // create Scanner to obtain input from command window
        Scanner input = new Scanner(System.in);
        int total; // sum of grades entered by user
        int gradeCounter; // number of the grade to be entered next
        int grade; // grade value entered by user
        int average; // average of grades
        // initialization phase
        total = 0; // initialize total
        gradeCounter = 1; // initialize loop counter
        while(gradeCounter <= 10) { // loop 10 times
            System.out.print("Enter grade: "); // prompt
            grade = input.nextInt(); // input next grade
            total = total + grade; // add grade to total
            gradeCounter = gradeCounter + 1; // increment counter by 1
        } // end while
        // termination phase
        average = total / 10; // integer division yields integer result
        // display total and average of grades
        System.out.printf("\nTotal of all 10 grades is %d\n", total);
        System.out.printf("Class average is %d\n", average);
    } // end main
} // end class ClassAverage
```

