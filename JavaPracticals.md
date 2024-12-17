# Table of Contents

| No.  | Practical  | Link         |
|------|------------|--------------|
| 1    | Practical 1| [Practical 1](#practical-1-) |
| 2    | Practical 2| [Practical 2](#practical-2-) |
| 3    | Practical 3| [Practical 3](#practical-3-) |
| 4    | Practical 4| [Practical 4](#practical-4-) |
| 5    | Practical 5| [Practical 5](#practical-5-) |
| 6    | Practical 6| [Practical 6](#practical-6-) |
| 7    | Practical 7| [Practical 7](#practical-7-) |
| 8    | Practical 8| [Practical 8](#practical-8-) |
| 9    | Practical 9| [Practical 9](#practical-9-) |
| 10   | Practical 10| [Practical 10](#practical-10-) |
---
# Practical 1 : 
## Write a program in java  to create a class for employee record with two constructors, first default constructor to initialize all variables, second constructor to accept the employee details and a method to display employee details.

```java
class Employee 
{
    int e_no;
    double e_sal;
    String e_name;
     Employee()
     {
         e_no=101;
         e_sal= 2090.50;
         e_name="AAAA";
     }
     Employee(int empno, double empsal, String empname)
     {
         e_no = empno;
         e_sal= empsal;
         e_name= empname;
     }
     void show()
     {
         System.out.println("Enter employee id - "+e_no);
         System.out.println("Enter employee salary - "+e_sal);
         System.out.println("Enter employee name - "+e_name);
     }
     
}
public class EmployeeRecord
{
    public static void main(String[] args) {
        Employee e1 = new Employee();
        e1.show();
        Employee e2 = new Employee(102,50050, "BBB");
        e2.show()   
    }
}

```
---

# Practical 2 : 
## Write a program in Java that has Boolean function returning a string to display whether it is leap year or not.

```java
// Java program to find a leap year

// Importing Classes/Files

// Class for leap-year dealing
public class LeapYearDemo {

	// Method to check leap year
	public static void isLeapYear(int year)
	{
		// flag to take a non-leap year by default
		boolean is_leap_year = false;

		// If year is divisible by 4
		if (year % 4 == 0) {
			is_leap_year = true;
			// To identify whether it is a century year or not
			if (year % 100 == 0) {
				// Checking if year is divisible by 400 therefore century leap year
				if (year % 400 == 0)
					is_leap_year = true;
				else
					is_leap_year = false;
			}
		}
			// We land here when corresponding if fails
			// If year is not divisible by 4
		else
			// Flag dealing- Non leap-year
			is_leap_year = false;
		if (!is_leap_year)
			System.out.println(year + " : Non Leap-year");
		else
			System.out.println(year + " : Leap-year");
	}

	// Main Driver Code
	public static void main(String[] args)
	{
		// Calling our function by
		// passing century year not divisible by 400
		isLeapYear(2000);

		// Calling our function by
		// passing Non-century year
		isLeapYear(2002);
	}
}
```
---

# Practical 3 :
## Write a program in java that has overloaded methods. The first methods should have no arguments. The second method should accept one string argument and third method should accept one string and one integer argument. The first method should display “Delhi is an important city” twice. The second method should display “Bombay is a beautiful city” thrice and third method should display “Chennai is a peaceful city” four times.

```java
class Overload {

    String s1, s2;
    int i, i1;

    void show() {
        for (int j = 0; j < 2; j++) {
            System.out.println("Delhi is an important city");
        }
        
    }

    void show(String s) {
        s1 = s;
        for (i = 0; i <= 2; i++)
        {
            System.out.println(s1);
        }
    }

    void show(String s, int i) {
        s2 = s;
        i1 = 0;
        while (i1 < i) {
            System.out.println(s2);
            i1++;
        }
    }
}

class GFG {

    public static void main(String[] args) {
        Overload obj1 = new Overload();
        obj1.show();
        System.out.println("\n");
        obj1.show("Bombay is a beautiful city");

        System.out.println("\n");
        obj1.show("Chennai is a peaceful city", 4);
    }
}

```
---
# Practical 4 :
## Write a program in java that creates an abstract class called Shape. Create subclass that calculate and displays area of rectangle and triangle.

```java
abstract class Shape {
    int l, b, h, ba;
    abstract int area();
}
class rectangle extends Shape {
    rectangle(int x, int y) {
        l = x;
        b = y;
    }
    int area() {
        return l * b;
    }
}
class triangle extends Shape {
    triangle(int a, int b) {
        ba = a;
        h = b;
    }
    int area() {
        return (ba * h) / 2;
    }
}
public class GFG {
    public static void main(String[] args) {
        Shape s1;
        rectangle r = new rectangle(10, 20);
        triangle t = new triangle(20, 40);
        int z;
        s1 = r;
        z = s1.area();
        System.out.println("Area of rectangle:" + z);
        s1 = t;
        z = s1.area();
        System.out.println("Area of triangle:" + z);
    }
}

```
---

# Practical 5 :
## Write a program in java to accept values for multithread.

```java
class A extends Thread
{
    public void run()
    {
        for (int i=1; i<=5; i++)
        {
            System.out.println("From thread A:i="+ i);
          }
            System.out.println("Exit from thread A" );
      }
}
class B extends Thread
{
    public void run()
    {
        for (int j=1; j<=5; j++)
        {
            System.out.println("From thread B: j="+ j);
         }
            System.out.println("Exit from thread B");
      }
}
class C extends Thread
{
    public void run()
    {
        for (int k=1; k<=5; k++)
        {
            System.out.println("From thread C: k="+ k);
         }
            System.out.println("Exit from thread C");
      }
}
public class Thread_demo {
    public static void main(String[] args) {
        new A().start();
        new B().start();
        new C().start();
  }
}

```
---

# Practical 6 :
## Write a program to demonstrate multiple inheritance through interface

```java
class person 
{
    String name;
    int age;
    String address;
    void persondetails(String nm, int ag, String add)
    {
        name=nm;
        age=ag;
        address=add;
     }
    void displayperson()
    {
        System.out.println("Name:"+ name);
         System.out.println("Age:"+ age);
         System.out.println("Address:"+ address);
    }
}
 class Employee extends person
 {
     int empid;
     int salary;
  void empdetails(int id, int sal)
 {
 empid = id ;
 salary = sal;
 }
 void displayemployee()
 {
     System.out.println("Empid:"+ empid);
     System.out.println("Salary:"+ salary);
 }
 }
interface Bonus{
    int bonus =1000;
    void compute();
}
class Faculty extends Employee implements Bonus
{
    int amount; 
    public void compute()
    {
        System.out.println("Bonus:"+ bonus);
        amount = salary+ bonus;
    }
    void Facultydetails()
    {
        displayperson();
        displayemployee();
        compute();
        System.out.println("the total amount is:"+amount);
        
    }
}
 public class MultipleInheritance{

    public static void main(String[] args)
    {
        Faculty obj = new Faculty();
        obj.persondetails("surbhi", 23, "friends colony");
        obj.empdetails(001,20000);
        obj.Facultydetails();
        System.out.println("");
        
        obj.persondetails("mili", 27, "jafar nagar");
        obj.empdetails(002,30000);
        obj.Facultydetails();
     }
}
```
---

# Practical 7 :
## Write a program to illustrate exception using multiple catch statement.

```java
class MyException extends Exception
{
   MyException(String message)
  {
    super(message);
  }
}
 class TestMyException {
 public static void main(String args[])
 {
     int x=5, y=1000;
     try
     {
         float z =(float)x/(float)y;
         if(z<0.01)
         {
         throw new MyException("number is too small");
         }    
     }
 catch(MyException e){
     System.out.println("caught MyException");
     System.out.println(e.getMessage());
     System.out.println(e);
 }
catch(Exception e){
System.out.println(e);
}
     finally
     {
         System.out.println("i am always here");
     }

}
  }
```
---

# Practical 8 :
##  Program to create Lamp using Applet

```java
import java.applet.Applet;
import java.io.*;
import java.awt.Graphics;


public class AppletLamp extends Applet 
{
 public void paint(Graphics g)
    {
        g.fillRect(0,250,290,290);
        
        g.drawLine(125, 250, 125, 160);
        g.drawLine(175, 250, 175, 160);
        
        g.drawArc(85, 157, 130, 50, -65, 312);
        g.drawArc(85, 87, 130, 50, 62, 58);
        
        g.drawLine(85, 177, 119, 89);
        g.drawLine(215, 177, 181, 89);
        
        g.fillArc(78, 120, 40, 40, 63, -174);
         g.fillOval(120, 96, 40, 40);
          g.fillArc(173, 100, 40, 40, 110, 180);
    }
    
}
```
---

# Practical 9 :
##  Write a program to create an application which shows the menu.  

```java
import java.awt.Frame;
import java.awt.Menu;
import java.awt.MenuBar;
import java.awt.MenuItem;

 class MyMenu extends Frame {
    MenuBar bar;
    Menu menu1, menu2, menu3;
    MenuItem MenuItem1, MenuItem2, MenuItem3, MenuItem4;
    MyMenu(String s)
    {
        super(s);
        setSize(400, 400);
        bar= new MenuBar();
        menu1 = new Menu("FILE");
        menu1 = new Menu("EDIT");
        menu1 = new Menu("VIEW");
   
        MenuItem1= new MenuItem("NEW");
        MenuItem2= new MenuItem("OPEN");
        MenuItem3= new MenuItem("SAVE");
        MenuItem4= new MenuItem("EXIT");
        
        menu1.add(MenuItem1);
        menu1.add(MenuItem2);
        menu1.add(MenuItem3);
        menu1.add(MenuItem4);
        
        bar.add(menu1);
        bar.add(menu2);
        bar.add(menu3);
      
        setMenuBar(bar);
    }
    public static void main(String args[])
    {
        MyMenu m = new MyMenu("MyMenu");
        m.setVisible(true);

    }  

    }

```
---   

# Practical 10 :
##  Write a program for creation of input dialog box.  

```java
import java.awt.FlowLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JApplet;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

public class TenActionInputDialog extends JApplet implements ActionListener{
   private static final long serialVersionUID = 1L;
    JFrame jf;
    JButton b1;
    JLabel l1;

    public TenActionInputDialog ()
    {
        jf=new JFrame("Demo of an Input dialog box");
        l1= new JLabel();
        jf.setLayout(new FlowLayout());
        jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        b1= new JButton("Name");
        b1.addActionListener(this);
        jf.setSize(350,200);
        jf.add(b1);
        jf.add(l1);
        jf.setVisible(true);
      }

    public void actionPerformed(ActionEvent e)
    {
        if (e.getSource()==b1)
        {
            int i = JOptionPane.QUESTION_MESSAGE;
            String pstr = JOptionPane.showInputDialog(jf, "What is your name?"," Input Dialog Box",i);
            l1.setText("Your name is :" +pstr);
        }
    }
    
    public static  void main(String str[])
    {
        TenActionInputDialog aid = new TenActionInputDialog(); 

    }
}
```
---
