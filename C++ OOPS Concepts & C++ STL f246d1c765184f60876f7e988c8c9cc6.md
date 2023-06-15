# C++ OOPS Concepts & C++ STL

### What is OOPS ?

Full form → Object oriented programming 

It is a programming technique /paradigm (paradigm means classifying languages based on features )

It revolves around objects 

Imperative programming paradigm→ OOPS, Procedural, Parallel

Declarative → Logical ,Functional, Database 

### What is object ?

Object = Any entity with —> state  + behaviour 

### Why we use object ?

Improves : Readability, Manageability, Extensibility  

### What is class ?

It is user defined datatype 

Made up of → data members + functions 

### Class vs Object

1. For a class no memory is allocated  WHEREAS object has its own memory 
2. Class can exist without object WHEREAS object cannot exist without class
3. Class is a logical entity WHEREAS object is a physical entity 
4. Class is blue print from which objects are created WHEREAS  object is an instance of class

### Examples of Class and Objects

Suppose we have a class named Student .

Let us assume each student has some features like : Name, Roll and Gender 

Suppose we have 3 students namely A, B and C

A has its own → Name, Roll, Gender

B has its own → Name, Roll, Gender 

C has its own → Name, Roll, Gender 

These features Name , Roll and Gender are nothing but DATA MEMBERS of Class Student 

The Students A, B and C are nothing but OBJECTS 

![Screenshot 2023-06-13 at 3.42.50 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_3.42.50_PM.png)

### How to represent Class student in code ?

`class Student`

`{`

`string Name;`

`int Roll;`

`bool Gender;`

`};`

### How to create objects of class Student A and assign values?

This code creates an object of class Student named A. 

Syntax : `<class_name> <object_name>`

```
Student A;  
```

We can now access the data members of the object using the dot operator. For example, to set the name, roll and gender  of the student A, we can use the following code:

```
A.Name = "Raju";
A.Roll = 10;
A.gender = false;
```

Overall code to  :

![Screenshot 2023-06-13 at 3.54.42 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_3.54.42_PM.png)

### How to print A’s information?

For that we can create a print Information function inside the class Student 

```cpp
void printInformation()
    {
        cout << Name << endl;
        cout << Roll << endl;
        cout << Gender << endl;
    }
```

And then we can call it using the . operator —> A.printInformation();

Overall code to print A’s information:

![Screenshot 2023-06-13 at 4.00.06 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_4.00.06_PM.png)

Output:

![Screenshot 2023-06-13 at 4.00.45 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_4.00.45_PM.png)

### How to access the private members of a class outside the class? → setters

To access the private members of class outside the class we can use **Setter**.

 Syntax of setter:

`void setNewName(string s)
{
Name = s;
}`

Then in main function we can do `A.setNewName(”Raju”);`

Overall code of using setter to access private value:

![Screenshot 2023-06-13 at 4.11.16 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_4.11.16_PM.png)

# Constructors:-

1. Always invoked during the time of object creation
2. Has no return type
3. Has same name as class name 
4. If no constructor is created by user then default constructor is called by default

How to print a default constructor?

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string Name;
    int Roll;
    bool Gender;

    // Default constructor example
    Student()
    {
        cout << "Default constructor printed" << endl;
    }

    void printInformation()
    {
        cout << Name << endl;
        cout << Roll << endl;
        cout << Gender << endl;
    }
};

int main()
{
    Student A; // Calling the default constructor 

}
```

How to implement parametrised constructor?

These are constructors accepting more than one parameter

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string Name;
    int Roll;
    bool Gender;

    // Parameterised constructor example
    Student(string n, int r, bool g)
    {
        cout << "Paramaterised constructor printed" << endl;
    }

    void printInformation()
    {
        cout << Name << endl;
        cout << Roll << endl;
        cout << Gender << endl;
    }
};

int main()
{
    Student A("Raju", 10, false); // the parameterized constructor
// of the Student class is called with the provided arguments.
}
```

How to implement copy constructor?

Takes class as argument

 

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string Name;
    int Roll;
    bool Gender;

    // Parameterised constructor example
    Student(string n, int r, bool g)
    {
        cout << "Paramaterised constructor printed" << endl;
    }

    // Copy constructor example
    Student(Student &A)
    {
        Name = A.Name;
        Roll = A.Roll;
        Gender = A.Gender;
        cout << "Copy constructor printed" << endl;
    }

    void printInformation()
    {
        cout << Name << endl;
        cout << Roll << endl;
        cout << Gender << endl;
    }
};

int main()
{
    Student A("Raju", 10, false);
    Student Z = A; // I want to assign all values of A in Z
}
```

The copy constructor created inside class Student takes a reference to a **`Student`** object **`A`** as a parameter and copies the values of its member variables (**`Name`**, **`Roll`**, **`Gender`**) to the corresponding member variables of the newly created object.

# Destructors:-

Deallocates memory 

Follows same syntax as constructors but prefixed with ~

Called when the lifecycle of object ends

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string Name;
    int Roll;
    bool Gender;

    // Parameterised constructor example
    Student(string n, int r, bool g)
    {
        cout << "Paramaterised constructor printed" << endl;
    }

    // Copy constructor example
    Student(Student &A)
    {
        Name = A.Name;
        Roll = A.Roll;
        Gender = A.Gender;
        cout << "Copy constructor printed" << endl;
    }
     
    //Destructor example
    ~Student()
    {
        cout << "Destructor called" << endl;
    }

    void printInformation()
    {
        cout << Name << endl;
        cout << Roll << endl;
        cout << Gender << endl;
    }
};

int main()
{
    Student A("Raju", 10, false);
    Student Z = A; 
}
```

