# Java Interview Questions!

**Static** - methods and members. If given to variable or method they act as a single value and any modification made on them are constant among all objects  
1. static methods can access static members directly

2. static methods needs a object to access non-static members

3. Non-static methods can access all static and non-static members directly

4. In case another class is created you would need an object to access both.


## Overloading and polymorphism -

The oops concept where you keep all the methods as same name with different data types of parameters or number of parameters or order of parameters .  
  
Keeping multiple methods with same name is overloading.

## Inheritance and Overriding -

Acquiring all the properties & behaviour from one class to another.  
  
Parent - SuperClass  
Child - SubClass  
  
Pros:  
  
1. reusability  
2. avoid duplication  
  
Types:  
  
1. single  
2. multi level  
3. hierarchy - single parent with multiple child’s  
4. multiple - multiple parent having same child -> not supported in class  
  
**Overriding** is when a child class has the implementation of a method already defined/present in super class

## Final and Super

When initialised to a variable it cannot be changed / modified  
  
Super - If I want to get the get the function of parent class while initialising the object of child class. The function should not be override with the child class method.  
  
in this format you can use -  
  
 1. 
```
 class Parent { 
    String colour = “parent”;
  }  
class Child extends Parent 
{
     String colour = “black ” ;
     void displayColor() {  
         System.out.println(super.colour);  
       }
 }  
```
2.
```
class Parent {  
   String colour = “parent”;  
  
   void eat() {  
     System.out.println(“eating”);  
  }  
  
} 
 
class Child extends Parent {  
	String colour = “black ”;

	void eat() {  
		System.out.println(“eating child”);  
		super.eat();  
	}  
}
```

## Abstraction

Abstraction is hiding the implementation details and showing only the functionality to the user.  
  
1. Abstract Class  
2. Interface

## Primitive and Non-primitive
Primitive data types are those data types which can be directly stored on the memory like int, long, double, byte, short and char  
  
Non-primitive data types are those data types where the reference of the memory is stored on stack and the object is stored on heap like string, object, class, array, interfaces.

## JVM, JRE, JDK, JIT and ClassLoader

**JVM** is known as Java Virtual Machine is a part of JRE. JVM is the type of interpreter responsible for converting byte code to machine readable code  
  
**JRE** is Java Runtime Environment, a installation package to provide an environment to run Java program and application  
  
**JDK** is Java Development Kit which provides environment to develop and execute java programs  
  
**JIT** is Just In Time complier which is a part of JRE it is used for better performance of the Java application during runtime. When source code is compiled in javac to form byte code. Bytecode is passed to JVM. Jit is a part of JVM which is responsible for compiling the byte code to native machine code. As JVM calls the compile code that increases the performance and speed of the execution.  
  
> Sourcecode.java -> complier ( complied in javac )-> bytecode -> at run time ( class loader is responsible for loading the java classes and interfaces to JVM )  -> JIT complier -> Native Machine Code


# String Pool


A string pool is the heap memory where all the strings defined in the program are stored.  
  
As we know for non-primitive data types there is a reference that is stored on stack for the variable and the values are stored on heap.  
  
This makes the execution much faster as if there is 2 string made same. There will be 2 variables made on stack and they will be pointing to the same memory on heap.  
  
**Note:** To make 2 different memories in heap as well you can use new String(“Hello World” ) then this would create two different locations in heap as well

## Packages

In Java are grouping of related classes , interfaces etc . Providing access to protection and namespace management. Types are built-in and user defined

## Primitive Data Types

**There are 8 primitive data types -** boolean, byte, char, short, int, long, float, double  
  
**Non Primitive:** Reference data types will contain a memory address of the variables value because it is not able to store directly in the memory.  
  
**Types -** String, Array, Class, Object, Interface

## Byte


**Byte** datatype is a 8 bit signed two-complement integer. The range is -128 to 127

## Pointers 
  
There are no pointers in java as this java is meant to be secure.


# Wrapper class


