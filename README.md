# Oops-lab-record
**Program 1: Class and Objects Implementation**

**Aim:**
To illustrate the concept of Class and Objects in C++, and to implement member functions defined inside and outside the class.

**Algorithm:**

1. Start the program.
2. Define a class named Car with data members brand, model, and year.
3. Define a member function displayInfo() inside the class.
4. Declare a member function startEngine() inside the class and define it outside the class using the scope resolution operator.
5. Create two objects of the Car class: myCar and anotherCar.
6. Assign values to their data members.
7. Call the member functions displayInfo() and startEngine() for both objects.
8. Stop the program.



**Source Code:**

```cpp
#include <iostream>
#include <string>
using namespace std;

// Define a class named 'Car'
class Car {
public:
    // Data members
    string brand;
    string model;
    int year;

    // Member function defined inside the class
    void displayInfo() {
        cout << "Brand: " << brand << ", Model: " << model << ", Year: " << year << endl;
    }

    // Member function declared inside, defined outside
    void startEngine();
};

// Member function defined outside the class
void Car::startEngine() {
    cout << "The " << brand << " " << model << " engine is starting..." << endl;
}

int main() {
    // Create objects of the 'Car' class
    Car myCar;
    Car anotherCar;

    // Assign values to data members
    myCar.brand = "Toyota";
    myCar.model = "Camry";
    myCar.year = 2023;

    anotherCar.brand = "Honda";
    anotherCar.model = "Civic";
    anotherCar.year = 2022;

    // Call member functions
    myCar.displayInfo();
    myCar.startEngine();

    anotherCar.displayInfo();
    anotherCar.startEngine();

    return 0;
}
```

---

**Result:**

Output:

Brand: Toyota, Model: Camry, Year: 2023
The Toyota Camry engine is starting...
Brand: Honda, Model: Civic, Year: 2022
The Honda Civic engine is starting...


-------------------------------------

 **Program 2: Constructor and Destructor**

**Aim:**
To illustrate the use of constructors and destructors in C++.



**Algorithm:**

1. Start the program.
2. Define a class named `Student` with data members `name` and `age`.
3. Define a **constructor** to initialize the data members when an object is created.
4. Define a **member function** `display()` to show the details.
5. Define a **destructor** to display a message when an object is destroyed.
6. Create objects of the `Student` class and call the display function.
7. Stop the program.



**Source Code:**

#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    string name;
    int age;

    // Constructor
    Student(string n, int a) {
        name = n;
        age = a;
        cout << "Constructor called for " << name << endl;
    }

    // Member function
    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }

    // Destructor
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



**Result:**

Output:
Constructor called for John
Constructor called for Alice
Name: John, Age: 20
Name: Alice, Age: 19
Destructor called for Alice
Destructor called for John

------------------------------------

 **Program 3: Function Overloading**

**Aim:**
To illustrate the concept of **function overloading** in C++.



**Algorithm:**

1. Start the program.
2. Define a class named `MathOperation`.
3. Overload the function `add()` with different parameter lists.
4. Call the overloaded functions to perform addition of integers, floating numbers, and three integers.
5. Stop the program.



**Source Code:**


#include <iostream>
using namespace std;

class MathOperation {
public:
    int add(int a, int b) {
        return a + b;
    }

    float add(float a, float b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    MathOperation m;

    cout << "Sum of two integers: " << m.add(10, 20) << endl;
    cout << "Sum of two floats: " << m.add(5.5f, 4.5f) << endl;
    cout << "Sum of three integers: " << m.add(1, 2, 3) << endl;

    return 0;
}



**Result:**

Output:
Sum of two integers: 30
Sum of two floats: 10
Sum of three integers:6

-------------------------------------

 **Program 4: Operator Overloading**

**Aim:**
To demonstrate **operator overloading** in C++ for adding two complex numbers using the `+` operator.

---

**Algorithm:**

1. Start the program.
2. Define a class `Complex` with data members `real` and `imag`.
3. Define a constructor to initialize values.
4. Overload the `+` operator to add two complex numbers.
5. Create two objects and add them using the overloaded operator.
6. Display the result.
7. Stop the program.

---

**Source Code:**


#include <iostream>
using namespace std;

class Complex {
    float real, imag;

public:
    Complex(float r = 0, float i = 0) {
        real = r;
        imag = i;
    }

    // Operator overloading
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

    c3 = c1 + c2;  // Using overloaded operator
    cout << "Result of addition: ";
    c3.display();

