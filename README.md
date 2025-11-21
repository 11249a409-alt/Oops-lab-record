---

# 🧩 **OOPS LAB RECORD**

---

## **Program 1: Class and Objects Implementation**

**Aim:**
To illustrate the concept of Class and Objects in C++, and to implement member functions defined inside and outside the class.

**Algorithm:**

1. Start the program.
2. Define a class named `Car` with data members brand, model, and year.
3. Define a member function `displayInfo()` inside the class.
4. Declare a member function `startEngine()` inside the class and define it outside the class using the scope resolution operator.
5. Create two objects of the `Car` class: `myCar` and `anotherCar`.
6. Assign values to their data members.
7. Call the member functions `displayInfo()` and `startEngine()` for both objects.
8. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Car {
public:
    string brand;
    string model;
    int year;

    void displayInfo() {
        cout << "Brand: " << brand << ", Model: " << model << ", Year: " << year << endl;
    }

    void startEngine();
};

void Car::startEngine() {
    cout << "The " << brand << " " << model << " engine is starting..." << endl;
}

int main() {
    Car myCar;
    Car anotherCar;

    myCar.brand = "Toyota";
    myCar.model = "Camry";
    myCar.year = 2023;

    anotherCar.brand = "Honda";
    anotherCar.model = "Civic";
    anotherCar.year = 2022;

    myCar.displayInfo();
    myCar.startEngine();

    anotherCar.displayInfo();
    anotherCar.startEngine();

    return 0;
}
```

**Result:**

```
Brand: Toyota, Model: Camry, Year: 2023
The Toyota Camry engine is starting...
Brand: Honda, Model: Civic, Year: 2022
The Honda Civic engine is starting...
```

---

## **Program 2: Constructor and Destructor**

**Aim:**
To illustrate the use of constructors and destructors in C++.

**Algorithm:**

1. Start the program.
2. Define a class `Student` with data members `name` and `age`.
3. Define a constructor to initialize the data members.
4. Define a member function `display()` to show the details.
5. Define a destructor to display a message when an object is destroyed.
6. Create objects and call the display function.
7. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    string name;
    int age;

    Student(string n, int a) {
        name = n;
        age = a;
        cout << "Constructor called for " << name << endl;
    }

    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }

    ~Student() {
        cout << "Destructor called for " << name << endl;
    }
};

int main() {
    Student s1("John", 20);
    Student s2("Alice", 19);

    s1.display();
    s2.display();

    return 0;
}
```

**Result:**

```
Constructor called for John
Constructor called for Alice
Name: John, Age: 20
Name: Alice, Age: 19
Destructor called for Alice
Destructor called for John
```

---

## **Program 3: Function Overloading**

**Aim:**
To illustrate the concept of function overloading in C++.

**Algorithm:**

1. Start the program.
2. Define a class `MathOperation`.
3. Overload the function `add()` with different parameter lists.
4. Call the overloaded functions.
5. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class MathOperation {
public:
    int add(int a, int b) { return a + b; }
    float add(float a, float b) { return a + b; }
    int add(int a, int b, int c) { return a + b + c; }
};

int main() {
    MathOperation m;
    cout << "Sum of two integers: " << m.add(10, 20) << endl;
    cout << "Sum of two floats: " << m.add(5.5f, 4.5f) << endl;
    cout << "Sum of three integers: " << m.add(1, 2, 3) << endl;
    return 0;
}
```

**Result:**

```
Sum of two integers: 30
Sum of two floats: 10
Sum of three integers: 6
```

---

## **Program 4: Operator Overloading**

**Aim:**
To demonstrate operator overloading in C++ for adding two complex numbers using the `+` operator.

**Algorithm:**

1. Start the program.
2. Define a class `Complex`.
3. Overload the `+` operator.
4. Create objects and add them.
5. Display the result.
6. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class Complex {
    float real, imag;

public:
    Complex(float r = 0, float i = 0) {
        real = r;
        imag = i;
    }

    Complex operator + (Complex c) {
        Complex temp;
        temp.real = real + c.real;
        temp.imag = imag + c.imag;
        return temp;
    }

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1(3.5, 2.5), c2(1.5, 4.5), c3;
    c3 = c1 + c2;
    cout << "Result of addition: ";
    c3.display();
    return 0;
}
```

**Result:**

```
Result of addition: 5 + 7i
```

---

## **Program 5: Constructor Types and Destructor**

**Aim:**
To demonstrate default, parameterized, and copy constructors, and destructor in C++.

