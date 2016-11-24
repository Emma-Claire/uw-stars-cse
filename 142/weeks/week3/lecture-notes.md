_CSE 142_
# Lecture Notes
## Week 3

### Key Words
* __scope__: the part of the program where a variable exists
 * A variable declared in a for loop exists only in that loop
 * A variable declared in a method exists only in that method
* __primitive types__: int, double, boolean, char
* __object types__: name of class (.e.g., String, DrawingPanel)
* __parameter__: sends information __in__ from the caller of a method
* __return__: sends information __out__ from a method to its caller

### Drawing Panel
_Not built into Java, something written specifically for this class. Will need to place [DrawingPanel.java](DrawingPanel.java) in the same folder as your code and compile it in order for it to work properly_
* In computer graphics, the upper-left hand corner is (0,0)
* In order to use Color, you will need to add `import java.awt.*;` to the top of your code
* Methods to consider using

 | __Method Name__                                      |  __Description__|
 | :--------------------------------------------------- | :--- |
 | `dp.setBackground(Color);` | sets the background color of the panel |
 | `dp.clear();` | clears the background of the panel |
 | `dp.pause(miliseconds);` | pause the program for the number of miliseconds passed |
 | `g.drawLine(x1, y1, x2, y2);` | draws a line between the points (x1, y1) and (x2, y2) |
 | `g.drawOval(x, y, width, height);` | draws the outline of an oval that fits exactly into a box of size width x height with the top-left corner of the box at (x, y) |
 | `g.drawRect(x, y, width, height);` | draws the outline of a rectangle of size width x height with the top-left corner at (x, y) |
 | `g.drawString(text, x, y)` | draws text with a bottom-left corner of (x, y) |
 | `g.fillOval(x, y, width, height)` | draws a filled in oval that fits exactly into a box of size width x height with a top-left corner at (x, y) |
 | `g.fillRect(x, y, width, height)` | draws a filled in rectangle of size width x height with a top-left corner at (x, y) |
 | `g.setColor(Color); ` | sets Graphics to paint any following shapes in the given color |
 
* Basic program setup
 ```java
  // needed in order to use Color
 import java.awt.*;

 public class BasicDrawing {
    public static void main(String [] args) {
       // creates a new Drawing Panel object of width 400, height 200
       DrawingPanel dp = new DrawingPanel(400, 200);

       // sets the background color of the panel
       dp.setBackground(Color.GREEN);

       // creates a new Graphics object
       Graphics g = dp.getGraphics();

       g.setColor(Color.RED);
       g.fillRect(100, 100, 50, 70);
       g.setColor(Color.BLUE);
       g.drawRect(100, 100, 50, 70);
    }
 }
 ```

### Math class
* The __Math__ class has a number of useful methods including `Math.sqrt()`, `Math.abs()`, and `Math.pow()`; check out more details in the [Java API](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html)

### return
* A return statement sends information __out__ from a method to its caller
* There cannot be statements executed after a return statement in a method
* The return type should be provided as the third keyword in your method header
 ```java
 // This method has a return type of void
 public static void hello() {
    System.out.println("Hello");
 }
 
 // This method has a return type of int
 public static int three() {
    return 3;
 }
 ```

### Casting
* Changes the type of a piece of information
 ```java
 int x = 2;
 // a will contain 2.0
 double a = (double) x;
 
 double y = 2.5;
 // b will contain 2
 int b = (int) y;
 ```
* Updated precedence list with casting
 
 | __Priority__ | __Operation__ |
 | :--- | :--- |
 | 1 | parens |
 | 2 | uniary operations, __casting__ |
 | 3 | multiplication, division, mod |
 | 4 | addition, subtraction, string concatenation |
 | 5 | less than, less than or equal to, greater than, greater than or equal to |
 | 6 | equal to, not equal to |
 