    return 0;
}


---

**Result:**

Output:
Result of addition: 5 + 7i

--------------‐--------------------
 **Program 5: Constructor Types and Destructor**

**Aim:**
To demonstrate the use of **constructors (default, parameterized, and copy)** and **destructor** in C++.

---

**Algorithm:**

1. Start the program.
2. Define a class `MyClass` with a data member `value`.
3. Define three types of constructors:

   * Default constructor (no parameters).
   * Parameterized constructor (takes one argument).
   * Copy constructor (copies values from another object).
4. Define a destructor to display a message when an object is destroyed.
5. Create objects using all three constructors.
6. Observe the constructor and destructor calls.
7. Stop the program.

---

**Source Code:**
#include <iostream>
using namespace std;

class MyClass {
public:
    int value;

    // Default Constructor
    MyClass() {
        value = 0;
        cout << "Default Constructor Called. Value: " << value << endl;
    }

    // Parameterized Constructor
    MyClass(int val) {
        value = val;
        cout << "Parameterized Constructor Called. Value: " << value << endl;
    }

    // Copy Constructor
    MyClass(const MyClass& other) {
        value = other.value;
        cout << "Copy Constructor Called. Value: " << value << endl;
    }

    // Destructor
    ~MyClass() {
        cout << "Destructor Called for object with value: " << value << endl;
    }
};

int main() {
    // Calling Default Constructor
    MyClass obj1;

    // Calling Parameterized Constructor
    MyClass obj2(10);

    // Calling Copy Constructor
    MyClass obj3 = obj2; // or MyClass obj3(obj2);

    return 0;
}


------------------------------------

**Result:**

Output:
Default Constructor Called. Value: 0
Parameterized Constructor Called. Value: 10
Copy Constructor Called. Value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 10
Destructor Called for object with value: 0
--------------‐----------------------

 **Program 6: Static Data Member and Static Member Function**

**Aim:**
To illustrate the use of **static data members** and **static member functions** in C++.

---

**Algorithm:**

1. Start the program.
2. Define a class `Car` with a static data member `carCount`.
3. Increment the count in the constructor whenever a new object is created.
4. Define a function to display car information.
5. Initialize the static data member outside the class definition.
6. Create multiple objects and display the total count using the class name.
7. Stop the program.

---

**Source Code:**

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    static int carCount; // Static data member

    // Constructor
    Car() {
        carCount++; // Increment count when object is created
    }

    void displayCarInfo() {
        cout << "This is a car object." << endl;
    }

    // Static member function
    static void displayCount() {
        cout << "Total cars created: " << carCount << endl;
    }
};

// Initialize static data member
int Car::carCount = 0;

int main() {
    Car car1, car2, car3;

    Car::displayCount(); // Access static function using class name

    return 0;
}
```

---

**Result:**

Output:
Total cars created: 3

◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇

**Program 7: Array of Objects**

**Aim:**
To illustrate the use of **array of objects** in C++.

---

**Algorithm:**

1. Start the program.
2. Define a class `Student` with data members `name` and `rollNumber`.
3. Define a function `displayInfo()` to print student details.
4. Declare an array of `Student` objects.
5. Initialize the objects in the array with names and roll numbers.
6. Use a loop to display details of all students.
7. Stop the program.

---

**Source Code:**


#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    string name;
    int rollNumber;

    void displayInfo() {
        cout << "Name: " << name << ", Roll No: " << rollNumber << endl;
    }
};

int main() {
    Student students[3]; // Array of 3 Student objects

    // Initialize array elements
    students[0].name = "Alice";
    students[0].rollNumber = 101;

    students[1].name = "Bob";
    students[1].rollNumber = 102;

    students[2].name = "Charlie";
    students[2].rollNumber = 103;

    // Display information
    for (int i = 0; i < 3; ++i) {
        students[i].displayInfo();
    }

    return 0;
}
```

---

**Result:**

Output:
Name: Alice, Roll No: 101
Name: Bob, Roll No: 102
Name: Charlie, Roll No: 103

◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇◇

**Program 8: Illustrate Memory Management Operators in C++

 **Aim:**

To illustrate the use of **memory management operators (`new` and `delete`)** for dynamic allocation and deallocation of memory in C++.



 **Algorithm:**