**Algorithm:**

1. Start the program.
2. Define a class `MyClass` with data member `value`.
3. Define constructors (default, parameterized, copy).
4. Define a destructor.
5. Create objects using all constructors.
6. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    int value;

    MyClass() {
        value = 0;
        cout << "Default Constructor Called. Value: " << value << endl;
    }

    MyClass(int val) {
        value = val;
        cout << "Parameterized Constructor Called. Value: " << value << endl;
    }

    MyClass(const MyClass& other) {
        value = other.value;
        cout << "Copy Constructor Called. Value: " << value << endl;
    }

    ~MyClass() {
        cout << "Destructor Called for object with value: " << value << endl;
    }
};

int main() {
    MyClass obj1;
    MyClass obj2(10);
    MyClass obj3 = obj2;
    return 0;
}
```

**Result:**

```
Default Constructor Called. Value: 0
Parameterized Constructor Called. Value: 10
Copy Constructor Called. Value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 0
```

---
---

## **Program 6: Inheritance in C++**

**Aim:**
To demonstrate single inheritance in C++.

**Algorithm:**

1. Start the program.
2. Create a base class `Person` with data members `name` and `age`.
3. Create a derived class `Student` that inherits publicly from `Person`.
4. Add data member `studentID` in the derived class.
5. Define a member function to display all details.
6. Create an object of the derived class and display data.
7. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Person {
public:
    string name;
    int age;

    void getDetails() {
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter Age: ";
        cin >> age;
    }
};

class Student : public Person {
public:
    int studentID;

    void getStudentDetails() {
        cout << "Enter Student ID: ";
        cin >> studentID;
    }

    void display() {
        cout << "\nStudent Details:\n";
        cout << "Name: " << name << "\nAge: " << age << "\nStudent ID: " << studentID << endl;
    }
};

int main() {
    Student s;
    s.getDetails();
    s.getStudentDetails();
    s.display();
    return 0;
}
```

**Sample Output:**

```
Enter Name: John
Enter Age: 20
Enter Student ID: 101

Student Details:
Name: John
Age: 20
Student ID: 101
```

**Result:**
The program successfully demonstrates single inheritance where the derived class inherits data and behavior from the base class.

---

## **Program 7: Multilevel Inheritance**

**Aim:**
To illustrate multilevel inheritance in C++.

**Algorithm:**

1. Start the program.
2. Define a base class `Person`.
3. Define a derived class `Student` from `Person`.
4. Define another derived class `Marks` from `Student`.
5. Accept and display data from all levels of inheritance.
6. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Person {
public:
    string name;
    int age;
    void getPersonDetails() {
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter Age: ";
        cin >> age;
    }
};

class Student : public Person {
public:
    int rollNo;
    void getStudentDetails() {
        cout << "Enter Roll Number: ";
        cin >> rollNo;
    }
};

class Marks : public Student {
public:
    float marks;
    void getMarks() {
        cout << "Enter Marks: ";
        cin >> marks;
    }
    void display() {
        cout << "\nStudent Record:\n";
        cout << "Name: " << name << "\nAge: " << age << "\nRoll No: " << rollNo << "\nMarks: " << marks << endl;
    }
};

int main() {
    Marks m;
    m.getPersonDetails();
    m.getStudentDetails();
    m.getMarks();
    m.display();
    return 0;
}
```

**Sample Output:**

```
Enter Name: Alice
Enter Age: 19
Enter Roll Number: 5
Enter Marks: 88.5

Student Record:
Name: Alice
Age: 19
Roll No: 5
Marks: 88.5
```

**Result:**
Multilevel inheritance was successfully implemented where data members are inherited across multiple levels.

---

## **Program 8: Virtual Base Class**

**Aim:**
To demonstrate the concept of virtual base class in C++.

**Algorithm:**

1. Start the program.
2. Create a base class `Person`.
3. Create two derived classes `Student` and `Employee` inheriting `Person` virtually.
4. Create a new class `Manager` derived from both `Student` and `Employee`.
5. Show that only one instance of base class `Person` is inherited.
6. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Person {
public:
    string name;
    void getName() {
        cout << "Enter Name: ";
        cin >> name;
    }
};

class Student : virtual public Person {
public:
    int rollNo;
    void getRoll() {
        cout << "Enter Roll Number: ";
        cin >> rollNo;
    }
};

class Employee : virtual public Person {
public:
    int empID;
    void getEmpID() {
        cout << "Enter Employee ID: ";
        cin >> empID;
    }
};

class Manager : public Student, public Employee {
public:
    void display() {
        cout << "\nManager Details:\n";
        cout << "Name: " << name << "\nRoll No: " << rollNo << "\nEmployee ID: " << empID << endl;
    }
};

int main() {
    Manager m;
    m.getName();
    m.getRoll();
    m.getEmpID();
    m.display();
    return 0;
}
```