Wrapper in general is larger entity encapsulating smaller entity. A Wrapper class is an object class that encapsulates the primitive data types.  
  
Primitive data types are once from which further data types can be created. Ex. Integers can further lead to the construction of long, byte, short etc. On the other hand, string cannot .  
  
Java has 8 wrapper classes. They are boolean, byte, short, long, double, float, int and char  
  
We need wrapper classes as -  
  
1. They are final and immutable  
2. Provides methods like valueOf() and parseInt() etc.  
3. Provides auto boxing and unboxing.

## Instance Variable vs Local variables

The instance variables has a default value and can be accessed throughout the class. It can be declared outside the method, directly invoked by the method.  
  
Local variables does not have a default value, the scope is limited to a method and declared only within the method

## Default values of data types

byte, short, int, long, float and double is 0.  
boolean is false  
classes, interfaces and arrays is null  
char is null character whose default value of “u0000”

## Encapsulation 

In Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit

## Note

Uppercase letters range is 65 to 90


# Int and Integer

Int is a primitive data type representing 32-bit integer. Default value is 0.  
  
**Ex.** Int a=0  
  
Integer is a class in java.lang and it represents an object that holds a single int value. Default value is null

**Ex.** Integer num = new Integer(10);


## WebDriver


` WebDriver driver = new ChromeDriver()`
      
  Here WebDriver is the interface , driver is the variable, new ChromeDriver() is creating an instance of the chrome browser and assigning it to the driver variable.

## Create an object of the Employee class

Check the ID of the employee and update the name of the employee here. 
```
class Employee {
    private int id;
    private String name;
    private int age;
    private String[] skills;

    // Constructor
    public Employee(int id, String name, int age, String[] skills) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.skills = skills;
    }

    // Getters
    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Employee{id=" + id + ", name='" + name + "', age=" + age + ", skills=" + String.join(", ", skills) + "}";
    }
}

public class UpdateEmployee {
    public static void main(String[] args) {
        // Create an Employee object
        Employee employee = new Employee(2, "Bob", 25, new String[]{"C#", "JavaScript"});

        // Print original employee details
        System.out.println("Before update: " + employee);

        // Update the name of the employee with id = 2
        updateEmployeeName(employee, 2, "Robert");

        // Print the updated employee details
        System.out.println("After update: " + employee);
    }

    // Method to update the name of an employee based on ID
    public static void updateEmployeeName(Employee employee, int id, String newName) {
        if (employee.getId() == id) {
            employee.setName(newName);
        }
    }
}

```

## Create a Employee List

Create a employee list and update name of one of the employee based on the id 
```
import java.util.ArrayList;
import java.util.List;

class Employee {
    private int id;
    private String name;
    private int age;
    private String[] skills;

    // Constructor
    public Employee(int id, String name, int age, String[] skills) {
        this.id = id;
        this.name = name;
        this.age = age;
        this.skills = skills;
    }

    // Getters
    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    // Setter for name
    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Employee{id=" + id + ", name='" + name + "', age=" + age + ", skills=" + String.join(", ", skills) + "}";
    }
}

public class EmployeeList {
    public static void main(String[] args) {
        // Create a list of Employee objects
        List<Employee> employees = new ArrayList<>();

        // Adding employees to the list
        employees.add(new Employee(1, "Alice", 30, new String[]{"Java", "Python"}));
        employees.add(new Employee(2, "Bob", 25, new String[]{"C#", "JavaScript"}));
        employees.add(new Employee(3, "Charlie", 35, new String[]{"PHP", "Ruby"}));

        // Update the name of the employee with id = 2
        updateEmployeeName(employees, 2, "Robert");

        // Print the updated list of employees
        for (Employee employee : employees) {
            System.out.println(employee);
        }
    }

    // Method to update the name of an employee based on ID
    public static void updateEmployeeName(List<Employee> employees, int id, String newName) {
        for (Employee employee : employees) {
            if (employee.getId() == id) {
                employee.setName(newName);
                break; // Exit the loop once the employee is found and updated
            }
        }
    }
}

```


