## AWT(Abstract Windowing Toolkit)

AWT stands for Abstract Windowing Toolkit. It contains all classes to write the program that interface between the user and different windowing toolkits.

### Components

#### Label

Labels: This is the simplest component of Java Abstract Window Toolkit. This component is generally used to show the text or string in our application and label never perform any type of action. Syntax for defining the label is:

```java
Label label_name = new Label (“This is the label text”);
```

Above code simply represents the text for the label.

```java
Label label_name = new Label (“This is the label text.”, Label.CENTER);
```

label can be left, right or centered. Above declaration used the center justification of the
label using the Label.CENTER

#### Button

Buttons: This is the component of Java Abstract Window Toolkit and is used to trigger
actions and other events required for our application. The syntax of defining the button is
as follows:

```java
Button button_name = new Button (“This is the label of the button.”);
```

We can change the Button’s label or get the label’s text by using the
Button.setLabel(String) and Button.getLabel() method. Buttons are added to its container
using the add (button_name) method.

#### CheckBox

Check Boxes: This component of Java AWT allows us to create check boxes in our applications. The syntax of the definition of Checkbox is as follows

```java
CheckBox checkbox_name = new Checkbox (“Optional check box 1”, false);
```

Above code constructs the unchecked Checkbox by passing the Boolean valued argument false with the Checkbox label through the Checkbox() constructor. Defined Checkbox is added to its container using add (checkbox_name) method. We can change and get the checkbox’s label using the setLabel (String) and getLabel() method. We can also set and get the state of the checkbox using the setState(boolean) and getState() method provided by the Checkbox class.

#### Radio Button

This is the special case of the Checkbox component of Java AWT package. This is used as a group of checkboxes which group name is same. Only one Checkbox from a Checkbox Group can be selected at a time. Syntax for creating radio buttons is as follow

```java
import java.awt.*;
/**
 * radio
 */
public class radio {

    public static void main(String[] args) {
        Frame fr = new Frame();
        CheckboxGroup chckgrp = new CheckboxGroup();
        Checkbox chck1 = new Checkbox("C++",chckgrp,false);
        Checkbox chck2 = new Checkbox("C",chckgrp,false);
        Checkbox chck3 = new Checkbox("Rust",chckgrp,false);
        fr.add(chck1);
        fr.add(chck2);
        fr.add(chck3);
        fr.setVisible(true);
        fr.setSize(300,300);
        fr.setLayout(new FlowLayout());
    }
}
```

#### Text Area

This is the text container component of Java AWT package. The Text Area contains plain text. TextArea can be declared as follows

```java
TextArea txtArea_name = new TextArea();
```

We can make the Text Area editable or not using the setEditable (Boolean) method. If we pass the Boolean valued argument false then the text area will be non-editable otherwise it will be editable. The text area is by default in editable mode. Text are set in the text area using the setText(string) method of the TextArea class.

#### Text Field

This is also the text container component of Java AWT package. This component contains single line and limited text information. This is declared as follows:

```java
TextField txtfield = new TextField(20);
```

We can fix the number of columns in the text field by specifying the number in the constructor. In the above code we have fixed the number of columns to 20. As shown in the example below, a button is represented by a single label. That is the label shown in the example can be pushed with a click of a mouse.

## Event Handling

Changing the state of an object is known as an event. For example, click on button, dragging mouse etc. The java.awt.event package provides many event classes and Listener interfaces for event handling.

```java

/**
 * firstAWT
 */
import java.awt.*;
import java.awt.event.*;

public class firstAWT {

    public static void main(String[] args) {
        Frame f = new Frame();
        Label l1 = new Label("first");
        Label l2 = new Label("second");
        TextField t1 = new TextField(10);
        TextField t2 = new TextField(10);
        Button b1 = new Button("OK");
        b1.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent ae) {
                String temp = t1.getText();
                t1.setText(t2.getText());
                t2.setText(temp);
            }
        });
        f.add(l1);
        f.add(l2);
        f.add(t1);
        f.add(t2);
        f.add(b1);
        f.setVisible(true);
        f.setSize(300, 300);
        f.setLayout(new FlowLayout());
    }

}
```

![](../../../statics/Pasted%20image%2020231125152332.png)

