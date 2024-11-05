#### Lecture 9

> [!CAUTION]
>
> A static method CANNOT access non-static  class members (instance variables, instance  methods).
>
> To explain this, we can say that the instance variable can various from objects to objects, so when you want to use the information, there will be contradiction on which one should you choose.

##### Main Method

Main method is also a static method.

##### Value Method

You can change the int number into String directly without changing it to an object Integer, which is the same for all the primitive values.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416104344626.png" alt="image-20240416104344626" style="zoom:50%;" />

##### Packages

*Definition: A way to group the similar classes together.*

**Benefits**

1. Organize the Application Components
2. Reuse the programs by importation

##### Declaring a Reusable Class

1. First line to be the declaration sentence.

   It is just create some folder and fit your class in.

   <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416105139456.png" alt="image-20240416105139456" style="zoom:50%;" />

2. Declare a public class (to be reusable).

##### Import a Class

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416105350172.png" alt="image-20240416105350172" style="zoom:50%;" />

> [!NOTE]
>
> When we have no import statement, then the search program in the system will just find the class in the same modulus, but when we give the import sentence, then for example *sustech.cs101.Time*, it will just search in the corresponding folder.

You can actually create a brand new Scanner in your folder, then if you want to use it, you just need to import the new Scanner.

##### Import String Class

We don't need to import String class, because it is in the folder of *java.lang*, and it will be automatically being imported in by the compiler.

##### Import Multiple Classes

You just need to know that * means anything in the folder.

##### Package Access for Class Members

```java
public class Time1 {
 	int hour;
	int minute;
	int second;
 	void setTime(int h, int m, int s) {...}
}
```

Here we have no modifier, which is also OK.

Then these members are all accessible to the program in the same package, which is a little more easier then the private type.

##### Access Level Modifiers (So Far)

|  Modifier   | Class | Package | World |
| :---------: | :---: | :-----: | :---: |
|   public    |   Y   |    Y    |   Y   |
| no modifier |   Y   |    Y    |   N   |
|   private   |   Y   |    N    |   N   |

**Example**

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416112222885.png" alt="image-20240416112222885" style="zoom:50%;" />

##### Access Modifiers for Classes

1. At the top level, a class can only be declared as public or  package-private (no explicit modifier).

   <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416113217881.png" alt="image-20240416113217881" style="zoom:50%;" />

2. A top-level class cannot be private.

3. We can declare multiple classes in one .java file

4. Only one of the class declarations in a .java file can be public.

5. Other classes in the file must not have public access modifiers, and can be used only by the other classes in the package

##### The final keyword

**Final (local) Variables**

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240416113741357.png" alt="image-20240416113741357" style="zoom:50%;" />

This is not compliable, because according to the definition of final, the value of the variables can not be changed anymore.

```java
private final int I_AM_A_CONSTANT = 2;
```

> [!CAUTION]
>
> It is a must for us to give an initialization for the final variables.

##### Enumerations

**enum**

*Definition: Some variable that will only change in a fixed range.*

*Standard Caller*

```java
public enum Direction {
 	NORTH, SOUTH, EAST, WEST
}
```

```java
Direction d = Direction.EAST
```

> [!NOTE]
>
> There are four object in the direction.
>
> You can set the variable to be one of the object.
>
> I think direction here is just like a class.

```java
public final class Direction {
 	private Direction() {}
 	public static final Direction EAST = new Direction();
 	public static final Direction WEST = new Direction();
 	public static final Direction SOUTH = new Direction();
 	public static final Direction NORTH = new Direction();
}
```

> [!CAUTION]
>
> This one is not true, it is just helping you to understand the enumerate class.

And it shows that you can not change the value in the enumeration.

##### Java Heap Memory

*Definition: The heap space is used by Java runtime to allocate memory to Objects.*

1. As long as there is no reference in the program to the particular object, then it will be deleted.
2. Any object created in the heap space has global access and can be  referenced from anywhere of the application (as long as you have a  reference)

##### Java Stack Memory

*Definition: Stack memory stores information for execution of methods in a thread.*

> [!TIP]
>
> Last in, first out.
>
> This is actually the same with caller is later than callee.

1. As soon as a method ends, the block will be erased and become available  for next method. Therefore, stack memory size is very less compared to  heap memory

##### Memory Allocation Example

```java
public class Memory { 
 	public static void main(String[] args) {
 	int i = 1;
 	Object obj = new Object();
 	Memory mem = new Memory();
 	mem.foo(obj);
 } 
 	private void foo(Object param){
 		String str = param.toString(); 
 		System.out.println(str); 
 }
}

```

