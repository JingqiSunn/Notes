#### A Better View on the Print Format

Here comes an example first.

> ```java
> public class TryFormatType {
>     public static void main(String[] args) {
>         double pi = Math.PI;
>         System.out.printf("%-20s%-20s%-20s\n", "radius", "perimeter", "area");
>         System.out.printf("%-20d%-20.4f%-20.4f\n", 1, 2 * pi * 1, pi * 1 * 1);
>         System.out.printf("%-20d%-20.4f%-20.4f\n", 2, 2 * pi * 2, pi * 2 * 2);
>         System.out.printf("%-20d%-20.4f%-20.4f\n", 3, 2 * pi * 3, pi * 3 * 3);
>         System.out.printf("%-20d%-20.4f%-20.4f\n", 4, 2 * pi * 4, pi * 4 * 4);
>    	}
> }
> ```
>
> ```
> radius              perimeter           area
> 1                   6.2832              3.1416
> 2                   12.5664             12.5664
> 3                   18.8496             28.2743
> 4                   25.1327             50.2655
> ```

**The Standard Form of Format Specifier**

% [flags] [width] [.precision] conversion-character                  ( square brackets denote optional parameters )

**Flags**

| Sign  |                           Meaning                            |
| :---: | :----------------------------------------------------------: |
|   -   |         left-justify ( default is to right-justify )         |
|   +   | output a plus ( + ) or minus ( - ) sign for a numerical value |
|   0   | forces numerical values to be zero-padded ( default is blank padding ) |
|   ,   |        comma grouping separator (for numbers > 1000)         |
| Space | space will display a minus sign if the number is negative or a space if it is positive |

**Width**

Specifies the field width for outputting the argument and represents the minimum number of characters to  be written to the output. Include space for expected commas and a decimal point in the determination of  the width for numerical values.

**Precision**

Used to restrict the output depending on the conversion. It specifies the number of digits of precision when  outputting floating-point values or the length of a substring to extract from a String. Numbers are rounded  to the specified precision.

**Conversion-Character**

| Conversion-Character |                 Data Type                 |        Subtypes        |                       Other Notations                        |
| :------------------: | :---------------------------------------: | :--------------------: | :----------------------------------------------------------: |
|          d           |              decimal integer              | byte, short, int, long |                             Null                             |
|          f           |           floating-point number           |     float, double      |                             Null                             |
|          c           |             character Capital             |          Null          |                 C will uppercase the letter                  |
|          s           |             String Capital S              |          Null          | String Capital S will uppercase all the letters in the string |
|          h           |                 hashcode                  |          Null          | A hashcode is like an address. This is useful for printing a reference |
|          n           |                  newline                  |          Null          | Platform specific newline character- use %n instead of \n for greater compatibility |
|          b           |                  boolean                  |          Null          | String Capital B will uppercase all the letters in the boolean value |
|          %           |                   Null                    |          Null          |                       Insert a % sign                        |
|          x           |               Hexa-Decimal                |          Null          |                                                              |
|          e           |            Scientific Notation            |          Null          | String Capital E will uppercase all the letters in the scientific notation value |
|          t           |                 Time/Date                 |          Null          |                                                              |
|          o           |               Octal Integer               |          Null          |                                                              |
|          g           | floating-point number/Scientific Notation |          Null          | Causes Formatter to use either %f or %e, whichever is shorter |
|          a           |        Floating-point hexadecimal         |          Null          |                                                              |

**Example**

> ```java
> public class PrintFormat {
>     public static void main(String[] args) {
>         int testInteger = 123456789;
>         float testFloat = 1.245990878f;
>         String testString = "JingqiSUN";
>         System.out.printf("%d\n",testInteger);
>         System.out.printf("%20d\n",testInteger);
>         System.out.printf("%-20d\n",testInteger);
>         System.out.printf("%+d\n",testInteger);
>         System.out.printf("%+20d\n",testInteger);
>         System.out.printf("%,d\n",testInteger);
>         System.out.printf("%,20d\n",testInteger);
>         System.out.printf("%,020d\n",testInteger);
>         System.out.printf("%,+020d\n",testInteger);
>         System.out.printf("%,+-20d\n",testInteger);
>         System.out.printf("%,-+20d\n",testInteger);
>         System.out.printf("%f\n",testFloat);
>         System.out.printf("%.7f\n",testFloat);
>         System.out.printf("%+-20.7f\n",testFloat);
>         System.out.printf("%+020.7f\n",testFloat);
>         System.out.printf("%s\n",testString);
>         System.out.printf("%S\n",testString);
>     }
> }
> ```
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240616141112306.png" alt="image-20240616141112306" style="zoom:40%;" />

**Other Resources**

https://www.geeksforgeeks.org/format-specifiers-in-java/

https://www.cs.colostate.edu/~cs160/.Summer16/resources/Java_printf_method_quick_reference.pdf

