# [[Fundamentals of C++ and Procedural Programming]]

## [[Introduction to C++]]

C++ is a high-level, general-purpose programming language created by Bjarne Stroustrup as an extension of the C programming language. It introduces [[Object-Oriented Programming]] while retaining the speed, efficiency, and procedural foundations of C.

### The [[Compilation Process]]

C++ is a compiled language, meaning human-readable source code is translated directly into machine code by a compiler before execution. This process happens in four distinct stages:

**ASCII Diagram of the Compilation Pipeline:**

Plaintext

```
                  +------------------+
[Source Code] --> | 1. Preprocessor  |  (Expands #includes and #defines)
(.cpp files)      +------------------+
                           |
                           V
                  +------------------+
                  |   2. Compiler    |  (Translates C++ to Assembly/Machine Code)
                  +------------------+
                           |
                           V
                  +------------------+
                  |  3. Assembler    |  (Creates Object files: .obj or .o)
                  +------------------+
                           |
                     [Object Files]
                           |
                           V
                  +------------------+
 [Libraries] ---> |    4. Linker     |  (Combines object files and libraries)
                  +------------------+
                           |
                           V
                  [Executable File]     (.exe or a.out)
```

### Structure of a C++ Program

A basic C++ program consists of header files, the standard namespace, and a `main` function where execution begins.

C++

```
#include <iostream> // Preprocessor directive for Input/Output stream

int main() {
    // std::cout is used to print output to the console
    std::cout << "Hello, Engineering Students!" << std::endl;
    return 0; // Returns 0 to the Operating System indicating successful execution
}
```

- **`#include <iostream>`:** Instructs the preprocessor to include the standard [[iostream]] library, which contains definitions for reading and writing data (like `std::cin` and `std::cout`).
    
- **`int main()`:** The entry point of every C++ program. It must return an integer type.
    

## [[Data Types and Operators]]

Variables in C++ must be declared with a specific data type before they can be used. This determines how much memory is allocated and what operations can be performed on the data.

### [[Primitive Data Types]]

|**Data Type**|**Description**|**Typical Size (Bytes)**|**Range (Approximate)**|
|---|---|---|---|
|`int`|Integer numbers|$4$|$-2 \times 10^9$ to $2 \times 10^9$|
|`float`|Single-precision floating point|$4$|$7$ decimal digits of precision|
|`double`|Double-precision floating point|$8$|$15$ decimal digits of precision|
|`char`|Single character (ASCII)|$1$|$-128$ to $127$|
|`bool`|Boolean value|$1$|`true` ($1$) or `false` ($0$)|

### [[Type Conversion]]

- **Implicit Conversion (Coercion):** Handled automatically by the compiler when assigning a smaller data type to a larger one (e.g., `int` to `double`).
    
- **Explicit Conversion (Casting):** Manually enforced by the programmer to prevent data loss or force a specific operation.
    
    C++
    
    ```
    int a = 10;
    int b = 3;
    // Without casting, 10/3 yields integer 3. Casting forces floating-point division.
    double result = static_cast<double>(a) / b; 
    ```
    

### [[Operators]]

C++ provides various operators to manipulate data:

- **Arithmetic:** `+`, `-`, `*`, `/`, `%` (Modulo, yields remainder).
    
- **Relational:** `==`, `!=`, `<`, `>`, `<=`, `>=`.
    
- **Logical:** `&&` (AND), `||` (OR), `!` (NOT).
    
- **Bitwise:** `&` (Bitwise AND), `|` (Bitwise OR), `<<` (Left Shift), `>>` (Right shift).
    

## [[Control Structures]]

[[Procedural Programming]] relies heavily on altering the sequential flow of execution based on logic and states.

### Conditional Statements

**1. The `if-else` Statement:**

Executes a block of code if a condition evaluates to `true`.

C++

```
int temperature = 85;
if (temperature > 100) {
    std::cout << "Boiling";
} else if (temperature > 0) {
    std::cout << "Liquid";
} else {
    std::cout << "Solid";
}
```

**2. The `switch` Statement:**

Used for multiple distinct branches based on an integral or character variable.

C++

```
char grade = 'A';
switch (grade) {
    case 'A': std::cout << "Excellent"; break;
    case 'B': std::cout << "Good"; break;
    default: std::cout << "Needs Improvement";
}
```