![Screenshot 2023-06-13 at 4.40.01 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_4.40.01_PM.png)

# Inheritance in C++

Class is made up of → data members & functions

Inheriting data members & functions from a parent class to a child class is called as Inheritance

Parent class is also called Super Class or Base Class

Child class is also called as Sub Class

Advantages of inheritance:

1. Increases code reusability 
2. Run time  polymorphism achieved through Inheritance

TYPES of Inheritance:

1. Hierarchical Inheritance( 1 parent for more than 1 class)
2. Multiple Inheritance ( 2 parents 1 child)
3. Multilevel Inheritance(like a family tree, where each generation inherits characteristics from the previous generation. )
4. Hybrid Inheritance ( Mixture of multiple inheritances)
5. Single level

Diagram for TYPES of Inheritance:

![Screenshot 2023-06-13 at 5.47.29 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_5.47.29_PM.png)

### Inheritance ambiguity and How to solve it ?

![Screenshot 2023-06-13 at 5.54.33 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-13_at_5.54.33_PM.png)

```cpp
//We use scope resolution operator to solve the issue of inheritence ambiguity
#include <iostream>
using namespace std;

// Parent class A
class A {
public:
    void display() {
        cout << "Base class A" << endl;
    }
};

// Parent class B
class B {
public:
    void display() {
        cout << "Base class B" << endl;
    }
};

// Derived class C, inheriting from A and B
class C : public A, public B {
public:
    void display() {
        cout << "Derived class C" << endl;
    }

    void show() {
        A::display(); // Access display() from class A
        B::display(); // Access display() from class B
        display();    // Access display() from class C
    }
};

int main() {
    C obj;
    obj.show();

    return 0;
}
```

# Polymorphism:

Ability to exist in various forms

Polymorphism is of two types : `Runtime` Polymorphism and `Compile time` Polymorphism

Compile time polymorphism further divided into → `Function overloading` and `Operator overloading`  

![Screenshot 2023-06-14 at 9.41.45 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_9.41.45_AM.png)

## FUNCTION OVERLOADING:

→ Two functions have same name 

→It doesn’t show error if :

1. No. of param are diff
2. Type of param are diff

→It shows error in these cases: Cant be overloaded .

```cpp
//cannot be overloaded 
int Add()
void Add() 
```

Function overloading Example :(difference in `no.of param`):-

![Screenshot 2023-06-14 at 9.28.46 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_9.28.46_AM.png)

Function overloading Example :(difference in `type of param`):-

![Screenshot 2023-06-14 at 9.32.19 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_9.32.19_AM.png)

OPERATOR OVERLOADING:

Plus(+) is used for addition 

Plus(+) is also used for concatenation

This is called Operator Overloading 

### RUNTIME POLYMORPHISM:

Functions are invoked during program execution.

It is achieved through the use of inheritance.

The decision is made at run time and not compile time.

![Screenshot 2023-06-14 at 9.41.45 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_9.41.45_AM.png)

## Function overriding:

Runtime polymorphism includes the ability to override functions.

In the case of function overriding, multiple methods with the same name and different types of parameter lists are used

It's done with the help of `virtual functions` and `pointers`

**What is a virtual function in C++ and how to achieve Runtime Polymorphism using this ?**

A virtual function is a base class member function that will be redefined in derived classes.

The virtual function must be declared using the virtual keyword in the base class.

When we announce a virtual function, the compiler decides which one to call at runtime.

Runtime polymorphism using (`virtual function and pointers` )

```cpp
#include <iostream>
using namespace std;

// defining the base class
class Base_class
{
public:
    int base_var = 25;

    // defining display function as virtual to override it in derived class
    virtual void display()
    {
        cout << "The value of the base variable is: " << base_var << endl;
    }
};

// defining the derived class
class Derived_class : public Base_class
{
public:
    int derived_var = 80;

    // Overriding the display function
    void display()
    {
        cout << "The value of the base variable is: "
             << base_var << endl
             << "The value of the derived variable is: "
             << derived_var << endl;
    }
};

int main()
{

    Derived_class obj;
    Base_class *ptr = &obj;
    ptr->display();

    return 0;
}
```

In the provided example, the **`virtualFunction()`** in the **`Base_class`** is declared as a virtual function. This means that it can be overridden by a function with the same name and signature in the derived class, **`Derived_class`**

When the **`display()`** function is called using a **`ptr`** pointing to an object of the derived class, the actual implementation of the function that gets executed is determined based on the type of the object being referred to at runtime. This is known as  `runtime polymorphism.`

# ENCAPSULATION:

Concept where `Data members` and `functions` wrapped under a single entity (called as an `object` or `class` )

What is fully encapsulated class ? → Where all the data members are marked private 

Advantages of Encapsulation:

1. Helps in data hiding 
2. Improves security and used in Unit Testing 
3. We can make a class read-only
4. Increases code readability 

However if we want to access the private members we can use `Getters` and `Setters` 

Example of getters and setters :

