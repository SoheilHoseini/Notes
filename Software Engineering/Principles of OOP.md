
##### Encapsulation
It means to control the outer access to fields of a class using access modifiers and getter and setter methods so modification to attributes would be the way we want and also some validation could be performed.

##### Abstraction
It is about hiding unnecessary details of a class to reduce complexity. For example, we have a `MailService` class including methods `sendEmai()`, `connect()`, `authenticate()` and `disconnect()`. If we define all of them as *public* , usage of the service would be complex; So we can use all the three lass methods inside the `senEamil()` and make them *private* so from outside, only method is accessible and complexity is reduced.
Furthermore, if a change is happened in any of the three, only inside the `MailService` class would be affected and this way, we have reduced coupling as well.

##### Inheritance
It is used for avoiding code duplication by implementing some functionalities in the base class and inherit them in the children classes.

##### Polymorphism
It is about making an object taking on different forms. For example we have a `UIControl` class and two other classes `CheckBox` and `TextBox` inheriting frim it in which each of them have the `draw()` functionality but in different forms. So we define the base class as `abstract` (which can not be used directly or instantiate it) and the `draw()` functionality will be `abstract`  as well and with no implementation. 
```java
public abstract class UIControl {

  public void enable() {
    System.out.println("Enabled");
  }

  public abstract void draw();
}
```

```java
public class CheckBox extends UIControl {
  @Override
  public void draw() {
    System.out.println("Drawing a checkbox");
  }
}
```

```java
public class TextBox extends UIControl {
  @Override
  public void draw() {
    System.out.println("Drawing a textbox");
  }
}
```

Now if we create a method which takes an instance of type `UIControl` and calls `draw()` for it, depending of the instance type, different forms of drawing would be executed.
```java
public class Main {
    public static void main(String[] args) {
		drawUI(new TextBox()); // draws a text box
		drawUI(new CheckBox()); // draws a check box
    }
    
	public static void drawUI(UIControl objUI){
		objUI.draw();
	}
}
```


### **Note** *
When class `B` inherits from class `A` or implements interface `I`, it is of type `A` or `I` as well!