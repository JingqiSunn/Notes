#### Lecture 8

**String Builder**

> **The Introduction of String Builder**
>
> Instruction
>
> ```java
> StringBuilder buffer1 = new StringBuilder();
> StringBuilder buffer2 = new StringBuilder(10);
> StringBuilder buffer3 = new StringBuilder("hello");
> ```
>
> The Output
>
> ```java
> System.out.printf("buffer1 = \"%s\"\n", buffer1);
> System.out.printf("buffer2 = \"%s\"\n", buffer2);
> System.out.printf("buffer3 = \"%s\"\n", buffer3);
> ```

*Append*

```java
String string = "goodbye";
char[] charArray = {'a', 'b', 'c', 'd', 'e', 'f'};
boolean booleanValue = true;
char charValue = 'Z';
int intValue = 7;
long longValue = 10000000000L;
float floatValue = 2.5f;
double doubleValue = 33.3333;
StringBuilder buffer = new StringBuilder();
StringBuilder lastBuffer = new StringBuilder("last buffer");
buffer.append(string); 
buffer.append("\n");
buffer.append(charArray); 
buffer.append("\n");
buffer.append(charArray, 0, 3); 
buffer.append("\n");
buffer.append(booleanValue); 
buffer.append("\n");
buffer.append(charValue); buffer.append("\n");
buffer.append(intValue); buffer.append("\n");
buffer.append(longValue); buffer.append("\n");
buffer.append(floatValue); buffer.append("\n");
buffer.append(doubleValue); buffer.append("\n");
buffer.append(lastBuffer);
System.out.printf("buffer contains:\n%s", buffer.toString());
```

**Wrapper Classes**

The object version of the primitive data type.

**A Time Class**

```java
public class Time1 {
private int hour; 
private int minute; 
private int second; 
public class Time1 {
	private int hour = 10;
	private int minute; 
	private int second; 
}

public void setTime(int h, int m, int s) { 
    hour = ( ( h >= 0 && h < 24 ) ? h : 0 ); 
    minute = ( ( m >= 0 && m < 60 ) ? m : 0 ); 
    second = ( ( s >= 0 && s < 60 ) ? s : 0 );
	}
public String toUniversalString() { 
    return String.format("%02d:%02d:%02d", hour, minute, second);
	}
public String toString() {
    return String.format("%d:%02d:%02d %s",
 	(hour == 0 || hour == 12) ? 12 : hour % 12,
 	minute, second, hour < 12 ? "AM" : "PM");
	}
}
```

**Handling Invalid Values**

*Giving Two Options*

```java
public void setTime(int h, int m, int s) {
	hour = ( ( h >= 0 && h < 24 ) ? h : 0 ); 
 	minute = ( ( m >= 0 && m < 60 ) ? m : 0 ); 
 	second = ( ( s >= 0 && s < 60 ) ? s : 0 ); 
}
```

*Change or Do Nothing*

```java
public void setTime(int h, int m, int s) {
	if(h >= 0 && h < 24) hour = h; 
 	if(m >= 0 && m < 60) minute = m;
 	if(s >= 0 && s < 60) second = s;
}

```

**Chasing the Internal Details**

```java
public boolean setTime(int h, int m, int s) {
    Statement;
}
```

**This Reference**

```java
public class Time1 {
private int hour;
private int minute; 
private int second; 
public void setTime(int hour, int minute, int second) {
	if(hour >= 0 && hour < 24) this.hour = hour;
 	if(minute >= 0 && minute < 60) this.minute = minute;
 	if(second >= 0 && second < 60) this.second = second;
}
}
```

**Overloaded Constructor**

```java
public class Time2 {
 public Time2(int h, int m, int s) {
 setTime(h, m, s);
 }
 public Time2(int h, int m) {
 this(h, m, 0);
 }
 public Time2(int h) {
 this(h, 0, 0);
 }
 public Time2() {
 this(0, 0, 0);
 }
 public Time2(Time2 time) {
 this(time.getHour(), time.getMinute(), time.getSecond());
 }
}
```