**Sample Output:**

```
Enter Name: Riya
Enter Roll Number: 12
Enter Employee ID: 501

Manager Details:
Name: Riya
Roll No: 12
Employee ID: 501
```

**Result:**
The program successfully shows that virtual inheritance avoids multiple copies of the base class when using multiple inheritance.

---

## **Program 9: Friend Functions and Friend Class**

### **9(a) Friend Class Example**

**Aim:**
To demonstrate how a friend class can access private and protected members of another class.

**Algorithm:**

1. Start the program.
2. Create a class `Geeks` with private and protected members.
3. Declare another class `GFG` as a friend.
4. Use the friend class to access and display private and protected members.
5. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class Geeks {
private:
    int private_variable;

protected:
    int protected_variable;

public:
    Geeks() {
        private_variable = 10;
        protected_variable = 99;
    }
    friend class GFG;
};

class GFG {
public:
    void display(Geeks &t) {
        cout << "The value of Private Variable = " << t.private_variable << endl;
        cout << "The value of Protected Variable = " << t.protected_variable << endl;
    }
};

int main() {
    Geeks g;
    GFG f;
    f.display(g);
    return 0;
}
```

**Result:**

```
The value of Private Variable = 10
The value of Protected Variable = 99
```

---

### **9(b) Friend Function Example**

**Aim:**
To demonstrate how a global friend function can access private and protected members of a class.

**Algorithm:**

1. Start the program.
2. Create a class `base` with private and protected members.
3. Declare a global friend function `friendFunction`.
4. Use the friend function to access and display the private and protected members.
5. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class base {
private:
    int private_variable;
protected:
    int protected_variable;

public:
    base() {
        private_variable = 10;
        protected_variable = 99;
    }
    friend void friendFunction(base &obj);
};

void friendFunction(base &obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable << endl;
}

int main() {
    base b;
    friendFunction(b);
    return 0;
}
```

**Result:**

```
Private Variable: 10
Protected Variable: 99
```

---

### **9(c) Member Function of Another Class as Friend**

**Aim:**
To demonstrate how a member function of one class can be declared as a friend in another class.

**Algorithm:**

1. Start the program.
2. Use forward declaration for the `base` class.
3. Define class `GFG` with a member function `GFG_Function()`.
4. Declare this function as a friend inside the `base` class.
5. Define and use the function to access private and protected members.
6. Stop the program.

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class base; // forward declaration

class GFG {
public:
    void GFG_Function(base &obj);
};

class base {
private:
    int private_variable;
protected:
    int protected_variable;

public:
    base() {
        private_variable = 10;
        protected_variable = 99;
    }
    friend void GFG::GFG_Function(base &);
};

void GFG::GFG_Function(base &obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable << endl;
}

int main() {
    base b;
    GFG g;
    g.GFG_Function(b);
    return 0;
}
```

**Result:**

```
Private Variable: 10
Protected Variable: 99
```

---

## **Program 10: File Handling in C++**

**Aim:**
To demonstrate file reading and writing operations using file streams in C++.

**Algorithm:**

1. Start the program.
2. Include the `<fstream>` header.
3. Declare `ofstream` object to write data to a file.
4. Declare `ifstream` object to read data from the file.
5. Write text into the file using `ofstream`.
6. Close the file.
7. Reopen it in read mode and display its contents.
8. Stop the program.

**Source Code:**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream outFile("sample.txt");
    outFile << "Hello, this is a sample file.\n";
    outFile << "File handling in C++ is easy!";
    outFile.close();

    ifstream inFile("sample.txt");
    string line;
    cout << "Contents of file:\n";
    while (getline(inFile, line)) {
        cout << line << endl;
    }
    inFile.close();
    return 0;
}
```

**Sample Output:**

```
Contents of file:
Hello, this is a sample file.
File handling in C++ is easy!
```

**Result:**
The program successfully demonstrates file handling operations in C++ using file streams.

---

# ***11. To implement the use of binary operator overloading***

**Aim:**
To overload a binary operator (+) to add two Point objects.