```cpp
#include <iostream>
using namespace std;

class Student
{
private:
    string Name;
    int Roll;
    bool Gender;

public:
    void setNewName(string s)
    {
        Name = s;
    }

    string getName() const
    {
        return Name;
    }

    void setRoll(int roll)
    {
        Roll = roll;
    }

    int getRoll() const
    {
        return Roll;
    }

    void setGender(bool gender)
    {
        Gender = gender;
    }

    bool getGender() const
    {
        return Gender;
    }

    void printInformation()
    {
        cout << "Name: " << Name << endl;
        cout << "Roll: " << Roll << endl;
        cout << "Gender: " << Gender << endl;
    }
};

int main()
{
    Student A;
    A.setNewName("Raju");
    A.setRoll(10);
    A.setGender(true);

    cout << "Name: " << A.getName() << endl;
    cout << "Roll: " << A.getRoll() << endl;
    cout << "Gender: " << A.getGender() << endl;

    return 0;
}
```

Output:

Name: Raju
Roll: 10
Gender: 1

# ABSTRACTION:

Hiding the  background details and delivering only essential information to the outer world is called Abstraction

Real life example of abstraction: 

A mobile user uses various mobile phone functionalities, such as calls, SMS, etc. But the actual implementation details of these functions are hidden from the mobile user. This is an example of abstraction

### Ways to achieve abstraction:-

1. Using Header files 
2. Using classes 
3. Using abstract methods 

Using Header files 

Abstraction can also be achieved using header files as we hide the function's implementation in header files. We could use that same function in our program without knowing its inside workings. Sort(), for example, is used to sort an array, a list, or a collection of items, and we know that if we give a container to sort, it will sort it, but we don't know which sorting algorithm it uses to sort that container.

`test.h`

```cpp
#ifndef TEST_H
#define TEST_H

void printMessage(); // Function declaration

#endif
```

`test.cpp`

```cpp
// test.cpp (Source file)
#include <iostream>
#include "test.h" // Include the header file

void printMessage() // Function definition
{
    std::cout << "Hello, this is a message from the header file!" << std::endl;
}

// main.cpp (Usage)
#include "test.h" // Include the header file

int main()
{
    printMessage(); // Call the function defined in the header file
    return 0;
}
```

Using classes 

Classes can be used to implement Abstraction in C++. We may group data members and member functions into classes using the available access specifiers. A Class can choose which data members are visible to the outside world and which are hidden.

Example of abstraction using classes :

```cpp
#include <iostream>

class TestAbstraction
{
private:
    int privateData;

public:
    void setPrivateData(int data) // Setter function to set the private data
    {
        privateData = data;
    }

    void displayPrivateData() // Function to display the private data
    {
        std::cout << "Private Data: " << privateData << std::endl;
    }
};

int main()
{
    TestAbstraction obj;
    obj.setPrivateData(42);
    obj.displayPrivateData();
    return 0;
}
```

Using abstract methods 

Abstract methods are pure virtual functions defined in a base class that have no implementation.

```cpp
#include <iostream>

class AbstractBase
{
public:
    virtual void abstractMethod() = 0; // Pure virtual function (Abstract Method)
};

class ConcreteDerived : public AbstractBase
{
public:
    void abstractMethod() override // Implementation of the abstract method
    {
        std::cout << "This is the implementation of the abstract method." << std::endl;
    }
};

int main()
{
    ConcreteDerived obj;
    obj.abstractMethod();
    return 0;
}
```

Other examples for abstraction:

```
#include <iostream>

using namespace std;

class TestAbstraction
{
private:
    string x, y;

public:
    // method to set values of
    // private members
    void set(string a, string b)
    {
        x = a;
        y = b;
    }
    // printing values
    void print()
    {
        cout << "x = " << x << endl;
        cout << "y = " << y << endl;
    }
};

int main()
{
    // object of TestAbstraction
    TestAbstraction t1;
    t1.set("Amit", "Patnaik");
    t1.print();

    return 0;
}
```

```cpp
#include <iostream>

using namespace std;

// Abstract base class
class AbstractClass
{
public:
    virtual void AbstractMethod() = 0;
};

// Concrete derived class
class ConcreteClass : public AbstractClass
{
public:

    void AbstractMethod() override
    {
        cout << "Implementation of AbstractMethod in the derived class" << endl;
        cout << "This is an example implementation of AbstractMethod." << endl;
        cout << "Hello from ConcreteClass!" << endl;
    }
};

int main()
{
    ConcreteClass obj;
    obj.AbstractMethod(); // Call the implementation in the derived class

    return 0;
}
```

It defines a common `interface` in the `abstract base class` and allows derived classes to provide their specific implementations for the `abstract method`. 

This promotes code organisation, reusability, and the ability to work with different derived classes through a unified interface.

### What is abstract class?

An abstract class is used to provide a suitable base class from which additional classes can be derived, or we can say that we could form a blueprint to derive more classes. Abstract classes only provide a user interface; they cannot be used to construct objects. When an object of abstract classes is attempted to be instantiated, a compilation error occurs. In C++, data abstraction is also implemented using abstract classes.

### Design strategy for abstraction:

Abstraction divides code into two categories: `interface` and `implementation`. So, when creating your component, keep the interface separate from the implementation so that if the underlying implementation changes, the interface stays the same.

In this instance, any program that uses these interfaces would remain unaffected and would require recompilation with the most recent implementation.

### Abstract class vs interface keyword

![Screenshot 2023-06-14 at 1.46.56 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_1.46.56_PM.png)

# C++ STL

[C++ STL theory diagrams.pdf](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/C_STL_theory_diagrams.pdf)

C++ STL are used as :-

1. `FUNCTIONS`
2. `CONTAINERS`

→ Helps us with algorithms like searching, sorting . In this we call them as `functions`

→Helps us to create stack, queue, array ,vectors ,unordered maps,. In this we use them as `containers`

These `containers`  are built using template classes ⇒ We can store any `DATATYPE` or `OBJECT` inside it . 

