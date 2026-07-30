# [[Memory Management and Advanced C++ Concepts]]

## [[Pointers and References]]

In C++, understanding how to interact directly with system memory is what gives the language its notorious power and performance. Memory is accessed sequentially, and we interact with it using [[Pointers]] and [[References]].

### [[Pointers]]

A pointer is a variable that stores the memory address of another variable. Instead of holding a data value (like $5$ or 'A'), it holds the physical location in the RAM where that data resides.

C++

```
int var = 42;
int* ptr = &var; // ptr now holds the memory address of var
```

### [[References]]

A reference is an alias, or an alternative name, for an already existing variable. Once a reference is initialized to a variable, it cannot be changed to refer to another variable.

C++

```
int original = 10;
int& ref = original; // ref is now another name for original
```

**Key Differences:**

- Pointers can be reassigned to point to different addresses; references cannot be reassigned after initialization.
    
- Pointers can be `nullptr` (point to nothing); references must always refer to a valid object.
    
- Pointers require dereferencing (`*ptr`) to access the value; references are used exactly like the original variable.
    

### [[Pointer Arithmetic]]

Because pointers hold memory addresses (which are essentially numerical values), you can perform arithmetic on them. When you add $1$ to a pointer, it does not simply add $1$ byte to the address. It adds the size of the data type it points to.

$$\text{New Address} = \text{Base Address} + (i \times \text{Size of Data Type})$$

**Variables:**

- $i$: The integer added to the pointer.
    
- $\text{Size of Data Type}$: Evaluated in bytes (e.g., $4$ bytes for a standard `int`).
    

### [[Arrays of Pointers]]

Just as you can have an array of integers, you can have an array of pointers. This is frequently used for managing arrays of C-style strings or dynamically allocated objects.

C++

```
const char* names[3] = {"Alan", "Ada", "Bjarne"};
```

## [[Dynamic Memory Allocation]]

### [[The Stack vs The Heap]]

To understand dynamic memory, one must understand the two primary regions of RAM used during program execution:

1. **The Stack:** Memory allocated automatically for local variables and function calls. It is fast, structured, but limited in size. Memory is freed automatically when variables go out of scope.
    
2. **The Heap:** A large pool of memory used for dynamic allocation. The programmer has complete control over when memory is requested and when it is freed.
    

**ASCII Diagram:**

Plaintext

```
 +------------------+ High Address
 |      Stack       | (Grows Downward)
 |        |         |
 |        v         |
 |                  |
 |                  |
 |        ^         |
 |        |         |
 |      Heap        | (Grows Upward)
 +------------------+ Low Address
```

### `new` and `delete`

In C++, you request memory from the Heap using the `new` operator, which returns a pointer to the allocated memory. You must release this memory using the `delete` operator to prevent a [[Memory Leak]].

C++

```
// Allocating a single integer
int* dynInt = new int(100); 
delete dynInt; 

// Allocating an array
int* dynArray = new int[50];
delete[] dynArray; // Note the [] required for arrays!
```

### [[Memory Leaks]]

A memory leak occurs when memory is allocated on the heap but the pointer holding its address is lost or goes out of scope before `delete` is called. The operating system cannot reclaim this memory until the program terminates, eventually causing the system to run out of RAM and crash.

## [[Modern Memory Management]]

Raw pointers (`*`) and manual `delete` statements are dangerous and prone to human error. C++11 introduced [[Smart Pointers]] to automate memory management, adhering to the principle of [[RAII]].

### [[RAII]] (Resource Acquisition Is Initialization)

RAII is a core C++ programming idiom. It dictates that resources (like heap memory, file handles, or network sockets) should be acquired during object construction and released during object destruction. Since destructors are called automatically when an object goes out of scope, RAII guarantees that resources are never leaked.

### [[Smart Pointers]]

Included via the `<memory>` library, smart pointers act like regular pointers but automatically manage the memory they point to.