**Algorithm:**

1. Start the program.
2. Include `<iostream>`.
3. Define a class `Point` with data members `x` and `y` and a constructor.
4. Overload the `operator+` to add coordinates of two points and return a new object.
5. In `main()`, create objects and add them using `+`.
6. Display the result.
7. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Point {
public:
    int x, y;
    Point(int a=0, int b=0): x(a), y(b) {}
    
    Point operator+(const Point &p) const {
        return Point(x + p.x, y + p.y);
    }
    
    void display() const { 
        cout << x << ", " << y << endl; 
    }
};

int main() {
    Point p1(2,3), p2(4,5);
    Point p3 = p1 + p2;
    p3.display();
    return 0;
}
```

**Output:**
6, 8

**Result:**
Binary + operator overloaded successfully to add two Point objects.

---

# ***12. Assignment and comparison of two strings (binary operator overloading)***

**Aim:**
To demonstrate string assignment and comparison using standard string operators.

**Algorithm:**

1. Start the program.
2. Include `<iostream>` and `<string>`.
3. Create string variables and perform assignment.
4. Compare strings using the equality operator `==`.
5. Display the results.
6. End the program.

**Program:**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string s1 = "Hello";
    string s2 = "World";
    string s3 = s1;   // assignment
    
    cout << (s1 == s3 ? "s1 equals s3" : "s1 not equal s3") << endl;
    cout << (s1 == s2 ? "s1 equals s2" : "s1 not equal s2") << endl;
    
    return 0;
}
```

**Output:**
s1 equals s3
s1 not equal s2

**Result:**
Assignment and comparison of strings using built-in operators executed successfully.

---

# ***13. Single inheritance (private and public)***

**Aim:**
To demonstrate single inheritance using public and private modes.

**Algorithm:**

1. Start the program.
2. Define base class with public, protected, and private members.
3. Create derived classes using public and private inheritance.
4. Access base members through derived methods.
5. Call derived class functions in `main()`.
6. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    int a = 10;
protected:
    int b = 20;
private:
    int c = 30;
};

class PublicDerived : public Base {
public:
    void show() {
        cout << "a = " << a << ", b = " << b << endl;
    }
};

class PrivateDerived : private Base {
public:
    void showp() {
        cout << "a = " << a << " (a is private here)" << endl;
    }
};

int main() {
    PublicDerived pd; 
    pd.show();
    
    PrivateDerived pr;
    pr.showp();
    
    return 0;
}
```

**Output:**
a = 10, b = 20
a = 10 (a is private here)

**Result:**
Single inheritance using both public and private modes demonstrated successfully.

---

# ***14. Multiple inheritance***

**Aim:**
To demonstrate multiple inheritance using two base classes.

**Algorithm:**

1. Start the program.
2. Create two base classes with individual methods.
3. Derive a new class from both base classes.
4. Access both base class methods using the derived object.
5. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class A {
public:
    void showA(){ cout << "A\n"; }
};

class B {
public:
    void showB(){ cout << "B\n"; }
};

class Derived : public A, public B {
public:
    void showBoth(){ showA(); showB(); }
};

int main() {
    Derived d;
    d.showBoth();
    return 0;
}
```

**Output:**
A
B

**Result:**
Multiple inheritance successfully implemented using two parent classes.

---

# ***15. Multilevel inheritance***

**Aim:**
To demonstrate multilevel inheritance using three classes.

**Algorithm:**

1. Start the program.
2. Create class A, then derive B from A, and C from B.
3. In class C, call functions of A and B.
4. Display results.
5. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class A { 
public: 
    void showA(){ cout << "A\n"; } 
};

class B : public A { 
public: 
    void showB(){ cout << "B\n"; } 
};

class C : public B { 
public: 
    void showC(){ showA(); showB(); cout << "C\n"; } 
};

int main() {
    C obj;
    obj.showC();
    return 0;
}
```

**Output:**
A
B
C

**Result:**
Multilevel inheritance implemented successfully.

---

# ***16. Hierarchical inheritance***

**Aim:**
To demonstrate hierarchical inheritance with multiple derived classes sharing one base class.

**Algorithm:**

1. Start the program.
2. Create base class `Animal`.
3. Derive `Dog` and `Cat` from Animal.
4. Access base class methods through derived class objects.
5. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Animal { 
public: 
    void eat(){ cout << "Eating\n"; } 
};

class Dog : public Animal { 
public: 
    void bark(){ cout << "Bark\n"; } 
};

class Cat : public Animal { 
public: 
    void meow(){ cout << "Meow\n"; } 
};

int main() {
    Dog d; 
    Cat c;
    
    d.eat(); 
    d.bark();
    
    c.eat(); 
    c.meow();
    
    return 0;
}
```

