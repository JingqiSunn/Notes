#### Lecture 6

**Method Signature**

*Definition: A combination of the method's name and number, types and order of its parameters.*

Here is an example:

The Complete Method

```java
public double calculateAnswer(double wingSpan, int numberOfEngines, 
 double length, double grossTons) {
//do the calculation here 
return 0.0;
}
```

The Corresponding Method Signature

```java
calculateAnswer(double, int, double, double)
```

**Method Overloading**

*Definition: You can use the methods with the same name in the same class, just with different sets of parameters.*

> [!WARNING]
>
> The compiler can declare the difference between two cousin method only with the different parameters.
>
> But the compiler can not declare the difference between the type of the return value, you can think it as the type of the return value is not in the method signature.
>
> Here is an example:
>
> The compiler don't know which one to use if your input is
>
> ```java
> int k;
> int v;
> int a = max(k,v);
> ```
>
> When the two method are
>
> ```java
> int max(int a , int b);
> double max(int a, int b);
> ```
>
> Because for a compiler, it just find the method by the signature.

**Object-Oriented Programming**

This is a very important conception in Java.

**Object**

An object has a unique identity, states and behavior, and it can interact with each others for communication.

*Variable:* The things to describe the statement of the object.

*Method:* It can define the behavior of the object.

*Class:* It is the blue print of the object.

*Instance:* the real object. 

You can actually think that **new class** is a way to construct the blueprint in the class into a real object.

**Declaring a Blue Print**

```java
public class GradeBook {
	arguments; 
    public void displayMessage() {
    System.out.println("Welcome to the Grade Book!");
}
```

*Public* before class means that any other object can use the object this blue print construct, somehow it is likely the employee at the bottom rank.

*public* before method means that this method can be used by other object not only the object with this tool, which somehow is like a public shared tooled but saved by one particular person.

But the start of the project is from the main method.

```java
public class GradeBookTest {
 	public static void main(String[] args) {
 		GradeBook myGradeBook = new GradeBook();
 		myGradeBook.displayMessage();
 	}
}
```

When you need to use the GradeBook, you have to build it by new method, and the complete name of this GradeBook can be called *GradeBook myGradeBook*, because what we really cared about is what kind of the thing the object is and what is the name of this particular one.

After you have this tool, or you kind of build it, you can borrow tools from it to do something you like. 

```java
public class GradeBook {
 	private String courseName;
 	public void displayMessage( String courseName ) {
		System.out.printf("Welcome to the Grade Book for
 		the course%s!\n", courseName);
 	}
}
```

*private* is used for hiding data.

**Initializing the Instance Object**

```java
GradeBook myGradeBook = new GradeBook();
GradeBook myGradeBook = new GradeBook(“Java”);
GradeBook myGradeBook = new GradeBook(“Alice”, “Java”);
GradeBook myGradeBook = new GradeBook(2022, “Spring”, “Java”);
```

*New* also has a meaning of initialization, which can also give some initialized data to the blue print.

Constructer is not like a method, it doesn't have a return type.

The standard form is as below:

```java
public ClassName(parameter){
    use parameter to initializing the blue print;
}
```

If your blue print has 5 data needed to be initialized and you offered 5 ports, then you have to initialize them all.

If you didn't offer enough ports, then the java compiler will help you to initialize the data while it is very low in performance.

**The Example of Without Enough Constructer**

```java
public class GradeBook { // no constructor provided by the programmer
 private String courseName;
 public void setCourseName(String name) {
 courseName = name;
 }
 public String getCourseName() {
 return courseName;
 }
 public void displayMessage() {
 System.out.printf("Welcome to the grade book for\n%s!\n", getCourseName());
 }
}
```

The courseName will will get a null value.

> [!CAUTION]
>
> ```java
> public class GradeBook { // this version has a constructor
>  private String courseName;
>  public GradeBook(String name) {
>  courseName = name;
>  }
>  public void setCourseName(String name) {
>  courseName = name;
>  }
>  public String getCourseName() {
>  return courseName;
>  } …
> }
> ```
>
> This one is illegal!

 