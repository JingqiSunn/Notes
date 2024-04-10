#### Lecture 7

**An Example of Object-Oriented-Programing **

> This is an example about pet.
>
> ```java
> public class Dog {
> 	private String name;
> 	private String breed;
> 	public Dog(String name, String breed) {
> 		this.name = name;
> 		this.breed = breed;
> 	}
>     public void selfIntro() {
>  	System.out.printf("My name is %s. I am a %s.\n", name, breed);
>  	}
> }
> ```
>
> ```java
> public class PetShow {
> public static void main(String[] args) {
> 	Dog dog1 = new Dog("Fluffy", "poodle");
> 	Dog dog2 = new Dog("Alfred", "hound");
> 	dog1.selfIntro();
> 	dog2.selfIntro();
> 	}
> }
> ```

> This is an example about bank account.
>
> ```java
> public class Account {
> 	private double balance;
> 	public Account(double initialBalance) {
> 		if(initialBalance > 0.0) balance =
> 		public void deposit(double amount) {
> 		balance += amount;
> 	}
> 	public double getBalance() {
> 		return balance;
> 	}
> }
> ```
>
> ```java
> import java.util.Scanner;
> 
> public class AccountTest {
>     public static void main(String[] args) {
>         Account account1 = new Account(50.00);
>         Account account2 = new Account(-7.53);
>         System.out.printf("account1 balance: $%.2f\n", account1.getBalance());
>         System.out.printf("account2 balance: $%.2f\n\n", account2.getBalance());
>         Scanner input = new Scanner(System.in);
>         double depositAmount;
>         System.out.print("Enter deposit amount for account1: ");
>         depositAmount = input.nextDouble();
>         System.out.printf("\nadding %.2f to account1 balance\n\n", depositAmount);
>         account1.deposit(depositAmount);
>         System.out.printf("account1 balance: $%.2f\n", account1.getBalance());
>         System.out.printf("account2 balance: $%.2f\n\n", account2.getBalance());
>         System.out.print("Enter deposit amount for account2: ");
>         depositAmount = input.nextDouble();
>         System.out.printf("\nadding %.2f to account2 balance\n\n", depositAmount);
>         account2.deposit(depositAmount);
>         System.out.printf("account1 balance: $%.2f\n", account1.getBalance());
>         System.out.printf("account2 balance: $%.2f\n\n", account2.getBalance());
>         input.close();
>     }
> }
> ```

**Primitive Types versus Reference Types**

Besides the eight primitive data types, the rest are the reference data types.

The default type of a reference type data is null, which has no meanings.

**Char[]**

Char represents a character and you can use the Unicode to describe them, not every characters are on your key board, then you can use the Unicode.

*The Standard ways to include the Unicode*

```java
char c1 = '\u0030';
char c2 = '\u0041';
char c3 = '\u4e2d';
char c4 = '\u56fd';
System.out.printf("%c %c %c %c", c1, c2, c3, c4);
```

```java
"I \u2665 Java programming"
```

**String and StringBuilder**

The difference between them is that the String variables can not be changed during the runtime while the StringBuilder can.

**String**

There are a few things about the String.

1. String represents a string of characters
2. String is a predefined class in Java.
3. String is a reference type

*String has a large amount of Constructors*.

> Here are some examples.
>
> 1. String s1 = new String("hello world");
> 2. String s2 = new String();
> 3. String s3 = new String(s1);
> 4. char[] charArray = {'h', 'e', 'l', 'l', 'o'};
> 5. String s4 = new String(charArray);
> 6. String s5 = new String(charArray, 3, 2);

> [!IMPORTANT]
>
> There is only one memory space unchanged for a String, that is why the case below is correct.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240402111227360.png" alt="image-20240402111227360" style="zoom:50%;" />

> [!IMPORTANT]
>
> When it is about the String variable, the sentence "s1 == s2" is just comparing the reference data. 

When you use a constructor, then we will find that we can create a new object which has the same value of Java but in a difference memory slot.

However every String without using a new method will be saved to the same constant pool, which will share a same value memorizing space.

*Immutability*

> [!WARNING]
>
> The things in the constant pool will not change, what will change is just the reference data.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240402112504714.png" alt="image-20240402112504714" style="zoom:50%;" />

**Some Method Of String**

```java
System.out.printf("\nLength of s1: %d", s1.length());
```

```java
System.out.printf("%c", s1.charAt(count));
```

```java
void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)
Copies characters from this string into the destination character array.
```

> [!WARNING]
>
> It will not take the value in srcEnd.
>
> And the object char[] dst has to be defined ahead.

**Equals Method**

> Here are two examples.
>
> ```java
> String s1 = "Hello World";
> String s2 = s1 + "";
> if(s1.equals(s2)) System.out.println("s1 = s2"); 
> ```
>
> ```java
> String s1 = "hello";
> String s2 = "HELLO";
> if(s1.equals(s2)) System.out.println("s1 = s2");
> ```
>
> ```java
> String s1 = "hello";
> String s2 = "HELLO";
> if(s1.equalsIgnoreCase(s2)) System.out.println("s1 = s2");
> ```

**Comparing Strings**

When two Strings has different length then we will say that the longer one is the bigger.

When two Strings has the same length then we can use the uniCode comparison from left to right.

```java
String s1 = "hello";
String s2 = "HELLO";
int result = s1.compareTo(s2); 
```

The result is 32, which is the s1(hex) - s2(hex) when you find the difference in the uniCode or the length of the String.

> [!CAUTION]
>
> The UniCode comes first then the length of the String

**startswitch & endswitch Method**

Here we have some examples.

```java
String s1 = "Hello World";
if(s1.startsWith("He")) System.out.print("true"); 
```

```java
String s1 = "Hello World";
if(s1.startsWith("llo", 2)) System.out.print("true"); 
```

```java
String s1 = "Hello World";
if(s1.endsWith("ld")) System.out.print("true"); 
```

One important thing is that we can actually specify the location of the start point.

Or it will be defaulted to be zero.

**indexOf & lastIndexOf Method**

I will just give you some examples.

```java
String s = "abcdefghijklmabcdefghijklm";
System.out.println(s.indexOf('c'));
System.out.println(s.indexOf('$'));
System.out.println(s.indexOf('a', 1));
```

you can actually specify the sequence of the target that you are looking for.

```java
String s = "abcdefghijklmabcdefghijklm";
System.out.println(s.lastIndexOf('c'));
System.out.println(s.lastIndexOf(‘$'));
System.out.println(s.lastIndexOf('a', 8));
```

```java
String s = "abcdefghijklmabcdefghijklm";
System.out.println(s.indexOf("def"));
System.out.println(s.indexOf("def", 7));
System.out.println(s.indexOf("hello"));
System.out.println(s.lastIndexOf("def"));
System.out.println(s.lastIndexOf("def", 7));
System.out.println(s.lastIndexOf("hello"));
```

**substring Method**

```java
String s = "abcdefghijklmabcdefghijklm";
System.out.println(s.substring(20));
System.out.println(s.substring(3, 6));
```

If you did not input two parameters, then the only parameter you input is the start point, and it will go to the end.

> [!CAUTION]
>
> The end point will not be returned.

**StringBuilder**

**Other Resources**

https://docs.oracle.com/javase/10/docs/api/java/lang/String.html

