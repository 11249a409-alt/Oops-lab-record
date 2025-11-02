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

*

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
□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□□


## **Program 8: Illustrate Memory Management Operators (`new` and delete )
**Aim:**

To illustrate the use of **memory management operators** — `new` and `delete` — in C++ for **dynamic allocation and deallocation** of memory.

---

## **8(a) Allocating and Deallocating a Single Variable**

---

### **Algorithm:**

1. Start the program.
2. Use the `new` operator to dynamically allocate memory for a single integer.
3. Assign a value to the allocated memory.
4. Display the stored value.
5. Use the `delete` operator to deallocate the memory.
6. Set the pointer to `nullptr` to prevent dangling pointer issues.
7. Stop the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    // Dynamically allocate memory for an integer and initialize it to 10
    int* ptr_int = new int(10);

    // Print the value stored at the allocated address
    cout << "Value of dynamically allocated integer: " << *ptr_int << endl;

    // Deallocate the memory to prevent a memory leak
    delete ptr_int;
    ptr_int = nullptr; // Set the pointer to nullptr after deletion

    return 0;
}
```

---

### **Result:**

```
Value of dynamically allocated integer: 10
```

---

### **Conclusion:**

The program successfully demonstrates how to **dynamically allocate and deallocate** memory for a single variable using `new` and `delete`.

---

 **8(b) Allocating and Deallocating a Dynamic Array**

---

### **Algorithm:**

1. Start the program.
2. Ask the user for the size of the array.
3. Dynamically allocate memory for an integer array using `new[]`.
4. Input array elements and display them.
5. Deallocate memory using `delete[]`.
6. Set the pointer to `nullptr`.
7. Stop the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int size;
    cout << "Enter the number of elements for the dynamic array: ";
    cin >> size;

    // Dynamically allocate memory for an array of integers
    int* dynamic_array = new int[size];

    // Read values into the array
    cout << "Enter " << size << " integer values:" << endl;
    for (int i = 0; i < size; i++) {
        cin >> dynamic_array[i];
    }

    // Print the array elements
    cout << "The elements of the dynamic array are: ";
    for (int i = 0; i < size; i++) {
        cout << dynamic_array[i] << " ";
    }
    cout << endl;

    // Deallocate the entire array
    delete[] dynamic_array;
    dynamic_array = nullptr;

    return 0;
}

---

### **Result (Sample Output):**

Enter the number of elements for the dynamic array: 5
Enter 5 integer values:
1 2 3 4 5
The elements of the dynamic array are: 1 2 3 4 5


-------—------------------------------

## **8(c) Dynamic Object Creation with Constructors and Destructors**


### **Algorithm:**

1. Define a class `Box` with a constructor and destructor.
2. Dynamically allocate a single object using `new`.
3. Use `delete` to deallocate the object and observe destructor call.
4. Dynamically create an array of objects using `new[]`.
5. Use `delete[]` to deallocate the array.
6. Observe automatic constructor and destructor calls.
7. Stop the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    // Constructor
    Box(int length) {
        this->length = length;
        cout << "Constructor for a box of length " << length << " is called." << endl;
    }

    // Destructor
    ~Box() {
        cout << "Destructor for a box of length " << length << " is called." << endl;
    }

private:
    int length;
};

int main() {
    // Create a single Box object dynamically
    Box* myBox = new Box(5);

    // Deallocate the object, which calls the destructor
    delete myBox;
    myBox = nullptr;

    // Create a dynamic array of Box objects
    Box* boxArray = new Box[3]{Box(1), Box(2), Box(3)};

    // Deallocate the array, calling the destructor for each element
    delete[] boxArray;
    boxArray = nullptr;

    return 0;
}
```



**Result (Sample Output):**

Constructor for a box of length 5 is called.
Destructor for a box of length 5 is called.
Constructor for a box of length 1 is called.
Constructor for a box of length 2 is called.
Constructor for a box of length 3 is called.
Destructor for a box of length 3 is called.
Destructor for a box of length 2 is called.
Destructor for a box of length 1 is called.


**8(d) Illustrative Program – Combined Example**



### **Algorithm:**

1. Dynamically allocate memory for a single integer and assign a value.
2. Dynamically allocate memory for an integer array and store values.
3. Display both single integer and array values.
4. Deallocate all memory and set pointers to `nullptr`.
5. Stop the program.

---