### [[Loops]]

**1. The `for` Loop:**

Best when the number of iterations is known beforehand.

C++

```
// for (initialization; condition; increment/decrement)
for (int i = 0; i < 5; i++) {
    std::cout << i << " "; // Outputs: 0 1 2 3 4
}
```

**2. The `while` Loop:**

Executes as long as a condition remains true. Condition is checked _before_ the loop body executes.

C++

```
int n = 5;
while (n > 0) {
    n--; 
}
```

**3. The `do-while` Loop:**

Condition is checked _after_ the loop body executes. Guarantees at least one execution.

C++

```
int option;
do {
    std::cout << "Enter positive number: ";
    std::cin >> option;
} while (option <= 0);
```

## [[Functions]]

A function is a reusable block of code designed to perform a specific task. Functions embody the core philosophy of procedural programming: breaking down large problems into smaller, manageable sub-routines.

### Declaration and Definition

- **Declaration (Prototype):** Tells the compiler the function's name, return type, and parameters. Usually placed above `main()`.
    
- **Definition:** The actual implementation body of the function.
    

C++

```
// Declaration
int add(int a, int b); 

int main() {
    int sum = add(5, 3); // Function call
    return 0;
}

// Definition
int add(int a, int b) {
    return a + b;
}
```

### [[Pass-by-Value]] vs. [[Pass-by-Reference]]

- **Pass-by-Value:** A _copy_ of the variable is passed to the function. Modifying the parameter inside the function does not affect the original variable.
    
- **Pass-by-Reference:** The _memory address_ of the variable is passed using the reference operator `&`. Modifying the parameter directly alters the original variable, saving memory and processing time for large data structures.
    

C++

```
void modifyByValue(int x) {
    x = 100; // Original variable remains unchanged
}

void modifyByReference(int &x) {
    x = 100; // Original variable is modified to 100
}
```

### [[Inline Functions]]

Defined using the `inline` keyword. The compiler replaces the function call with the actual function code. This eliminates the overhead of a function call for very short, frequently used functions, speeding up execution.

### [[Function Overloading]]

C++ allows multiple functions to share the exact same name, provided their parameter lists (number of parameters or types) differ. The compiler determines which function to call based on the arguments provided.

C++

```
int computeArea(int side) { 
    return side * side; // Square
}
double computeArea(double radius) { 
    return 3.14159 * radius * radius; // Circle
}
```

## [[Basic Data Structures]]

### [[Arrays]]

An array is a collection of elements of the _same data type_ stored in contiguous memory locations. Arrays in C++ have a fixed size defined at compile-time.

C++

```
int scores[5] = {90, 85, 88, 92, 100};
scores[0] = 95; // Arrays are zero-indexed. This changes 90 to 95.
```

_Memory Math:_ If an integer takes $4$ bytes, an array of $5$ integers takes exactly $20$ bytes of continuous memory.

### [[C-style Strings]]

Inherited from C, these are simply arrays of characters terminated by a special null character `'\0'` to indicate the end of the string.

C++

```
char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
// Equivalently:
char sameGreeting[] = "Hello"; // Compiler adds '\0' automatically
```

### [[std::string]]

A much safer and more versatile class provided by the C++ Standard Library to handle text. It automatically manages memory, resizes as needed, and provides built-in functions for concatenation, substring extraction, and comparison.

C++

```
#include <string>

std::string firstName = "Alan";
std::string lastName = "Turing";
std::string fullName = firstName + " " + lastName; // String concatenation
```

## [[Solved Examples]]

**Problem:** Write a modular C++ program using procedural concepts to find the maximum value in an integer array and compute the average of its elements. Pass the array to functions appropriately.

**Solution:**

C++

```
#include <iostream>

// Function Declarations
int findMax(const int arr[], int size);
double computeAverage(const int arr[], int size);

int main() {
    int dataSet[5] = {12, 45, 7, 89, 23};
    int size = 5;

    int maxVal = findMax(dataSet, size);
    double avgVal = computeAverage(dataSet, size);

    std::cout << "Maximum Value: " << maxVal << std::endl;
    std::cout << "Average Value: " << avgVal << std::endl;

    return 0;
}

// Function Definitions
int findMax(const int arr[], int size) {
    int currentMax = arr[0];
    for (int i = 1; i < size; i++) {
        if (arr[i] > currentMax) {
            currentMax = arr[i];
        }
    }
    return currentMax;
}

double computeAverage(const int arr[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i]; // Accumulate sum
    }
    // Explicit type cast to prevent integer division
    return static_cast<double>(sum) / size; 
}
```

