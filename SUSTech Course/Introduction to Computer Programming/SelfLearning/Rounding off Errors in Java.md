#### Rounding off Errors in Java

**Basic Reasons**

| Class of Information | Memorizing Space |
| :------------------: | :--------------: |
|        Float         | 8 Bytes/32 Bits  |
|        Double        | 16 Bytes/64 Bits |

**Example for Rounding Off Error**

```java
public class Main{
   public static void main(String[] args) {
      double data1 = 0.30;
      double data2 = 0.20 + 0.10;
      System.out.println("Value after addition: " + data2);
      System.out.println(data1 == data2);
      double data3 = 0.50;
      double data4 = 0.10 + 0.10 + 0.10 + 0.10 + 0.10;
      System.out.println("Value after addition: " + data4);
      System.out.println(data3 == data4);
   }
} 
```

```
Value after addition: 0.30000000000000004
false
Value after addition: 0.5
true
```

```java
public class Main {
   public static void main(String[] args) {
      double data1 = 4.30452;
      double data2 = 0.503542;
      double res = data1 + data2;
      System.out.println("Value after addition: " + res);
   }
}
```

```
Value after addition: 4.8080620000000005
```

**Reason For Errors**

The ‘IEEE 754’ is a standard that is followed by Java while implementing floating point numbers. According to its ‘Rounding’ rule, when than value of mantissa is greater than 23 bits then it adds 1 to the 23rd bit to round the value. Here, the mantissa is the binary representation of fractional digits.

This is the reason why we are getting different values.

**Solution For the Error**

1. BigDecimal

   *Definition: It is a class that can be used in the place of floating point numbers like float and double. We can perform all the normal operations that float and double datatypes provide. For example, arithmetic operations, comparison and rounding. It can handle these operations with accurate precision.*

   > ```java
   > import java.math.*;
   > public class Main{
   >    public static void main(String[] args) {
   >       BigDecimal data1 = new BigDecimal("0.20");
   >       BigDecimal data2 = new BigDecimal("0.10");
   >       BigDecimal res = data1.add(data2); // performing addition
   >       System.out.println("Value after addition: " + res);
   >    }
   > }
   > ```
   >
   > ```
   > Value after addition: 0.30
   > ```

2. Math.round()

   *Definition: It is a static method of class ‘Math’. It takes a floating point value as an argument and returns the nearest integer value. We call it using its class name.*

   > ```java
   > public class Main {
   >    public static void main(String[] args) {
   >       double data1 = 4.30452;
   >       double data2 = 0.503542;
   >       double res = data1 + data2;
   >       System.out.println("Value after addition: " + res);
   >       System.out.println("Value after rounding off the addition: " + Math.round(res));
   >    }
   > }
   > ```
   >
   > ```
   > Value after addition: 4.8080620000000005
   > Value after rounding off the addition: 5
   > ```

**More Information**

https://www.tutorialspoint.com/rounding-off-errors-in-java