### **Source Code:**
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
    singleInt = nullptr; // Prevent dangling pointer

    delete[] dynamicArray;
    dynamicArray = nullptr; // Prevent dangling pointer

    return 0;
}
```

---

### **Result:**

```
Value of singleInt: 25
Elements of dynamicArray: 10 20 30
-------------------------------------
## **Program 9(a): Friend Class**

---

### **Aim:**

To demonstrate the concept of a **friend class** in C++ and show how one class can access private and protected members of another class.

---

### **Algorithm:**

1. Start the program.
2. Define a class `Geeks` with private and protected data members.
3. Declare another class `GFG` as a **friend class** inside `Geeks`.
4. Define a function inside `GFG` that accesses private and protected members of `Geeks`.
5. Create objects of both classes and call the display function.
6. Stop the program.

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

    // Friend class declaration
    friend class GFG;
};

// Class GFG can access private members of Geeks
class GFG {
public:
    void display(Geeks& t) {
        cout << "The value of Private Variable = "
             << t.private_variable << endl;
        cout << "The value of Protected Variable = "
             << t.protected_variable;
    }
};

int main() {
    Geeks g;
    GFG fri;
    fri.display(g);
    return 0;
}
```

---

### **Output:**

```
The value of Private Variable = 10
The value of Protected Variable = 99
```

---


## **Program 9(b): Friend Function**

---

### **Aim:**

To illustrate the concept of a **friend function** in C++ that can access private and protected members of a class.

---

### **Algorithm:**

1. Start the program.
2. Define a class `base` with private and protected members.
3. Declare a **friend function** that can access these members.
4. Define the friend function outside the class.
5. Create an object of `base` and call the friend function.
6. Display the values of private and protected members.
7. Stop the program.

---

### **Source Code:**

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

    // Friend function declaration
    friend void friendFunction(base& obj);
};

// Friend function definition
void friendFunction(base& obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable;
}

int main() {
    base object1;
    friendFunction(object1);
    return 0;
}
```

---

### **Output:**

```
Private Variable: 10
Protected Variable: 99
```

---

### **Explanation:**

* `friendFunction()` is a **non-member function**, but it can access private and protected members of the class `base`.
* It is declared as a **friend** inside the class definition.
* A friend function can be declared in **any section** (private, public, or protected).

---

## **Program 9(c): Member Function of Another Class as Friend Function**

---

### **Aim:**

To demonstrate how a **member function of another class** can be declared as a **friend** of a class in C++.

---

### **Algorithm:**

1. Start the program.
2. Forward declare class `base`.
3. Define another class `GFG` with a member function `GFG_Function()`.
4. In class `base`, declare `GFG_Function()` as a **friend function**.
5. Define the function outside both classes using the **scope resolution operator**.
6. Create objects of both classes and call the function.
7. Stop the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

// Forward Declaration
class base;

// Another class in which function is declared
class GFG {
public:
    void GFG_Function(base& obj);
};

// Base class declares a friend function of another class
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

    // Friend function declaration
    friend void GFG::GFG_Function(base&);
};

// Friend function definition
void GFG::GFG_Function(base& obj) {
    cout << "Private Variable: " << obj.private_variable << endl;
    cout << "Protected Variable: " << obj.protected_variable;
}

int main() {
    base object1;
    GFG object2;
    object2.GFG_Function(object1);

    return 0;
}
```

---

### **Output:**

```
Private Variable: 10
Protected Variable: 99
-------------------------------------
## ✅ **Program 10: Exception Handling in C++**

---

### **Aim:**

To demonstrate **exception handling** in C++ using `try`, `throw`, and `catch` blocks.

---

### **Algorithm:**

1. Start the program.
2. Accept two integers from the user as input.
3. Check if the denominator is zero.
4. If zero, **throw an exception**.
5. If not zero, perform division operation.
6. Catch the thrown exception and display an error message.
7. End the program.

---

### **Source Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int numerator, denominator;
    
    cout << "Enter numerator: ";
    cin >> numerator;
    cout << "Enter denominator: ";
    cin >> denominator;

    try {
        if (denominator == 0) {
            throw "Error! Division by zero is not allowed.";
        }
        double result = (double)numerator / denominator;
        cout << "Result = " << result << endl;
    }
    catch (const char* msg) {
        cout << msg << endl;
    }

    return 0;
}
```

---

### **Output:**

✅ Case 1: Valid input

```
Enter numerator: 20
Enter denominator: 4
Result = 5
```

❌ Case 2: Division by zero

```
Enter numerator: 10
Enter denominator: 0
Error! Division by zero is not allowed.
```

