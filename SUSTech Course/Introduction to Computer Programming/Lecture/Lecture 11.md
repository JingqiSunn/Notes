#### Lecture 11

##### Polymorphism

###### Example of polymorphism

> Each class extends superclass Animal, which contains a method move and  maintains an animal’s current location as x-y coordinates. Each subclass  implements (overrides) method move.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240430103012283.png" alt="image-20240430103012283" style="zoom:33%;" />

You can see that although fish, frog and bird all have *move* method, but they are not the same, you can not simply use inheritance.

If we use the knowledge that we have learnt before, then it is 

```java
public class Zookeeper {
	public static void main(String[] args) {
		Bird bird = new Bird();
		bird.move();
		Fish fish = new Fish();
		fish.move();
		Frog frog = new Frog();
		frog.move();
}
```

Because what we leant is 

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240430103459028.png" alt="image-20240430103459028" style="zoom:50%;" />

###### Polymorphic

```java
Animal animal = new Fish();
```

> [!CAUTION]
>
> The following is incorrect.
>
> ```java
> Fish fish = new Animal();
> ```

**Example**

```java
Animal animal = new Fish();
animal.move();
```

In this example , **we can learned that in java compiler, the method being used will be used by the actual type.**

> [!CAUTION]
>
> ```java
> animal.move();
> ```
>
> | When  |     Where     |
> | :---: | :-----------: |
> | Check | Declared Type |
> |  Run  |  Actual Type  |
>
> That means even if the method is created in the declared type, as long as there is no corresponding method in the actual type we will find that the program can not be compiled.

|  Type  |    Meaning    |
| :----: | :-----------: |
| Animal | Declared Type |
|  Fish  |  Actual Type  |

Suppose the Fish class adds a new method sleepEyesOpen(). 

Can the code compile?

```java
Animal animal = new Fish();
animal.sleepEyesOpen();
```

No.

How to solve?

```java
Animal animal = new Fish();
if(animal instanceof Fish){
	Fish fish = (Fish) animal;
	fish.sleepEyesOpen();
}
```

The following is incorrect.

```java
Animal animal = new Bird();
Fish fish = (Fish) animal;
fish.sleepEyesOpen();
```

###### Principle of Polymorphism

> 1. Superclass references can point to subclass instances.
> 2. Superclass references can be  used to invoke accessible superclass members.
> 3. Superclass references cannot  be used to invoke subclass-specific members, like sleepEyesOpen.
> 4. When using the  superclass reference to invoke a method, the real effect is determined by the actual  type of the object; **Java runtime will search from the actual class type all the way up to  the superclass to find the method version to be executed.**

###### Polymorphism Use Cases

```java
public class Zookeeper {
public static void main(String[] args) {
	Animal bird = new Bird();
	Animal fish = new Fish();
	Animal frog = new Frog();
	ArrayList<Animal> list = new ArrayList<>();
	list.add(bird);
	list.add(fish);
	list.add(frog);
	for(Animal animal: list){
		animal.move();
		}
    }
}
```

You can define an array list with the component of different actual type.

```java
public class Zookeeper {
	public static void manage(Animal animal){
		animal.move();
	}
	public static void main(String[] args) {
		manage(new Bird());
		manage(new Fish());
		manage(new Frog());
	}
}

```

###### Method Binding

**Two Types**

1. Dynamic Binding

   the method that will be executed is  *determined at runtime*.

2. Static Binding

   the method that will be executed is  *determined at compile-time*.

> **Dynamic Binding**
>
> - Also known as late binding or runtime  polymorphism.
> - The method to be executed is determined at  runtime, based on the actual type of the  object, not the reference type (declared type)
>
> **Static Binding**
>
> - Also known as early binding or compile-time  binding.
> - The compiler determines the method to be  called based on the declared type of the  reference variable.
>
> *Component:*
>
> 1. Private method
>
>    Because such method are not inherited.
>
> 2. Static method
>
>    Because it is bounded to the class.
>
> 3. Method overloading
>
>    Because unless you use the polymorphism we will not need to choose method from the actual type to declared type.
>
> 4. Final Class
>
> **Example**
>
> ```java
> public class Animal {
> 	public static void eat(){
> 		System.out.println("Animal eats");
> 	}
> }
> public class Cat extends Animal{
> 	public static void eat(){
> 	System.out.println("Cat eats");
> }
> public static void main(String[] args) {
> 	Animal x = new Cat();
> 	x.eat();
> 	}
> }
> ```

###### Final Class

**Characteristics**

1. A final class cannot be a superclass.
2. All methods in a final class are implicitly final.
3. Making the class final also prevents programmers from creating subclasses that  might bypass security restrictions 

####  Abstract classes

What we have learned is Concrete Class.

> Concrete Class
>
> We need to build the whole body of the concrete class.

**Example**

```java
public abstract class Animal {
 	public abstract void move();
}
```

You can see there is no body for the method.

An abstract method can not have a method body.

Our intension is to make it been rewritten in other classes.

So it is a very great choice to be written as a super class.

> [!NOTE]
>
> Only after you override all the abstract method in the superclass can you finally create an object.

That means **abstract class can only be used as a declared type rather than an actual type**.

###### Using Abstract Class

```java
public abstract class Animal {
	int position_x;
	int position_y;
	Animal(){
		position_x = 10;
		position_y = 10;
	}
	public abstract void move();
	public void sleep(){
	System.out.println("zzz...");
	}
}
```

```java
public class Fish extends Animal {
@Override
	public void move(){
	System.out.println("Fish swims"); 
	}
}
```

We can see that the constructor can only be called by the default construction of the sub class.

**Case Study**