*this* in the method is representing another constructor from up to down.

**Invalid Way**

```java
public class Time2 {
 public Time2(int h, int m, int s) {
 setTime(h, m, s);
 }
 public Time2(int h, int m) {
 Time2(h, m, 0);
 }
}
```

![image-20240409113505482](C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240409113505482.png)

![image-20240409113728284](C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240409113728284.png)

**Controlling Access to Members **

```java
private int hour;
public void setHour(int h) { 
    hour = ( ( h >= 0 && h < 24 ) ? h : 0 ); 
}
public int getHour() { 
    return hour; 
}
```

*Design 1*

```java
public class Time2 {
 	private int hour;
 	private int minute;
 	private int second;
 	public String toUniversalString() {
 	return String.format("%02d:%02d:%02d",
 hour, minute, second);
 }
 	public String toString() {
 	return String.format("%d:%02d:%02d %s", 
 	( (hour == 0 || hour == 12) ? 12 : hour % 12 ),
 	minute, second, (hour < 12 ? "AM" : "PM") );
 	}
}
```

*Design 2*

```java
public class Time2 {
 	private int hour;
	private int minute;
 	private int second;
 	public String toUniversalString() {
 	return String.format("%02d:%02d:%02d",
 	getHour(), getMinute(), getSecond());
 	}
 	public String toString() {
 	return String.format("%d:%02d:%02d %s", 
 	( (getHour() == 0 || getHour() == 12) ? 12 : getHour() % 12 ),getMinute(), getSecond(), (getHour() < 12 ? "AM" : "PM") );
 	}
}
```

**The design two is much better because it will be easier if we make some big changes to the variables type, then we just need to change the get and set method.**

**Code Reuse**

*Definition: In OOP, code reuse means that new classes (types) are  built on the basis of already existing classes (types).*

> **Composition**
>
> A class contains an object of another class.  This approach uses the functionality of the finished code;
>
> **Inheritance**

**Composition**

*Definition: A class can have references to objects of other classes as  members.*

![image-20240409115427331](C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240409115427331.png)

> [!NOTE]
>
> Always remember that it is object oriented.

**Employee Class**

```java
public class Date {
	private int month;
	private int day;
	private int year;
    public Date(int theMonth, int theDay, int theYear) {
 		month = checkMonth(theMonth);
 		year = theYear;
 		day = checkDay(theDay);
 		System.out.printf("Date object constructor for date 	%s\n", this);
	}
	private int checkMonth(int testMonth) {
 		if(testMonth > 0 && testMonth <=12)
            return testMonth;
 		else {
 			System.out.printf("Invalid month (%d), set to 				1", testMonth);
 			return 1;
 			}
		}
    private int checkDay(int testDay) { 
 	int[] daysPerMonth ={ 0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
 	if(testDay > 0 && testDay <= daysPerMonth[month]) 			return testDay;
 	if(month == 2 && testDay == 29 && (year % 400 == 0 || 
 	(year % 4 == 0 && year % 100 != 0)))
 		return testDay;
 		System.out.printf("Invalid day (%d), set to 1", 		testDay);
 		return 1;
}
	public String toString() { 
 	return String.format("%d/%d/%d", month, day, year);
}
}
```

```java
public class Employee {
	private String firstName;
	private String lastName;
	private Date birthDate;
	private Date hireDate;
}
```

**Static Class Members**

*Definition: A static variable represents class-wide information. All  objects of the class share the same piece of data.*

> [!WARNING]
>
> There is only one memory slot for a particular static information, no matter how many objects that you have created, they will share the same preference information of the location of the static variable is saved.

```java
public class Employee {
 	private String firstName;
 	private String lastName;
 	private static int count;
 	public Employee(String first, String last) {
 		firstName = first;
 		lastName = last;
 		++count;
 	System.out.printf("Employee constructor: %s %s; count = %d\n", firstName, lastName, count);
 	}
 	public String getFirstName() { 
        return firstName; 
    }
 	public String getLastName() { 
        return lastName; 
    }
 	public static int getCount() { 
        return count; 
    }
}
```