**Output:**
Eating
Bark
Eating
Meow

**Result:**
Hierarchical inheritance executed successfully.

---

# ***17. Virtual base class (to resolve diamond problem)***

**Aim:**
To demonstrate virtual base class to avoid duplication in diamond inheritance.

**Algorithm:**

1. Start the program.
2. Create base class and two intermediate classes using virtual inheritance.
3. Derive final class from intermediate classes.
4. Access base class member without ambiguity.
5. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Base { 
public: 
    int x; 
    Base(){ x = 10; } 
};

class D1 : virtual public Base { };
class D2 : virtual public Base { };

class Final : public D1, public D2 {
public:
    void show(){ cout << "x = " << x << endl; }
};

int main() {
    Final f;
    f.show();
    return 0;
}
```

**Output:**
x = 10

**Result:**
Virtual inheritance successfully removed ambiguity in diamond structure.

---

# ***18. To implement abstraction using pure virtual functions***

**Aim:**
To demonstrate abstraction using abstract classes and pure virtual functions.

**Algorithm:**

1. Start the program.
2. Create abstract class `Shape` with pure virtual function.
3. Implement derived classes `Rectangle` and `Circle`.
4. Call overridden methods using base pointer.
5. Display area.
6. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual double area() const = 0;
    virtual ~Shape() {}
};

class Rectangle : public Shape {
    double w, h;
public:
    Rectangle(double _w, double _h): w(_w), h(_h) {}
    double area() const override { return w * h; }
};

class Circle : public Shape {
    double r;
public:
    Circle(double _r): r(_r) {}
    double area() const override { return 3.14159 * r * r; }
};

int main() {
    Shape* s1 = new Rectangle(4,5);
    Shape* s2 = new Circle(3);
    
    cout << "Rect area: " << s1->area() << endl;
    cout << "Circle area: " << s2->area() << endl;
    
    delete s1; 
    delete s2;
    return 0;
}
```

**Output:**
Rect area: 20
Circle area: 28.2743

**Result:**
Abstraction successfully implemented using pure virtual functions.

---

# ***19. To implement runtime polymorphism using virtual functions***

**Aim:**
To demonstrate runtime polymorphism using virtual functions.

**Algorithm:**

1. Start the program.
2. Create base class with virtual method.
3. Override method in derived class.
4. Use base pointer to access derived object.
5. Observe runtime binding.
6. End the program.

**Program:**

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show(){ cout << "Base\n"; }
    virtual ~Base() {}
};

class Derived : public Base {
public:
    void show() override { cout << "Derived\n"; }
};

int main() {
    Base* p = new Derived();
    p->show();
    delete p;
    return 0;
}
```

**Output:**
Derived

**Result:**
Runtime polymorphism executed successfully through base pointer.

---

# ***20. To demonstrate templates (class/function template)***

**Aim:**
To implement and demonstrate templates for generic programming.

**Algorithm:**

1. Start the program.
2. Create a function template `maxValue`.
3. Create class template `Pair`.
4. Instantiate templates with different data types.
5. Display results.
6. End program.

**Program:**

```cpp
#include <iostream>
using namespace std;

template<typename T>
T maxValue(T a, T b) { 
    return (a > b) ? a : b; 
}

template<typename T>
class Pair {
public:
    T first, second;
    Pair(T a, T b): first(a), second(b) {}
    
    void show(){ 
        cout << first << ", " << second << endl; 
    }
};

int main() {
    cout << maxValue<int>(3,7) << endl;
    cout << maxValue<double>(3.5, 2.1) << endl;
    
    Pair<string> p("Hi", "There");
    p.show();
    
    return 0;
}
```

**Output:**
7
3.5
Hi, There

**Result:**
Templates successfully implemented for function and class.

---

# ***21. To demonstrate exception handling***

**Aim:**
To demonstrate exception handling using try, catch, and throw.

**Algorithm:**

1. Start the program.
2. Create a divide function that throws exception if denominator is zero.
3. Wrap operations inside try block.
4. Catch exception and display error.
5. End program.

**Program:**

```cpp
#include <iostream>
using namespace std;

double divide(double a, double b) {
    if (b == 0) 
        throw "Division by zero error";
    return a / b;
}