1. Start the program.
2. Use the `new` operator to dynamically allocate memory for variables and arrays on the heap.
3. Assign values to the dynamically allocated memory.
4. Display the stored values using pointers.
5. Use the `delete` operator to deallocate memory for a single variable.
6. Use `delete[]` to deallocate memory for arrays.
7. Set pointers to `nullptr` after deletion to avoid dangling pointers.
8. Stop the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    // Dynamic allocation for a single integer
    int* singleInt = new int;
    *singleInt = 25;
    cout << "Value of singleInt: " << *singleInt << endl;

    // Dynamic allocation for an array of integers
    int size = 3;
    int* dynamicArray = new int[size];

    for (int i = 0; i < size; ++i) {
        dynamicArray[i] = (i + 1) * 10;
    }

    cout << "Elements of dynamicArray: ";
    for (int i = 0; i < size; ++i) {
        cout << dynamicArray[i] << " ";
    }
    cout << endl;

    // Deallocate memory
    delete singleInt;
    singleInt = nullptr; // Good practice to set pointer to nullptr after deletion

    delete[] dynamicArray;
    dynamicArray = nullptr; // Good practice to set pointer to nullptr after deletion

    return 0;
}


Result:
Value of singleInt: 25
Elements of dynamicArray: 10 20 30
♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤♤
## 🧩 **Program 9: Friend Class and Friend Function in C++**

---

### **Aim:**

### **Algorithm:**

1. Start the program.
2. Create a class `Geeks` with private and protected data members.
3. Declare another class `GFG` as a **friend** inside `Geeks`.
4. Define `GFG` to access and display the private and protected members of `Geeks`.
5. In `main()`, create objects of both classes.
6. Call the display function to print the values.
7. Stop the program.

---

### **Source Code:**

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

    // friend class declaration
    friend class GFG;
};

// Friend class GFG can access private and protected members of Geeks
class GFG {
public:
    void display(Geeks& t) {
        cout << "The value of Private Variable = " << t.private_variable << endl;
        cout << "The value of Protected Variable = " << t.protected_variable << endl;
    }
};

int main() {
    Geeks g;
    GFG fri;
    fri.display(g);
    return 0;
}


-

**Result:**


The value of Private Variable = 10
The value of Protected Variable = 99
□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□
**Program 10: Inheritance – Area of Triangle, Circle, and Rectangle (C++)**

---

**Aim:**

To demonstrate the concept of **inheritance** in C++ by calculating the area of a **Triangle**, **Circle**, and **Rectangle** using base and derived classes.

---

**Algorithm:**

1. Start the program.
2. Define a base class `Shape` with a **virtual function `area()`**.
3. Derive three classes from `Shape`:

   * `Triangle` – for calculating area = ½ × base × height.
   * `Circle` – for calculating area = π × r².
   * `Rectangle` – for calculating area = length × breadth.
4. Use a menu-driven approach to choose the shape.
5. Create an object of the respective derived class and calculate the area.
6. Display the result.
7. Stop the program.

---

**Source Code:**


#include <iostream>
#include <cmath>
using namespace std;

// Base class
class Shape {
public:
    virtual void area() = 0; // Pure virtual function
};

// Derived class for Triangle
class Triangle : public Shape {
    float base, height;
public:
    void getData() {
        cout << "Enter base of the triangle: ";
        cin >> base;
        cout << "Enter height of the triangle: ";
        cin >> height;
    }
    void area() {
        cout << "Area of Triangle = " << 0.5 * base * height << endl;
    }
};

// Derived class for Circle
class Circle : public Shape {
    float radius;
public:
    void getData() {
        cout << "Enter radius of the circle: ";
        cin >> radius;
    }
    void area() {
        cout << "Area of Circle = " << M_PI * radius * radius << endl;
    }
};

// Derived class for Rectangle
class Rectangle : public Shape {
    float length, breadth;
public:
    void getData() {
        cout << "Enter length of the rectangle: ";
        cin >> length;
        cout << "Enter breadth of the rectangle: ";
        cin >> breadth;
    }
    void area() {
        cout << "Area of Rectangle = " << length * breadth << endl;
    }
};

// Main function
int main() {
    Shape* shapePtr; // Base class pointer
    Triangle t;
    Circle c;
    Rectangle r;
    int choice;

    cout << "1. Triangle\n2. Circle\n3. Rectangle\n";
    cout << "Enter your choice (1-3): ";
    cin >> choice;

    switch (choice) {
        case 1:
            shapePtr = &t;
            t.getData();
            shapePtr->area();
            break;
        case 2:
            shapePtr = &c;
            c.getData();
            shapePtr->area();
            break;
        case 3:
            shapePtr = &r;
            r.getData();
            shapePtr->area();
            break;
        default:
            cout << "Invalid choice!" << endl;
    }

    return 0;
}


---

Result (Sample Output):


1. Triangle
2. Circle
3. Rectangle
Enter your choice (1-3): 1
Enter base of the triangle: 10
Enter height of the triangle: 5
Area of Triangle = 25