|**Smart Pointer**|**Ownership Model**|**When is memory freed?**|
|---|---|---|
|**`std::unique_ptr`**|Exclusive (1:1). Cannot be copied, only moved.|When the pointer goes out of scope.|
|**`std::shared_ptr`**|Shared (1:N). Multiple pointers can own the same data.|When the reference count drops to exactly $0$.|
|**`std::weak_ptr`**|Observer. Views data owned by a `shared_ptr` but doesn't increase the reference count.|Does not govern freeing memory; used to prevent cyclic references.|

**ASCII Diagram of Shared Pointer Reference Counting:**

Plaintext

```
 [ ptrA ] \
           --> [ Control Block: RefCount=2 ] ---> [ Heap Data ]
 [ ptrB ] /
 
 *If ptrB goes out of scope, RefCount becomes 1. 
 *If ptrA goes out of scope, RefCount becomes 0, and Heap Data is deleted.*
```

## [[Error and Exception Handling]]

Runtime anomalies (like dividing by zero, failing to open a file, or running out of memory) must be handled gracefully to prevent immediate program crashes.

- **`try`**: A block of code that might generate an exception.
    
- **`throw`**: A keyword used to signal that an error has occurred.
    
- **`catch`**: A block of code that handles the specific error thrown.
    

C++

```
#include <iostream>
#include <stdexcept>

double divide(double a, double b) {
    if (b == 0) {
        throw std::invalid_argument("Division by zero!");
    }
    return a / b;
}
```

### [[Custom Exception Classes]]

You can define your own exceptions by inheriting from the standard exception base class.

C++

```
class NetworkException : public std::exception {
public:
    const char* what() const noexcept override {
        return "Network connection dropped.";
    }
};
```

## [[Templates]]

C++ is statically typed, meaning data types must be known at compile-time. [[Templates]] bypass this limitation by allowing you to write generic code that works with any data type. The compiler generates the specific type-safe versions of the code automatically when the template is used.

### [[Function Templates]]

C++

```
template <typename T>
T findMax(T a, T b) {
    return (a > b) ? a : b;
}
// Can be called as findMax<int>(5, 10) or findMax<double>(3.14, 2.71)
```

### [[Class Templates]]

Used heavily in the standard library to create generic data structures (like `std::vector` or `std::stack`).

## [[Solved Examples]]

**Problem:** Create a template class representing a dynamic generic array. Use modern memory management (`std::unique_ptr`) to ensure no memory leaks occur. Include exception handling if the user attempts to access an out-of-bounds index.

**Solution:**

C++

```
#include <iostream>
#include <memory>
#include <stdexcept>

// Template Class Declaration
template <typename T>
class SafeArray {
private:
    std::unique_ptr<T[]> data; // Smart pointer managing a dynamic array
    int size;

public:
    // Constructor
    SafeArray(int s) : size(s) {
        if (s <= 0) throw std::invalid_argument("Size must be positive");
        data = std::make_unique<T[]>(size); // C++14 dynamic array allocation
    }

    // Accessor Method with Bounds Checking
    T& getElement(int index) {
        if (index < 0 || index >= size) {
            throw std::out_of_range("Index out of bounds!");
        }
        return data[index];
    }

    // Setter Method
    void setElement(int index, T value) {
        if (index < 0 || index >= size) {
            throw std::out_of_range("Index out of bounds!");
        }
        data[index] = value;
    }
};

int main() {
    try {
        // Instantiate for integers
        SafeArray<int> myInts(5);
        myInts.setElement(0, 100);
        std::cout << "Value at 0: " << myInts.getElement(0) << std::endl;

        // This will trigger the exception
        myInts.setElement(10, 500); 
    } 
    catch (const std::exception& e) {
        std::cerr << "Error Caught: " << e.what() << std::endl;
    }

    // No delete[] needed! std::unique_ptr cleans up automatically.
    return 0;
}
```

# [[Formula Sheet]]

