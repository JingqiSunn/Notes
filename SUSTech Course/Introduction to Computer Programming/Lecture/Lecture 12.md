#### Lecture 12

##### Example

> We have three subclass
>
> 1. Fruit
> 2. Chicken
> 3. Tiger
>
> We can find that fruit and chicken are edible, while chicken and tiger are both animal.
>
> But we know that in java, a class can only be inherit from to classes, so how can we design chicken and fruit? 
>
> While fruit is an abstract class.
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507104109383.png" alt="image-20240507104109383" style="zoom:33%;" />

> [!NOTE]
>
> So we have to understand interface.

##### Example of Interface

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507104324855.png" alt="image-20240507104324855" style="zoom:50%;" />

The algorithms of comparison for different class are different.

##### Declaring Interface

```java
public interface Payable{
    double getPaymentAmount();
}
```

You can obviously see the difference.

Interface are always public, because it can interact with outer world.

##### Fields in Interface

- All the variable in the interface are implicitly public static final.

- And you have to give the initial value by yourself.

- Because all the variables are static type, so there is no need to use the constructor.
- If you add constructor in interface, the compiler will think it is invalid.

##### Method in Interface

You can create three types of method:

1. Abstract
2. Static
3. Default

```java
public interface MyInterface {
	default void foo(){
		System.out.println("Default method");
	}
	static void bar(){
		System.out.println("Static method");
	}
	void baz();
}
```

Abstract method must need to be override by the subclass, but default class is optional.

But default method has to have concrete implementation.

You can see that the syntax of calling abstract method is a little different.

> **Example**
>
> ```java
> public interface P {
>     void foo();//Abstract class
>     default void burn(){
>         Arguments;
>     }
> }
> ```
>
> ```java
> public class C implements P {
>     void zoo(){
>         Arguments;
>     }//You need to override the abstract methods
>     //You can optionally ovverride the burn method because it is default
> }
> ```
>
> What we need is 
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507112316142.png" alt="image-20240507112316142" style="zoom:50%;" />

##### Back to the Question

```java
public interface Payable{
    double getPaymentAmount();
}
```

```java
public class Invoice implements Payable {
	double getPaymentAmount(){
        Arguments;
    }
}
```

> [!NOTE]
>
> If we forget to override getPaymentAmount in the Invoice class, it is basically abstract itself, so we need further subclass to override it.

```java
public class Invoice implements Payable {
    private String partNumber;
    private String partDescription;
    private int quantity;
    private double pricePerItem;
    public Invoice(String part, String description, int count, double price) {
        partNumber = part;
        partDescription = description;
        setQuantity(count);
        setPricePerItem(price);
    }
    public String getPartNumber() {
        return partNumber;
    }

    public String getPartDescription() {
        return partDescription;
    }

    public int getQuantity() {
        return quantity;
    }

    public double getPricePerItem() {
        return pricePerItem;
    }

    public void setPartNumber(String partNumber) {
        this.partNumber = partNumber;
    }

    public void setPartDescription(String partDescription) {
        this.partDescription = partDescription;
    }

    public void setQuantity(int quantity) {
        this.quantity = quantity;
    }

    public void setPricePerItem(double pricePerItem) {
        this.pricePerItem = pricePerItem;
    }
    public String toString() {
        return String.format("...")
    }
    @Override
    public double getPaymentAmount() {
        return getQuantity * getPricePerItem();
    }
}
```

Interface can not be instance.

You can use Interface class to be the declared type, but it can not be actual type.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507114658364.png" alt="image-20240507114658364" style="zoom:50%;" />

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507114713610.png" alt="image-20240507114713610" style="zoom:50%;" />

This is Ok for compiler because it is just like the inheritance.

If you want to use the methods in the actual type, you can actually convert the declared type to the actual type.

But please examine the validity before application.

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240507115054903.png" alt="image-20240507115054903" style="zoom:50%;" />

In this way you actually collect two different type of method.

You can imply no limitation numbers of interfaces, while you can only extend one super class.

So it can actually inherit several  interface.