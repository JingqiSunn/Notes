#### Lecture 13

##### AWT

> **Abstract Window Toolkit**
>
> - AWT components are platform-dependent.  
> - AWT contains 12 packages of 370 classes (Swing and FX are more  complex, 650+ classes)

##### Swing 

> - provides a much more  comprehensive set of UI widgets than AWT.
> - They are written entirely in Java and  platform-independent.

###### Things in Java Swing

> - Component
> - Container
> - Event Handling

###### Java GUI Class Hierarchy

<img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240514103612413.png" alt="image-20240514103612413" style="zoom:50%;" />

###### Requirement in Swing

> - A Swing application requires a top-level container (a window that is not  contained inside another window)

###### Top Level Container in Swing

> - JFrame
> - JDialog
> - JApplet

There are lots of secondary containers.

###### Import Java Swing

```java
import javax.swing.JFrame;
```

> Example:
>
> ```java
> import javax.swing.JFrame;
> public class HelloWorld extends JFrame {
>     public HelloWorld() {
>  	super("Our first Swing program");
>  	}
>  	public static void main(String[] args) {
> 	HelloWorld gui = new HelloWorld();
> 	gui.setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE );
> 	gui.setSize(800, 600);
>  	gui.setVisible(true);
>  	}
> }
> ```
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240514105248093.png" alt="image-20240514105248093" style="zoom:33%;" />

> **Example**
>
> ```java
> public class HelloWorld extends JFrame {
> 	private JLabel label;
> 	public HelloWorld() {
> 		super("Our first Swing 	program");
>  		setLayout(new FlowLayout());
>  		label = new JLabel("Hello World");
>  		label.setFont(new Font("San Serif", Font.PLAIN, 30));
>  		add(label);
>  		}
>  	public static void main(String[] args) { // same as earlier }
> }
> ```
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240514105902004.png" alt="image-20240514105902004" style="zoom:33%;" />

> **Example**
>
> ```java
> public class JPanelTest {
> public static void main(String[] args) {
> JFrame frame = new JFrame("Hello World");
> //Create a panel and add components to it.
> JPanel panel = new JPanel(new BorderLayout());
> panel.add(new JButton("North"), BorderLayout.NORTH);
> panel.add(new JButton("South"), BorderLayout.SOUTH);
> panel.add(new JButton("West"), BorderLayout.WEST);
> panel.add(new JButton("East"), BorderLayout.EAST);
> panel.add(new JButton("Center"), BorderLayout.CENTER);
> frame.setContentPane(panel);
> frame.setSize(300,200);
> frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
> frame.setVisible(true);
> }
> 
> ```
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240514110050564.png" alt="image-20240514110050564" style="zoom:33%;" />

> **Example**
>
> ```java
> public class GraphicsDemo {
> public static void main(String[] args) {
> JFrame frame = new JFrame();
> MyCircle circle = new MyCircle();
> frame.add(circle);
> frame.pack();
> frame.setVisible(true);
> }
> }
> class MyCircle extends JComponent{
> int X = 100;
> int Y = 50;
> @Override
> public void paintComponent(Graphics g){
> g.drawOval(X,Y,50,50);
> }
> @Override
> public Dimension getPreferredSize(){
> return new Dimension(200, 100);
> }
> }
> 
> ```
>
> <img src="C:\Users\孙璟琦\AppData\Roaming\Typora\typora-user-images\image-20240514110557501.png" alt="image-20240514110557501" style="zoom:33%;" />

###### Dialog

> - A Dialog window is an independent sub window meant to carry  temporary notice apart from the main Swing Application Window
> - Most Dialogs present an error message or warning to a user, but Dialogs  can present images, directory trees, or just about anything compatible  with the main Swing Application that manages them

###### JOptionPane

```java
public static void main(String[] args) {
 String str1 = JOptionPane.showInputDialog("Enter 1st integer");
 String str2 = JOptionPane.showInputDialog("Enter 2nd integer");
 int num1 = Integer.parseInt(str1);
 int num2 = Integer.parseInt(str2);
 int sum = num1 + num2;
 JOptionPane.showMessageDialog(null, num1 + " + " + num2 + " = " + sum);
}
```

###### Event