What are containers ?

→CONTAINER IS AN OBJECT THAT STORES COLLECTION OF OTHER OBJECTS(ELEMENTS)

→CONTAINER MANAGES THE STORAGE SPACE FOR IT'S ELEMENTS AND PROVIDES MEMBER FUNCTIONS TO ACCESS THEM (MOSTLY THROUGH `ITERATORS`)

Containers can store : 

1. `Datatypes` 
2. `Objects` 

![Screenshot 2023-06-14 at 11.26.34 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_11.26.34_PM.png)

Each object have their own data members or properties.

`Iterators :` They are Objects in form of Pointers 

Usage of iterator:

→ For accessing array elements we can use indexing like a[0], a[1], a[2]….

→But for complex DS like trees and linked list we cannot use indexing to access elements . Instead we must use iterators.

CATEGORY OF CONTAINERS :

![Screenshot 2023-06-14 at 11.41.52 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_11.41.52_PM.png)

SEQUENCE CONTAINERS:

![Screenshot 2023-06-15 at 12.30.02 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_12.30.02_AM.png)

ASSOCIATIVE CONTAINERS

![Screenshot 2023-06-15 at 12.32.31 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_12.32.31_AM.png)

UNORDERED ASSOCIATIVE CONTAINERS:

![Screenshot 2023-06-15 at 12.34.14 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_12.34.14_AM.png)

![Screenshot 2023-06-15 at 12.35.12 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_12.35.12_AM.png)

### NOTES WITH DETAIL ON THE ABOVE STL:

# Arrays :

→ Stored in contiguous memory location

→ Cannot introduce gaps in arrays 

![Screenshot 2023-06-14 at 8.22.02 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_8.22.02_PM.png)

Diadvantage of array:

1. As we always have to store array in contiguous memory location, already occupied memory cannot be replaced. So we use a concept called Linked list to solve this .
    
    ![Screenshot 2023-06-14 at 8.42.59 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_8.42.59_PM.png)
    

1. We cannot increase the size of array . So we have concept called Vectors to solve this.

![Screenshot 2023-06-14 at 8.37.14 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_8.37.14_PM.png)

![Screenshot 2023-06-15 at 12.37.39 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_12.37.39_AM.png)

Code(Classical Arrays)

```cpp
#include <iostream>
using namespace std;
int main()
{
    // Classical arrays
    int arr[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " " << endl;
    }
}
```

Function to update array (Classical Arrays )

```cpp
#include <iostream>
using namespace std;

void Update(int arr[], int i, int updatedval)
{
    arr[i] = updatedval;
}

int main()
{

    int arr[] = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);

    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
//Output: 1 50 3 4 5
```

```cpp
//Arrangement of classical array in memory address 
2000 2004 2008 2012 2016
1     2    3     4    5
```

Printing the size of array inside and outside the main function()

```cpp
#include <iostream>
using namespace std;

void Update(int arr[], int i, int updatedval)
{
    arr[i] = updatedval;
}
void sizeOfUpdatedArray(int *arr)
{
    cout << "Size of updated array outside main is : " << sizeof(arr) << endl;
}
int main()
{

    int arr[] = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);

    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
    cout << "Size of updated array inside main is : " << sizeof(arr) << endl;
    sizeOfUpdatedArray(arr);

    return 0;
}
//Output
1 50 3 4 5 
Size of updated array inside main is : 20
Size of updated array outside main is : 8
```

Here in function `sizeOfUpdatedArray` the array’s base address of 2000 is stored in pointer `arr` 
So when we print the size we get : 8 (size of pointer as per architecture of the system)

So if we need to print the size of array we have to pass size to the function

```cpp
#include <iostream>
using namespace std;

void Update(int arr[], int i, int updatedval)
{
    arr[i] = updatedval;
}

void sizeOfUpdatedArray(int *arr, int n)
{
    cout << "Size of updated array outside main is: " << n << endl;
    cout << "Space occupied by ponter arr inside memory:" << sizeof(arr) << endl;
}

int main()
{
    int arr[] = {1, 2, 3, 4, 5};
    int n = sizeof(arr) / sizeof(int);

    Update(arr, 1, 50);
    sizeOfUpdatedArray(arr, n);

    cout << "Updated array: ";
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }

    cout << endl;
    cout << "Space occupied by array inside memory:" << sizeof(arr) << endl;

    return 0;
}
//output:
Size of updated array outside main is: 5
Space occupied by ponter arr inside memory:8
Updated array: 1 50 3 4 5 
Space occupied by array inside memory:20
```

Syntax (STL Arrays):

→ Use header file `#include<array>`

→Write `array` followed by `datatype`. Datatype can be int char, float…. Datatype can also be a object. Then give a name. Then initialise a size for it :

Example :  `array<int,5> arr= {1, 2, 3, 4, 5};`

Code (STL Arrays):

```cpp
#include <iostream>
#include <array>
using namespace std;

int main()
{
    array<int, 5> arr = {1, 2, 3, 4, 5};
    for (int i = 0; i < arr.size(); i++)
    {
        cout << arr[i] << " ";
    }
}
```

Function to update array (STL Arrays ):

```cpp
#include <iostream>
using namespace std;

void Update(array<int, 5> arr, int i, int updatedval)
{
    arr[i] = updatedval;
}

int main()
{

    array<int, 5> arr = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);

    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
//Output:
1 2 3 4 5 (Not updated)
```

Not updated because the `arr inside main` and the `arr outside main` are different. They are not pointing to the same base address 2000. To make it point to the same base address just add an & before the arr in the function:

```cpp
#include <iostream>
using namespace std;

void Update(array<int, 5> &arr, int i, int updatedval)
{
    arr[i] = updatedval;
}

int main()
{

    array<int, 5> arr = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);

    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
// Output:
// 1 50 3 4 5(Updated)
```

Printing STL array using functions:

```cpp
#include <iostream>
using namespace std;

void Update(array<int, 5> &arr, int i, int updatedval)
{
    arr[i] = updatedval;
}
void PrintSTLArray(array<int, 5> arr) //here 
{
    cout << "Printing STL Array : " << endl;
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main()
{

    array<int, 5> arr = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);
    PrintSTLArray(arr);

    return 0;
}
```

Now updating a value in STL Array :

```cpp
#include <iostream>
using namespace std;

void Update(array<int, 5> &arr, int i, int updatedval)
{
    arr[i] = updatedval;
}
void PrintSTLArray(array<int, 5> arr) // normal
{
    arr[0] = 4;
    cout << "Printing STL Array : " << endl;
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main()
{

    array<int, 5> arr = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);
    PrintSTLArray(arr);

    for (int i = 0; i < arr.size(); i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
//output:
4 50 3 4 5 
1 50 3 4 5
```

Changes will happen in the arr of PrintSTLArray and `not` in the main array :

To get changes in the main array we can use : & before array

```cpp
#include <iostream>
using namespace std;

void Update(array<int, 5> &arr, int i, int updatedval)
{
    arr[i] = updatedval;
}
void PrintSTLArray(array<int, 5> &arr) //here
{
    arr[0] = 4;
    cout << "Printing STL Array : " << endl;
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main()
{

    array<int, 5> arr = {1, 2, 3, 4, 5};
    Update(arr, 1, 50);
    PrintSTLArray(arr);

    for (int i = 0; i < arr.size(); i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;
    return 0;
}
//Output
4 50 3 4 5 
4 50 3 4 5
```

It is good practice to use const to prevent any update in the array of main function

### Iterators in array STL:

```cpp
2000 2004 2008 2012 2016 2020
1     2     3    4   5
```

`array.begin()` will point to 2000

`array.end()` will point to 2020(address just next after the last element of array)

So iterators point to the address.

```cpp
#include <iostream>
#include<array>
using namespace std;

int main()
{
    array<int, 5> arr = {5, 4, 3, 2, 1};
    cout << arr.begin() << " ";
    cout << arr.end();
    return 0;
}
```

`sort(arr,arr+n);`  and `sort(arr.begin(),arr.end())`; means the same. Used for `sorting` in arrays

```cpp
#include <iostream>
#include <array>
#include <algorithm>
using namespace std;

int main()
{
    array<int, 5> arr = {5, 4, 3, 2, 1};
    int n = arr.size();
    sort(arr.begin(), arr.end());

    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
```

Filling array STL with same values: 

```cpp
#include <iostream>
#include <array>
#include <algorithm>
using namespace std;

int main()
{
    array<int, 5> filledArray;
    filledArray.fill(2);

    for (int i = 0; i < filledArray.size(); i++)
    {
        cout << filledArray[i] << " ";
    }
    cout << endl;

    return 0;
}
Output:
2 2 2 2 2 2 2 2
```

for each loop in STL

`Normal for loop` → iterates through `indexes` 

`For each loop` → iterates through `values` 

```cpp
#include <iostream>
#include <array>
#include <algorithm>
using namespace std;

int main()
{
    array<int, 5> arr = {1, 2, 3, 4, 5};
    for (int num : arr)
    {
        cout << num << endl;
    }
    return 0;
}
```

Accessing elements in arrays STL:

`arr[i]` or `arr.at(i)`

`arr.front()` and `arr.back()`

## Vectors STL :

![Screenshot 2023-06-15 at 2.50.16 AM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-15_at_2.50.16_AM.png)

```cpp
std::vector<int> v;

//---------------------------------
// General Operations
//---------------------------------

// Size
unsigned int size = v.size();

// Insert head, index, tail
v.insert(v.begin(), value);             // head
v.insert(v.begin() + index, value);     // index
v.push_back(value);                     // tail

// Access head, index, tail
int head = v.front();       // head
head = v[0];                // or using array style indexing

int value = v.at(index);    // index
value = v[index];           // or using array style indexing

int tail = v.back();        // tail
tail = v[v.size() - 1];     // or using array style indexing

// Iterate
for(std::vector<int>::iterator it = v.begin(); it != v.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove head, index, tail
v.erase(v.begin());             // head
v.erase(v.begin() + index);     // index
v.pop_back();                   // tail

// Clear
v.clear();

```

# C++ Data Structures and Algorithms Cheat Sheet

## Table of Contents

