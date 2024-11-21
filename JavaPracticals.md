# Table of Contents
1. [Practical 1](#practical-1-)
2. [Practical 2](#practical-2-)
3. [Practical 3](#practical-3-)
4. [Practical 4](#practical-4-)
5. [Practical 5](#practical-5-)

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