1. ActionEvent : It indicates the component-defined events occurred i.e. the event generated by the component like Button, Checkboxes etc.
2. AdjustmentEvent : This is the AdjustmentEvent class extends from the AWTEvent class. When the Adjustable Value is changed then the event is generated.
3. ComponentEvent : This is the low-level event which indicates, if the object moved, changed and its states (visibility of the object). This class only performs the notification about the state of the object.
4. ContainerEvent : This is a low-level event which is generated when container’s contents changes because of addition or removal of a components.
5. FocusEvent : This indicates about the focus where the focus has gained or lost by the object
6. InputEvent : This event class handles all the component-level input events. This class acts as a root class for all component-level input events.
7. ItemEvent : The ItemEvent class handles all the indication about the selection of the object i.e., whether selected or not.
8. KeyEvent : It handles all the indication related to the key operation in the application if we press any key for any purposes of the object then the generated event gives the information about the pressed key. These types of events check whether the pressed key left key or right key, ‘A’ or ‘a’ etc.
9. MouseEvent : It handle all events generated during the mouse operation for the object. That contains the information whether mouse is clicked or not if clicked then checks the pressed key is left or right.
10. PaintEvent : The PaintEvent class only ensures that the paint() or update() are serialized along with the other events delivered from the event queue.
11. TextEvent : TextEvent is generated when the text of the object is changed.
12. WindowEvent : If the window or the frame of our application is changed (Opened, closed, activated, deactivated or any other events are generated), WindowEvent is generated.

### Event Delegation model in java

## Swing

The Java Swing provides the multiple platform independent APIs interfaces for interacting between the users and GUIs components. Java provides an interactive feature for design the GUIs toolkit or components like: labels, buttons, text boxes, checkboxes, combo boxes, panels and sliders etc

## Layout Manager

To create layouts, we use layout managers. Layout managers are one of the most difficult
parts of modern GUI programming. We can use no layout manager, if we want. There might
be situations, where we might not need a layout manager. But to create truly portable,
complex applications, we need layout managers. Without layout manager, we position
components using absolute values.

There are some of the common tasks associated to use layout managers:
•Setting Layout Manager
•Adding Components to a Container
•Providing Size and Alignment Hints
•Putting Space Between Components
•Setting the Container’s Orientation

GridLayout: The GridLayout layout manager lays out components in a rectangular grid.
The container is divided into equally sized rectangles. One component is placed in each
rectangle.

BoxLayout: BoxLayout is a powerful manager that can be used to create sophisticated
layouts. This layout manager puts components into a row or into a column. It enables
nesting, a powerful feature, which makes this manager very flexible. It means that we can
put a box layout into another box layout.

BorderLayout: A BorderLayout manager is a very handy layout manager. It divides the
space into five regions. North, West, South, East and Centre. Each region can have only
one component. If we need to put more components into a region, we can simply put a
panel there with a manager of our choice. The components in N, W, S, E regions get their
preferred size. The component in the centre takes up the whole space left.
BoxLayout: BoxLayout is a powerful manager that can be used to create s

FlowLayout manager : This is the simplest layout manager in the Java Swing toolkit. It
is mainly used in combination with other layout managers. When calculating its children
size, a flow layout lets each component assume its natural (preferred) size.
The manager puts components into a row. In the order, they were added. If they do not fit
into one row, they go into the next one. The components can be added from the right to the
left or vice versa. The manager allows aligning the components.

## JOptionPane

`JOptionPane` is a class in the Java Swing framework that provides a set of static methods to create and manage various types of dialog boxes. Dialog boxes are graphical user interface (GUI) elements that pop up to interact with the user. `JOptionPane` is part of the javax.swing package and is commonly used for displaying simple dialog boxes for user input, information, warnings, and confirmations.

```java
JOptionPane.showMessageDialog(null, "This is an informational message.", "title", JOptionPane.INFORMATION_MESSAGE);
```

## Combo Box
Creating a simple combo box in AWT involves using the `Choice` class. Here's a basic example:

```java
import java.awt.*;
/**
 * combo
 */
public class combo {

    public static void main(String[] args) {
        Frame fr = new Frame();
        Choice choice = new Choice();
        choice.add("Haryana");
        choice.add("Delhi");
        choice.add("UP");
        choice.add("Himachal");
        fr.add(choice);
        fr.setVisible(true);
        fr.setSize(300, 300);
        fr.setLayout(new FlowLayout());
    }
}
```

In this example:

1. We create a `Frame` to hold our GUI components.
2. We create a `Choice` (combo box) named `choice` and add items to it.
3. We add an `ItemListener` to the `Choice` to handle selection events. The `itemStateChanged` method is called when the user selects a different item in the combo box.
4. We add the `Choice` to the frame.
5. The `WindowAdapter` is used to handle the window-closing event.

When you run this program, it will display a window with a combo box containing the specified items. The program will print the selected item to the console whenever the user makes a selection.