_Key Syntax Patterns for Memory and Advanced Features:_

- **Dynamic Allocation:**
    
    `DataType* ptr = new DataType;`
    
    `delete ptr;`
    
- **Unique Pointer (C++14+):**
    
    `std::unique_ptr<Type> ptr = std::make_unique<Type>(args);`
    
- **Shared Pointer (C++11+):**
    
    `std::shared_ptr<Type> ptr = std::make_shared<Type>(args);`
    
- **Template Function:**
    
    `template <typename T> T functionName(T param) { ... }`
    
- **Try-Catch Block:**
    
    C++
    
    ```
    try { throw std::runtime_error("msg"); }
    catch (const std::exception& e) { ... }
    ```
    

# [[Problem Solving Strategy]]

When handling dynamic memory and advanced types in C++:

1. **Default to Smart Pointers:** Never use `new` and `delete` in modern C++ unless absolutely necessary for a low-level library or hardware driver. Default to `std::unique_ptr`. Upgrade to `std::shared_ptr` only if you mathematically require multiple owners of the data.
    
2. **Pass by Const Reference:** When dealing with templates or complex objects, always pass parameters as `const T& obj` to avoid expensive copies and prevent unintended modifications.
    
3. **Catch by Reference:** Always catch exceptions by `const reference` (e.g., `catch(const std::exception& e)`). Catching by value causes "object slicing", where inherited exception data is truncated.
    
4. **Template Instantiation:** Remember that template code is strictly a blueprint. If you separate a template class into `.h` and `.cpp` files, you will get linker errors. Template implementations must reside entirely in the header file.
    

# [[Common Mistakes]]

- **Dangling Pointers:** Calling `delete` on a pointer, but forgetting to set it to `nullptr`. The pointer still holds the address of the freed memory. Attempting to use it later causes a segmentation fault.
    
- **Double Delete:** Calling `delete` twice on the same memory address. This immediately crashes the program.
    
- **Memory Leaks in Exceptions:** Using raw pointers in a function that throws an exception. If `new` is called, and an exception is thrown before `delete` is reached, the memory leaks. (This is why [[RAII]] and [[Smart Pointers]] are mandatory).
    
- **Cyclic References:** Two `std::shared_ptr` objects pointing at each other. Their reference counts will never drop below $1$, meaning the memory is never freed. Resolve this by making one a `std::weak_ptr`.
    

# [[Applications]]

- **Game Engines (Unreal Engine):** Extremely heavy reliance on pointers for spatial manipulation, memory pooling, and physics simulations where raw performance is required. They use proprietary smart pointers to manage game entity lifecycles.
    
- **Standard Template Library (STL):** The entire C++ STL (`std::vector`, `std::map`, `std::sort`) is built on [[Templates]], allowing the same highly optimized algorithms to sort integers, strings, or custom 3D vectors.
    
- **High-Frequency Trading:** Requires precise control of the [[The Stack vs The Heap]]. Traders avoid heap allocations entirely during trading hours because the runtime overhead of requesting memory from the OS is too slow.
    

# [[Summary]]

Mastering C++ requires navigating the physical realities of computer architecture. [[Pointers]] and [[References]] allow for zero-overhead manipulation of data, while [[Dynamic Memory Allocation]] provides flexible access to the Heap. However, with absolute power comes absolute responsibility; manual memory management is fraught with [[Memory Leaks]] and crashes. Modern C++ solves this through [[RAII]] and [[Smart Pointers]], automating cleanup. Combined with the robust safety nets of [[Error and Exception Handling]] and the boundless flexibility of [[Templates]], C++ enables developers to write code that is simultaneously universally generic, mathematically safe, and hardware-efficient.

# [[Related Notes]]

- [[Object-Oriented Programming in C++]]
    
- [[Data Structures and Algorithms]]
    
- [[Standard Template Library (STL)]]
    
- [[Operating Systems Memory Management]]
    
- [[Computational Complexity]]