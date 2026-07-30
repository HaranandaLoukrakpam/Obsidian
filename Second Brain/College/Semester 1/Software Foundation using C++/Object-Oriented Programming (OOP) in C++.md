# [[Object-Oriented Programming in C++]]

## [[Classes and Objects]]

At the heart of [[Object-Oriented Programming]] (OOP) are **classes** and **objects**. OOP is a paradigm that organizes software design around data, or objects, rather than strictly functions and logic.

- **[[Class]]:** A user-defined data type that acts as a blueprint or template. It defines the structure (attributes/data) and behaviors (methods/functions) that its objects will possess.
    
- **[[Object]]:** A specific, physical instance of a class occupying memory during runtime.
    

**ASCII Diagram of Class vs Object:**

Plaintext

```
      CLASS (Blueprint)                 OBJECT (Instance)
 +-------------------------+       +-------------------------+
 |       Car_Blueprint     |       |       myCar             |
 |-------------------------|       |-------------------------|
 | - string brand          | ====> | - brand = "Toyota"      |
 | - int speed             |       | - speed = 120           |
 |-------------------------|       |-------------------------|
 | + accelerate()          |       | + accelerate()          |
 | + brake()               |       | + brake()               |
 +-------------------------+       +-------------------------+
```

### [[Access Specifiers]]

C++ uses access specifiers to enforce data hiding and security within a class.

|**Specifier**|**Visibility Inside Class**|**Visibility in Derived Class**|**Visibility Outside Class (main)**|
|---|---|---|---|
|**`private`** (Default)|Yes|No|No|
|**`protected`**|Yes|Yes|No|
|**`public`**|Yes|Yes|Yes|

## [[Constructors and Destructors]]

### [[Constructors]]

A constructor is a special member function automatically invoked when an object is instantiated. It has the exact same name as the class and **no return type** (not even `void`). Its primary purpose is to initialize the object's data members.

1. **Default Constructor:** Takes no arguments. If you do not provide any constructor, the C++ compiler generates a blank default constructor automatically.
    
2. **Parameterized Constructor:** Takes arguments to initialize an object with specific values at the time of creation.
    
3. **Copy Constructor:** Initializes a newly created object by copying the data from an existing object of the same class.
    

### [[Destructors]]

A destructor is automatically called when an object goes out of scope or is explicitly deleted. It has the same name as the class, preceded by a tilde (`~`). It takes no arguments and returns nothing. Its primary physical significance is memory management—freeing dynamically allocated memory to prevent **memory leaks**.

## [[Encapsulation and Abstraction]]

### [[Encapsulation]]

Encapsulation is the bundling of data (variables) and the methods that operate on that data into a single unit (the class). It also involves **data hiding**—making member variables `private` and providing `public` getter and setter methods to access or modify them safely.

### [[Abstraction]]

Abstraction means displaying only the essential information and hiding the complex background details. In C++, this is often achieved by separating the **interface** from the **implementation**.

- **Header Files (`.h` / `.hpp`):** Contain the class definitions, member declarations, and access specifiers (the Interface).
    
- **Source Files (`.cpp`):** Contain the actual programmatic logic of the methods (the Implementation).
    

## [[Inheritance]]

[[Inheritance]] allows a new class (the **Derived Class** or Child Class) to inherit the attributes and methods of an existing class (the **Base Class** or Parent Class). This promotes code reusability and establishes an "is-a" relationship (e.g., a Dog _is an_ Animal).

**Types of Inheritance:**

- **Single:** One child inherits from one parent.
    
- **Multiple:** One child inherits from multiple parents.
    
- **Multilevel:** A child inherits from a parent, which inherits from a grandparent.
    

### The `protected` Modifier

The `protected` access modifier is specifically designed for inheritance. A `protected` member is hidden from the outside world (like `private`), but it _can_ be directly accessed by derived classes.

## [[Polymorphism]]

[[Polymorphism]] translates to "many forms." It allows methods to do different things based on the object it is acting upon.

### [[Compile-Time Polymorphism]] (Static Binding)

Resolved during compilation.

- **Function Overloading:** Multiple functions with the same name but different parameters.
    
- **Operator Overloading:** Redefining how standard C++ operators (`+`, `-`, `==`) work for user-defined classes.
    

### [[Runtime Polymorphism]] (Dynamic Binding)

Resolved during program execution using pointers and the `virtual` keyword.

- **[[Virtual Functions]]:** A function declared in a base class using the `virtual` keyword that is meant to be overridden in a derived class. When a base class pointer points to a derived class object, calling a virtual function executes the derived class's version.
    
- **[[Abstract Classes]] and [[Pure Virtual Functions]]:** A pure virtual function is declared by assigning `= 0` in its declaration: `virtual void draw() = 0;`. A class containing at least one pure virtual function becomes an **Abstract Class**. You cannot instantiate an abstract class; it exists solely as a strict template for derived classes to implement.
    

## [[Solved Examples]]

**Problem:** Demonstrate Encapsulation, Inheritance, and Runtime Polymorphism using a Base class `Shape` and a Derived class `Rectangle`. Calculate the area using a base class pointer.