- [C++ Data Structures and Algorithms Cheat Sheet](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#c-data-structures-and-algorithms-cheat-sheet)
    - [Table of Contents](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#table-of-contents)
    - [1.0 Data Structures](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#10-data-structures)
        - [1.1 Overview](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#11-overview)
        - [1.2 Vector `std::vector`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#12-vector-stdvector)
        - [1.3 Deque `std::deque`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#13-deque-stddeque)
        - [1.4 List `std::list` and `std::forward_list`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#14-list-stdlist-and-stdforward_list)
        - [1.5 Map `std::map` and `std::unordered_map`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#15-map-stdmap-and-stdunordered_map)
        - [1.6 Set `std::set`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#16-set-stdset)
        - [1.7 Stack `std::stack`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#17-stack-stdstack)
        - [1.8 Queue `std::queue`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#18-queue-stdqueue)
        - [1.9 Priority Queue `std::priority_queue`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#19-priority-queue-stdpriority_queue)
        - [1.10 Heap `std::priority_queue`](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#110-heap-stdpriority_queue)
    - [2.0 Trees](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#20-trees)
        - [2.1 Binary Tree](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#21-binary-tree)
        - [2.2 Balanced Trees](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#22-balanced-trees)
        - [2.3 Binary Search](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#23-binary-search)
        - [2.4 Depth-First Search](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#24-depth-first-search)
        - [2.5 Breadth-First Search](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#25-breadth-first-search)
    - [3.0 NP Complete Problems](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#30-np-complete-problems)
        - [3.1 NP Complete](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#31-np-complete)
        - [3.2 Traveling Salesman Problem](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#32-traveling-salesman-problem)
        - [3.3 Knapsack Problem](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#33-knapsack-problem)
    - [4.0 Algorithms](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#40-algorithms)
        - [4.1 Insertion Sort](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#41-insertion-sort)
        - [4.2 Selection Sort](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#42-selection-sort)
        - [4.3 Bubble Sort](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#43-bubble-sort)
        - [4.4 Merge Sort](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#44-merge-sort)
        - [4.5 Quicksort](notion://www.notion.so/C-OOPS-Concepts-C-STL-f246d1c765184f60876f7e988c8c9cc6#45-quicksort)

## 1.0 Data Structures

### 1.1 Overview

## 

![Screenshot 2023-06-14 at 10.44.33 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_10.44.33_PM.png)

![Screenshot 2023-06-14 at 10.46.16 PM.png](C++%20OOPS%20Concepts%20&%20C++%20STL%20f246d1c765184f60876f7e988c8c9cc6/Screenshot_2023-06-14_at_10.46.16_PM.png)

### 1.2 Vector `std::vector`

**Use for**

- Simple storage
- Adding but not deleting
- Serialization
- Quick lookups by index
- Easy conversion to C-style arrays
- Efficient traversal (contiguous CPU caching)

**Do not use for**

- Insertion/deletion in the middle of the list
- Dynamically changing storage
- Non-integer indexing

**Time Complexity**

| Operation | Time Complexity |
| --- | --- |
| Insert Head | O(n) |
| Insert Index | O(n) |
| Insert Tail | O(1) |
| Remove Head | O(n) |
| Remove Index | O(n) |
| Remove Tail | O(1) |
| Find Index | O(1) |
| Find Object | O(n) |

**Example Code**

```cpp
std::vector<int> v;

//---------------------------------
// General Operations
//---------------------------------

// Size
unsigned int size = v.size();

// Insert head, index, tail
v.insert(v.begin(), value);             // head
v.insert(v.begin() + index, value);     // index
v.push_back(value);                     // tail

// Access head, index, tail
int head = v.front();       // head
head = v[0];                // or using array style indexing

int value = v.at(index);    // index
value = v[index];           // or using array style indexing

int tail = v.back();        // tail
tail = v[v.size() - 1];     // or using array style indexing

// Iterate
for(std::vector<int>::iterator it = v.begin(); it != v.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove head, index, tail
v.erase(v.begin());             // head
v.erase(v.begin() + index);     // index
v.pop_back();                   // tail

// Clear
v.clear();

```

---

### 1.3 Deque `std::deque`

**Use for**

- Similar purpose of `std::vector`
- Basically `std::vector` with efficient `push_front` and `pop_front`

**Do not use for**

- C-style contiguous storage (not guaranteed)

**Notes**

- Pronounced 'deck'
- Stands for **D**ouble **E**nded **Que**ue

**Time Complexity**

| Operation | Time Complexity |
| --- | --- |
| Insert Head | O(1) |
| Insert Index | O(n) or O(1) |
| Insert Tail | O(1) |
| Remove Head | O(1) |
| Remove Index | O(n) |
| Remove Tail | O(1) |
| Find Index | O(1) |
| Find Object | O(n) |

**Example Code**

```cpp
std::deque<int> d;

//---------------------------------
// General Operations
//---------------------------------

// Insert head, index, tail
d.push_front(value);                    // head
d.insert(d.begin() + index, value);     // index
d.push_back(value);                     // tail

// Access head, index, tail
int head = d.front();       // head
int value = d.at(index);    // index
int tail = d.back();        // tail

// Size
unsigned int size = d.size();

// Iterate
for(std::deque<int>::iterator it = d.begin(); it != d.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove head, index, tail
d.pop_front();                  // head
d.erase(d.begin() + index);     // index
d.pop_back();                   // tail

// Clear
d.clear();

```

---

### 1.4 List `std::list` and `std::forward_list`

**Use for**

- Insertion into the middle/beginning of the list
- Efficient sorting (pointer swap vs. copying)

**Do not use for**

- Direct access

**Time Complexity**

| Operation | Time Complexity |
| --- | --- |
| Insert Head | O(1) |
| Insert Index | O(n) |
| Insert Tail | O(1) |
| Remove Head | O(1) |
| Remove Index | O(n) |
| Remove Tail | O(1) |
| Find Index | O(n) |
| Find Object | O(n) |

**Example Code**

```cpp
std::list<int> l;

//---------------------------------
// General Operations
//---------------------------------

// Insert head, index, tail
l.push_front(value);                    // head
l.insert(l.begin() + index, value);     // index
l.push_back(value);                     // tail

// Access head, index, tail
int head = l.front();                                           // head
int value = std::next(l.begin(), index);		        // index
int tail = l.back();                                            // tail

// Size
unsigned int size = l.size();

// Iterate
for(std::list<int>::iterator it = l.begin(); it != l.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove head, index, tail
l.pop_front();                  // head
l.erase(l.begin() + index);     // index
l.pop_back();                   // tail

// Clear
l.clear();

//---------------------------------
// Container-Specific Operations
//---------------------------------

// Splice: Transfer elements from list to list
//	splice(iterator pos, list &x)
//  	splice(iterator pos, list &x, iterator i)
//  	splice(iterator pos, list &x, iterator first, iterator last)
l.splice(l.begin() + index, list2);

// Remove: Remove an element by value
l.remove(value);

// Unique: Remove duplicates
l.unique();

// Merge: Merge two sorted lists
l.merge(list2);

// Sort: Sort the list
l.sort();

// Reverse: Reverse the list order
l.reverse();

```

---

### 1.5 Map `std::map` and `std::unordered_map`

**Use for**

- Key-value pairs
- Constant lookups by key
- Searching if key/value exists
- Removing duplicates
- `std::map`
    - Ordered map
- `std::unordered_map`
    - Hash table

**Do not use for**

- Sorting

**Notes**

- Typically ordered maps (`std::map`) are slower than unordered maps (`std::unordered_map`)
- Maps are typically implemented as *binary search trees*

**Time Complexity**

**`std::map`**

| Operation | Time Complexity |
| --- | --- |
| Insert | O(log(n)) |
| Access by Key | O(log(n)) |
| Remove by Key | O(log(n)) |
| Find/Remove Value | O(log(n)) |

**`std::unordered_map`**

| Operation | Time Complexity |
| --- | --- |
| Insert | O(1) |
| Access by Key | O(1) |
| Remove by Key | O(1) |
| Find/Remove Value | -- |

**Example Code**

```cpp
std::map<std::string, std::string> m;

//---------------------------------
// General Operations
//---------------------------------

// Insert
m.insert(std::pair<std::string, std::string>("key", "value"));

// Access by key
std::string value = m.at("key");

// Size
unsigned int size = m.size();

// Iterate
for(std::map<std::string, std::string>::iterator it = m.begin(); it != m.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove by key
m.erase("key");

// Clear
m.clear();

//---------------------------------
// Container-Specific Operations
//---------------------------------

// Find if an element exists by key
bool exists = (m.find("key") != m.end());

// Count the number of elements with a certain key
unsigned int count = m.count("key");

```

---

### 1.6 Set `std::set`

**Use for**

- Removing duplicates
- Ordered dynamic storage

**Do not use for**

- Simple storage
- Direct access by index

**Notes**

- Sets are often implemented with binary search trees

**Time Complexity**

| Operation | Time Complexity |
| --- | --- |
| Insert | O(log(n)) |
| Remove | O(log(n)) |
| Find | O(log(n)) |

**Example Code**

```
std::set<int> s;

//---------------------------------
// General Operations
//---------------------------------

// Insert
s.insert(20);

// Size
unsigned int size = s.size();

// Iterate
for(std::set<int>::iterator it = s.begin(); it != s.end(); it++) {
    std::cout << *it << std::endl;
}

// Remove
s.erase(20);

// Clear
s.clear();

//---------------------------------
// Container-Specific Operations
//---------------------------------

// Find if an element exists
bool exists = (s.find(20) != s.end());

// Count the number of elements with a certain value
unsigned int count = s.count(20);

```

---

### 1.7 Stack `std::stack`

**Use for**

- First-In Last-Out operations
- Reversal of elements

**Time Complexity**

| Operation | Time Complexity |
| --- | --- |
| Push | O(1) |
| Pop | O(1) |
| Top | O(1) |

**Example Code**

```
std::stack<int> s;

//---------------------------------
// Container-Specific Operations
//---------------------------------

// Push
s.push(20);

// Size
unsigned int size = s.size();

// Pop
s.pop();

// Top
int top = s.top();

```

---

### 1.8 Queue `std::queue`

**Use for**

- First-In First-Out operations
- Ex: Simple online ordering system (first come first served)
- Ex: Semaphore queue handling
- Ex: CPU scheduling (FCFS)

**Notes**

- Often implemented as a `std::deque`

**Example Code**

```
std::queue<int> q;

//---------------------------------
// General Operations
//---------------------------------

// Insert
q.push(value);

// Access head, tail
int head = q.front();       // head
int tail = q.back();        // tail

// Size
unsigned int size = q.size();

// Remove
q.pop();

```

---

### 1.9 Priority Queue `std::priority_queue`

**Use for**

- First-In First-Out operations where **priority** overrides arrival time
- Ex: CPU scheduling (smallest job first, system/user priority)
- Ex: Medical emergencies (gunshot wound vs. broken arm)

**Notes**

- Often implemented as a `std::vector`

**Example Code**

```
std::priority_queue<int> p;

//---------------------------------
// General Operations
//---------------------------------

// Insert
p.push(value);

// Access
int top = p.top();  // 'Top' element

// Size
unsigned int size = p.size();

// Remove
p.pop();

```

---

### 1.10 Heap `std::priority_queue`

**Notes**

- A heap is essentially an instance of a priority queue
- A **min** heap is structured with the root node as the smallest and each child subsequently larger than its parent
- A **max** heap is structured with the root node as the largest and each child subsequently smaller than its parent
- A min heap could be used for *Smallest Job First* CPU Scheduling
- A max heap could be used for *Priority* CPU Scheduling

**Max Heap Example (using a binary tree)**

## 2.0 Trees

### 2.1 Binary Tree

- A binary tree is a tree with at most two (2) child nodes per parent
- Binary trees are commonly used for implementing `O(log(n))` operations for ordered maps, sets, heaps, and binary search trees
- Binary trees are **sorted** in that nodes with values greater than their parents are inserted to the **right**, while nodes with values less than their parents are inserted to the **left**

**Binary Search Tree**

## 

### 2.2 Balanced Trees

- Balanced trees are a special type of tree which maintains its balance to ensure `O(log(n))` operations
- When trees are not balanced the benefit of `log(n)` operations is lost due to the highly vertical structure
- Examples of balanced trees:
    - AVL Trees
    - Red-Black Trees

---

### 2.3 Binary Search

**Idea:**

1. If current element, return
2. If less than current element, look left
3. If more than current element, look right
4. Repeat

**Data Structures:**

- Tree
- Sorted array

**Space:**

- `O(1)`

**Best Case:**

- `O(1)`

**Worst Case:**

- `O(log n)`

**Average:**

- `O(log n)`

**Visualization:**

### 2.4 Depth-First Search

**Idea:**

1. Start at root node
2. Recursively search all adjacent nodes and mark them as searched
3. Repeat

**Data Structures:**

- Tree
- Graph

**Space:**

- `O(V)`, `V = number of verticies`

**Performance:**

- `O(E)`, `E = number of edges`

**Visualization:**

### 2.5 Breadth-First Search

**Idea:**

1. Start at root node
2. Search neighboring nodes first before moving on to next level

**Data Structures:**

- Tree
- Graph

**Space:**

- `O(V)`, `V = number of verticies`

**Performance:**

- `O(E)`, `E = number of edges`

**Visualization:**

## 

## 3.0 NP Complete Problems

### 3.1 NP Complete

- **NP Complete** means that a problem is unable to be solved in **polynomial time**
- NP Complete problems can be *verified* in polynomial time, but not *solved*

---

### 3.2 Traveling Salesman Problem

---

### 3.3 Knapsack Problem

[Implementation](notion://www.notion.so/NP-complete/knapsack/)

---

## 4.0 Algorithms

### 4.1 Insertion Sort

### Idea

1. Iterate over all elements
2. For each element:
    - Check if element is larger than largest value in sorted array
3. If larger: Move on
4. If smaller: Move item to correct position in sorted array

### Details

- **Data structure:** Array
- **Space:** `O(1)`
- **Best Case:** Already sorted, `O(n)`
- **Worst Case:** Reverse sorted, `O(n^2)`
- **Average:** `O(n^2)`

### Advantages

- Easy to code
- Intuitive
- Better than selection sort and bubble sort for small data sets
- Can sort in-place

### Disadvantages

- Very inefficient for large datasets

### Visualization

## 

### 4.2 Selection Sort

### Idea

1. Iterate over all elements
2. For each element:
    - If smallest element of unsorted sublist, swap with left-most unsorted element

### Details

- **Data structure:** Array
- **Space:** `O(1)`
- **Best Case:** Already sorted, `O(n^2)`
- **Worst Case:** Reverse sorted, `O(n^2)`
- **Average:** `O(n^2)`

### Advantages

- Simple
- Can sort in-place
- Low memory usage for small datasets

### Disadvantages

- Very inefficient for large datasets

### Visualization

### 4.3 Bubble Sort

### Idea

1. Iterate over all elements
2. For each element:
    - Swap with next element if out of order
3. Repeat until no swaps needed

### Details

- **Data structure:** Array
- **Space:** `O(1)`
- **Best Case:** Already sorted `O(n)`
- **Worst Case:** Reverse sorted, `O(n^2)`
- **Average:** `O(n^2)`

### Advantages

- Easy to detect if list is sorted

### Disadvantages

- Very inefficient for large datasets
- Much worse than even insertion sort

### Visualization

## 

### 4.4 Merge Sort

### Idea

1. Divide list into smallest unit (1 element)
2. Compare each element with the adjacent list
3. Merge the two adjacent lists
4. Repeat

### Details

- **Data structure:** Array
- **Space:** `O(n) auxiliary`
- **Best Case:** `O(nlog(n))`
- **Worst Case:** Reverse sorted, `O(nlog(n))`
- **Average:** `O(nlog(n))`

### Advantages

- High efficiency on large datasets
- Nearly always O(nlog(n))
- Can be parallelized
- Better space complexity than standard Quicksort

### Disadvantages

- Still requires O(n) extra space
- Slightly worse than Quicksort in some instances

### Visualization

## 

### 4.5 Quicksort

### Idea

1. Choose a **pivot** from the array
2. Partition: Reorder the array so that all elements with values *less* than the pivot come before the pivot, and all values *greater* than the pivot come after
3. Recursively apply the above steps to the sub-arrays

### Details

- **Data structure:** Array
- **Space:** `O(n)`
- **Best Case:** `O(nlog(n))`
- **Worst Case:** All elements equal, `O(n^2)`
- **Average:** `O(nlog(n))`

### Advantages

- Can be modified to use O(log(n)) space
- Very quick and efficient with large datasets
- Can be parallelized
- Divide and conquer algorithm

### Disadvantages

- Not stable (could swap equal elements)
- Worst case is worse than Merge Sort

### Optimizations

- Choice of pivot:
    - Choose median of the first, middle, and last elements as pivot
    - Counters worst-case complexity for already-sorted and reverse-sorted

### Visualization