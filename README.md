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


