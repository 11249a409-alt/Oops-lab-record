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