int main() {
    try {
        cout << divide(10, 2) << endl;
        cout << divide(5, 0) << endl;
    }
    catch (const char* msg) {
        cout << "Caught exception: " << msg << endl;
    }
    
    return 0;
}
```

**Output:**
5
Caught exception: Division by zero error

**Result:**
Exception handling successfully implemented.

---

# ***22. File handling using streams***

**Aim:**
To demonstrate file operations using file streams.

**Algorithm:**

1. Start program.
2. Use ofstream to write into a file.
3. Close file.
4. Use ifstream to read the file.
5. Display contents.
6. End program.

**Program:**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream fout("data.txt");
    fout << "Line1\nLine2\n";
    fout.close();
    
    ifstream fin("data.txt");
    string line;
    while (getline(fin, line))
        cout << line << endl;
    fin.close();
    
    return 0;
}
```

**Output:**
Line1
Line2

**Result:**
File read/write operations performed successfully.

---

# ***23. To demonstrate STL – vector and iterator***

**Aim:**
To demonstrate vector operations and iterators in STL.

**Algorithm:**

1. Start program.
2. Create vector and insert elements.
3. Use iterator to traverse and print elements.
4. Display size.
5. End program.

**Program:**

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> v;
    
    v.push_back(10);
    v.push_back(20);
    v.push_back(30);
    
    for (vector<int>::iterator it = v.begin(); it != v.end(); ++it)
        cout << *it << endl;
    
    cout << "Size: " << v.size() << endl;
    
    return 0;
}
```

**Output:**
10
20
30
Size: 3

**Result:**
STL vector and iterator operations demonstrated successfully.

---

# ***24. To demonstrate STL – stack and queue***

**Aim:**
To demonstrate stack (LIFO) and queue (FIFO) operations.

**Algorithm:**

1. Start program.
2. Push elements in stack and queue.
3. Pop/access elements.
4. Display results.
5. End program.

**Program:**

```cpp
#include <iostream>
#include <stack>
#include <queue>
using namespace std;

int main() {
    stack<int> s;
    s.push(1); 
    s.push(2); 
    s.push(3);
    
    cout << "Stack pop: " << s.top() << endl;
    s.pop();
    
    queue<int> q;
    q.push(1); 
    q.push(2); 
    q.push(3);
    
    cout << "Queue front: " << q.front() << endl;
    q.pop();
    
    return 0;
}
```

**Output:**
Stack pop: 3
Queue front: 1

**Result:**
Stack and queue operations performed successfully.

---

# ***25. To demonstrate sorting and searching using STL algorithms***

**Aim:**
To demonstrate sorting and binary search using STL algorithms.

**Algorithm:**

1. Start program.
2. Create vector with unsorted elements.
3. Sort using `sort()`.
4. Search element using `binary_search()`.
5. Display result.
6. End program.

**Program:**

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    vector<int> v = {5,2,9,1,7};
    
    sort(v.begin(), v.end());
    
    for(int x : v) 
        cout << x << " ";
    cout << endl;
    
    cout << (binary_search(v.begin(), v.end(), 7) ? "Found" : "Not Found") << endl;
    
    return 0;
}
```

**Output:**
1 2 5 7 9
Found

**Result:**
Sorting and searching using STL executed successfully.

---

# ***26. Mini Project – Simple student management system***

**Aim:**
To implement a simple student record system using classes, vectors, and file handling.

**Algorithm:**

1. Start program.
2. Create `Student` class with data members and display function.
3. Store objects inside vector.
4. Display all student records.
5. Save records to text file using ofstream.
6. End program.

**Program:**

```cpp
#include <iostream>
#include <vector>
#include <fstream>
using namespace std;

class Student {
public:
    string name;
    int roll;
    
    Student(string n="", int r=0): name(n), roll(r) {}
    
    void display(){
        cout << roll << " : " << name << endl;
    }
};

int main() {
    vector<Student> list;
    
    list.push_back(Student("Alice",101));
    list.push_back(Student("Bob",102));
    
    cout << "Students:\n";
    for(auto &s : list)
        s.display();
    
    ofstream fout("students.txt");
    for(auto &s : list)
        fout << s.roll << " " << s.name << "\n";
    fout.close();
    
    cout << "Saved to students.txt\n";
    
    return 0;
}
```

**Output:**
Students:
101 : Alice
102 : Bob
Saved to students.txt

**Result:**
Student record stored and saved successfully using vectors and file handling.

---
