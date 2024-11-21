# Table of Contents
1. [Practical 1](#practical-1-)
2. [Practical 2](#practical-2-)
3. [Practical 3](#practical-3-)
4. [Practical 4](#practical-4-)
5. [Practical 5](#practical-5-)

---
# Practical 1 : 
## WAP in java to create a class for employee record with two constructor, first default constructor to initialize all variables, second parametarized constructor to accept the employee details and a method to display employee details

```java
class Employee {
    int empId ;
    String empName;
    double empSalary;
    
    Employee(){
    	empId = 1;
        empName = "Dev";
        empSalary = 10000.00;
    }
    
    Employee(int empId, String empName, double empSalary){
    	this.empId = empId;
        this.empName = empName;
        this.empSalary = empSalary;
    }
    
    void display() {
      System.out.println("Employee ID: " + empId);
      System.out.println("Employee Name: " + empName);
      System.out.println("Employee Salary: $" + empSalary);
  }
}

public class Main {
  public static void main(String[] args) {
    Employee e1 = new Employee();
    System.out.println("Details from default constructor:");
    e1.display();
    
    Employee e2 = new Employee(2, "Sujata", 15000.00);
    System.out.println("Details from parameterized constructor:");
    e2.display();
    
  }
}

```