**Solution:**

C++

```
#include <iostream>

// Abstract Base Class
class Shape {
protected:
    double width;
    double height;

public:
    // Parameterized Constructor
    Shape(double w, double h) {
        width = w;
        height = h;
    }
    
    // Virtual Destructor (Crucial for proper memory cleanup in inheritance)
    virtual ~Shape() {} 

    // Pure Virtual Function forces derived classes to implement this
    virtual double calculateArea() = 0; 
};

// Derived Class
class Rectangle : public Shape {
public:
    // Constructor invoking Base Class constructor
    Rectangle(double w, double h) : Shape(w, h) {}

    // Overriding the pure virtual function
    double calculateArea() override {
        return width * height;
    }
};

int main() {
    // Cannot do: Shape s; // Error: Shape is abstract

    // Runtime Polymorphism: Base pointer pointing to Derived object
    Shape* rect = new Rectangle(5.0, 4.0);
    
    // Dynamically calls the Rectangle's version of calculateArea()
    std::cout << "Area of Rectangle: " << rect->calculateArea() << std::endl;

    delete rect; // Invokes virtual destructor
    return 0;
}
```

# [[Formula Sheet]]

_In Software Engineering, core syntax paradigms replace mathematical formulas._

- **Class Definition:**
    
    C++
    
    ```
    class ClassName {
    private:
        // data members
    public:
        ClassName(); // Constructor
        ~ClassName(); // Destructor
    };
    ```
    
- **Inheritance Syntax:**
    
    `class Derived : public Base { ... };`
    
- **Pure Virtual Function:**
    
    `virtual returnType functionName() = 0;`
    
- **Operator Overloading:**
    
    `ReturnType operator+(const ClassName& obj) { ... }`
    

# [[Problem Solving Strategy]]

When modeling a system using OOP in C++:

1. **Identify the Objects (Nouns):** Nouns in your problem statement become Classes (e.g., `Vehicle`, `Bank_Account`).
    
2. **Identify the Attributes (Adjectives/Properties):** These become `private` data members (e.g., `balance`, `speed`).
    
3. **Identify the Behaviors (Verbs):** These become `public` methods (e.g., `deposit()`, `accelerate()`).
    
4. **Establish Relationships:**
    
    - If classes share common properties (e.g., Car and Truck are both Vehicles), extract the commonalities into a Base class and use **Inheritance**.
        
    - If a class simply "has a" property of another class (e.g., a Car has an Engine), use composition (instantiate the Engine object inside the Car class).
        
5. **Use Polymorphism for Extensibility:** Design systems using pointers to Base classes. This allows you to add new derived classes later without changing the core execution logic.
    

# [[Common Mistakes]]

- **Missing Virtual Destructors:** If a base class pointer deletes a derived class object, and the base class lacks a `virtual` destructor, only the base portion of the object is destroyed, leading to severe memory leaks.
    
- **Shallow Copy vs. Deep Copy:** If your class dynamically allocates memory (using `new`), the default copy constructor performs a "shallow copy" (copying the memory address, not the data). Both objects will point to the same memory. You must write a custom copy constructor to perform a "deep copy".
    
- **Violating Encapsulation:** Making data members `public` out of laziness. This allows external code to arbitrarily change object states, bypassing validation logic normally placed in setter methods.
    
- **Forgetting Access Specifiers:** In a `class`, members are `private` by default. Many students write a constructor at the top of the class without writing `public:` first, resulting in compilation errors because the object cannot be instantiated.
    

# [[Applications]]

- **Game Engines:** Platforms like Unreal Engine rely heavily on C++ OOP. A base `Entity` class might spawn derived classes like `Player`, `Enemy`, and `NPC`, all controlled via a master list of `Entity*` pointers updating via Polymorphism.
    
- **GUI Frameworks:** Graphical User Interfaces (like Qt) use base `Widget` classes, from which `Button`, `TextBox`, and `Slider` inherit.
    
- **Simulation Systems:** Simulating physics, traffic, or fluid dynamics where millions of autonomous objects must encapsulate their own state (velocity, mass, position) and interact with one another.
    

# [[Summary]]

[[Object-Oriented Programming]] in C++ transforms procedural, top-down code into a modeled system of interacting entities. By defining [[Class]] templates, we instantiate [[Object]]s that safeguard their internal state through [[Encapsulation]] and [[Access Specifiers]]. [[Constructors]] ensure these objects are born in a valid state, while [[Destructors]] clean up memory upon their demise. [[Inheritance]] maps out hierarchical relationships to eliminate redundant code, while [[Polymorphism]]—via [[Virtual Functions]] and [[Abstract Classes]]—allows software to execute dynamic, modular behaviors at runtime. Mastering these paradigms is the gateway to writing scalable, maintainable, enterprise-level software.

# [[Related Notes]]

- [[Fundamentals of C++ and Procedural Programming]]
    
- [[Pointers and Memory Management]]
    
- [[Design Patterns]]
    
- [[Data Structures and Algorithms]]
    
- [[Software Engineering Principles]]