# [[Formula Sheet]]

_In programming, our formulas are core syntax patterns._

- **Basic Program Skeleton:**
    
    `#include <iostream>`
    
    `int main() { ... return 0; }`
    
- **For Loop Syntax:**
    
    `for (init; condition; update) { ... }`
    
- **Pass-by-Reference Syntax:**
    
    `returnType functionName(dataType &variableName) { ... }`
    
- **Array Declaration:**
    
    `dataType arrayName[size];`
    
- **Casting Syntax (Modern C++):**
    
    `static_cast<newType>(variable)`
    

# [[Problem Solving Strategy]]

When approaching a computational problem in C++ procedural programming:

1. **Understand Inputs and Outputs:** Determine what data types are required. Will a `float` suffice, or is the precision of a `double` necessary?
    
2. **Break down into Functions (Modularization):** Do not write everything inside `main()`. If a task can be described in a single sentence (e.g., "Sort the array," "Calculate the root"), it should be its own function.
    
3. **Choose the Right Control Structure:**
    
    - Use `for` loops when you know exactly how many iterations are needed (like iterating through an array).
        
    - Use `while` loops for event-driven logic (e.g., "keep prompting the user until they enter a valid number").
        
4. **Memory Considerations:** If passing large datasets (like an array or a massive `std::string`) to a function, pass by reference `&` to avoid the performance penalty of copying data. Use `const` if the function should not alter the data.
    

# [[Common Mistakes]]

- **Missing Semicolons (`;`):** The most frequent compilation error for beginners. Every standard statement must end with a semicolon.
    
- **Index Out of Bounds:** C++ arrays are zero-indexed. An array of size $5$ has indices $0, 1, 2, 3, 4$. Accessing `arr[5]` will read or corrupt adjacent memory, leading to unpredictable behavior or segmentation faults.
    
- **Integer Division:** Writing `5 / 2` yields `2`, not `2.5`. At least one operand must be a float/double (e.g., `5.0 / 2`) to perform floating-point division.
    
- **Assignment vs. Equality:** Using `=` (assignment) instead of `==` (comparison) in an `if` statement. For example, `if (x = 5)` assigns $5$ to $x$ and evaluates to `true`, which is almost never the intended logic.
    
- **Dangling Null Terminators:** Forgetting the `\0` when manually constructing C-style strings, causing the program to read garbage memory until it randomly hits a null byte.
    

# [[Applications]]

- **Embedded Systems & IoT:** Procedural C++ is heavily used in programming microcontrollers (like Arduino) where memory is strictly constrained, making low-level arrays and pass-by-reference functions highly efficient.
    
- **High-Frequency Trading:** The speed of compiled C++ and the low overhead of inline functions allow financial institutions to execute algorithms in microseconds.
    
- **Operating Systems:** Much of the structural foundations of modern OS drivers are written procedurally in C/C++, leveraging direct memory access and strict control flows.
    

# [[Summary]]

The [[Fundamentals of C++ and Procedural Programming]] establish the building blocks for translating human logic into machine execution. Beginning with a rigorous [[Compilation Process]], C++ mandates explicit declaration of [[Primitive Data Types]] and leverages a wide array of [[Operators]] to manipulate memory. By utilizing [[Control Structures]] (conditionals and loops), programmers can dictate the exact execution path of algorithms. Through the use of [[Functions]], especially the powerful [[Pass-by-Reference]] paradigm, code becomes modular and efficient. Finally, organizing primitive types into [[Basic Data Structures]] like [[Arrays]] and `std::string` provides the necessary scaffolding to handle large and complex datasets.

# [[Related Notes]]

- [[Object-Oriented Programming]]
    
- [[Pointers and Memory Management]]
    
- [[Data Structures and Algorithms]]
    
- [[Time and Space Complexity]]
    
- [[Object-Oriented C++]]