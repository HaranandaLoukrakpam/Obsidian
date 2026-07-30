# [[The Standard Template Library (STL) and File IO]]
## [[Introduction to STL]]

The [[Standard Template Library]] (STL) is a powerful, template-based collection of classes and functions in C++ that provides standardized, highly optimized implementations of common data structures and algorithms. The STL is divided into three core components:

1. **[[Containers]]:** Data structures that store collections of objects.
    
2. **[[Iterators]]:** Pointer-like objects used to traverse these containers safely.
    
3. **[[Algorithms]]:** Functions that perform operations (searching, sorting, transforming) on containers.
    

## [[STL Containers]]

Containers manage the memory space for their elements and provide member functions to access them. They are generally categorized into Sequence and Associative containers.

### [[Sequence Containers]]

Sequence containers store data in a linear, sequential manner.

- **[[std::vector]]:** A dynamic array that automatically resizes itself when elements are added or removed. It provides contiguous memory allocation.
    
    - **Strengths:** $O(1)$ time complexity for random access and insertion/deletion at the end.
        
    - **Weaknesses:** $O(N)$ time complexity for insertion/deletion in the middle or beginning.
        
- **[[std::list]]:** A doubly-linked list. Elements are stored in non-contiguous memory locations, linked by pointers.
    
    - **Strengths:** $O(1)$ insertion/deletion anywhere (if the iterator is already at the position).
        
    - **Weaknesses:** $O(N)$ random access (no index-based access).
        
- **[[std::deque]]:** A double-ended queue. Like a vector, but optimized for fast insertion and deletion at _both_ the beginning and the end.
    

### [[Associative Containers]]

Associative containers are non-linear and excel at retrieving data quickly using keys. They are typically implemented using self-balancing binary search trees (like Red-Black Trees) or Hash Tables.

|**Container**|**Underlying Structure**|**Time Complexity (Search/Insert)**|**Properties**|
|---|---|---|---|
|**[[std::set]]**|Red-Black Tree|$O(\log N)$|Stores unique elements in sorted order.|
|**[[std::map]]**|Red-Black Tree|$O(\log N)$|Stores unique Key-Value pairs in sorted order by key.|
|**[[std::unordered_map]]**|Hash Table|$O(1)$ average, $O(N)$ worst|Stores Key-Value pairs in no particular order. extremely fast lookups.|

## [[STL Iterators]]

[[Iterators]] act as a bridge between Containers and Algorithms. They behave like C++ pointers, allowing you to access and traverse the elements of a container without needing to know its underlying memory structure.

C++

```
std::vector<int> numbers = {10, 20, 30};
// Using traditional iterators
for (std::vector<int>::iterator it = numbers.begin(); it != numbers.end(); ++it) {
    std::cout << *it << " "; // Dereferencing the iterator
}
```

### [[Range-Based For Loops]]

Introduced in C++11, this loop abstracts away the iterators, making traversal incredibly clean.

C++

```
// Using auto infers the type. We use reference '&' to avoid copying, 
// and 'const' to prevent modification.
for (const auto& num : numbers) {
    std::cout << num << " ";
}
```

## [[STL Algorithms]]

The `<algorithm>` header contains dozens of functions that operate on ranges of elements, specified by starting and ending iterators.

- **[[std::sort]]:** Sorts elements in ascending order by default. It utilizes IntroSort (a hybrid of QuickSort, HeapSort, and InsertionSort), guaranteeing $O(N \log N)$ performance.
    
    C++
    
    ```
    std::sort(numbers.begin(), numbers.end());
    ```
    
- **[[std::find]]:** Performs a linear search $O(N)$ to find a specific element.
    
    C++
    
    ```
    auto it = std::find(numbers.begin(), numbers.end(), 20);
    if (it != numbers.end()) std::cout << "Found: " << *it;
    ```
    

## [[Advanced Features]]

To make algorithms more flexible, C++ allows us to pass custom behavior directly into STL functions.

### [[Functors]] (Function Objects)

A Functor is any class or struct that overloads the `operator()`. It behaves like a function but can maintain internal state (attributes).

C++

```
struct Multiplier {
    int factor;
    Multiplier(int f) : factor(f) {}
    int operator()(int x) const { return x * factor; }
};
```

### [[Lambda Expressions]]

Introduced in C++11, a Lambda is an anonymous, inline function. It allows you to write quick, throwaway logic exactly where it is needed without declaring a separate class or function.

**Syntax:** `[capture_clause](parameters) -> return_type { body }`

C++

```
std::vector<int> v = {4, 1, 3, 5, 2};
// Sorting in descending order using a lambda
std::sort(v.begin(), v.end(), [](int a, int b) {
    return a > b; 
});
```

_Note:_ The capture clause `[]` allows the lambda to access local variables from the surrounding scope (e.g., `[&]` captures all local variables by reference).

## [[File Input and Output]]

C++ handles file operations via the `<fstream>` library, which treats files as streams of characters.

- **[[std::ifstream]]:** Input File Stream. Used exclusively for reading data from a file.
    
- **[[std::ofstream]]:** Output File Stream. Used exclusively for writing data to a file.
    
- **[[std::fstream]]:** File Stream. Can handle both reading and writing.
    

### [[Parsing CSV Data]]

A common engineering task is reading Comma-Separated Values (CSV). We use `std::getline` with a custom delimiter to parse the data.

C++

```
#include <fstream>
#include <sstream>
#include <string>

// Inside a function...
std::ifstream file("data.csv");
std::string line, value;

while (std::getline(file, line)) {       // Read file row by row
    std::stringstream ss(line);          // Convert row string into a stream
    while (std::getline(ss, value, ',')) { // Extract tokens separated by commas
        std::cout << value << " | ";
    }
    std::cout << "\n";
}
```

## [[Solved Examples]]

**Problem:** Read a sequence of temperatures from a file, store them in a vector, use an STL algorithm with a lambda to filter out temperatures below freezing ($< 0$), and write the valid temperatures to a new CSV file in descending order.

**Solution:**

C++

```
#include <iostream>
#include <fstream>
#include <vector>
#include <algorithm>

int main() {
    // 1. Read from File
    std::ifstream inFile("input_temps.txt");
    if (!inFile.is_open()) {
        std::cerr << "Error opening input file." << std::endl;
        return 1;
    }

    std::vector<double> temps;
    double temp;
    while (inFile >> temp) {
        temps.push_back(temp);
    }
    inFile.close();

    // 2. Erase-Remove Idiom to filter out negative temperatures
    // std::remove_if moves elements to delete to the end, erase physically removes them.
    temps.erase(std::remove_if(temps.begin(), temps.end(), [](double t) {
        return t < 0.0;
    }), temps.end());

    // 3. Sort in descending order
    std::sort(temps.begin(), temps.end(), [](double a, double b) {
        return a > b;
    });

    // 4. Write to CSV File
    std::ofstream outFile("valid_temps.csv");
    if (!outFile.is_open()) {
        std::cerr << "Error opening output file." << std::endl;
        return 1;
    }

    outFile << "Index,Temperature\n"; // CSV Header
    for (size_t i = 0; i < temps.size(); ++i) {
        outFile << i + 1 << "," << temps[i] << "\n";
    }
    outFile.close();

    std::cout << "Data processed and saved." << std::endl;
    return 0;
}
```

# [[Formula Sheet]]

_Syntax cheat sheet for STL and File I/O:_

- **Vector Iteration:** `for (const auto& elem : myVector) { ... }`
    
- **Map Iteration:**
    
    `for (const auto& pair : myMap) { cout << pair.first << ":" << pair.second; }`
    
- **Custom Sort:** `std::sort(v.begin(), v.end(), [](T a, T b){ return a < b; });`
    
- **File Opening Check:** `if (!file.is_open()) { /* handle error */ }`
    
- **Read Token by Delimiter:** `std::getline(stream, string_var, 'delimiter')`
    

# [[Problem Solving Strategy]]

1. **Selecting the Right Container:**
    
    - If you need fast traversal and append-only operations: use `[[std::vector]]`.
        
    - If you need to quickly check if an item exists: use `[[std::unordered_set]]` ($O(1)$ lookups).
        
    - If you are counting frequencies of words or mapping IDs to Objects: use `[[std::map]]` or `[[std::unordered_map]]`.
        
2. **Avoid Reinventing the Wheel:** Before writing a custom loop to find, count, replace, or reverse data, check the `<algorithm>` header. `std::count`, `std::reverse`, and `std::transform` are heavily optimized and less bug-prone than manual loops.
    
3. **File Parsing Mentality:** Never assume file data is perfectly formatted. Read line-by-line using `std::getline`, dump the line into a `std::stringstream`, and parse the string stream token by token. This prevents formatting errors from crashing the main file stream.
    

# [[Common Mistakes]]

- **Iterator Invalidation:** If you loop through a `std::vector` and use `.erase()` or `.push_back()` inside the loop, the underlying memory might be reallocated. This invalidates all active iterators, causing undefined behavior or segmentation faults.
    
- **Copying Containers by Accident:** Writing `for (auto item : myVector)` creates a deep copy of every single item in the vector. If the vector contains large objects, this destroys performance. Always use `for (const auto& item : myVector)`.
    
- **Forgetting to Close Files:** While standard fstream objects close automatically when they go out of scope (due to RAII), relying on this in long-running functions can lock files, preventing other programs from reading them. Explicitly call `.close()` when done.
    
- **`std::map` accidental insertion:** Using the `[]` operator on a map (e.g., `if (myMap["key"] == 5)`) will _silently insert_ "key" into the map with a default value if it doesn't already exist. Use `myMap.find("key")` to check for existence safely.
    

# [[Applications]]

- **Data Processing Pipelines:** Reading raw sensor data from `.csv` files, storing it in a `[[std::vector]]`, applying `[[std::sort]]` to find median values, and writing the clean data back to disk.
    
- **Graph Algorithms:** `[[std::vector]]` is used to build adjacency lists, while `[[std::deque]]` (or `std::queue`) and `[[std::set]]` are critical for maintaining the frontier and visited states in Breadth-First Search (BFS) and Dijkstra's algorithm.
    
- **Configuration Management:** Using `[[std::map]]` to read and store key-value pairs from a `.ini` or text configuration file upon program startup, providing $O(\log N)$ access to system settings.
    

# [[Summary]]

The [[Standard Template Library]] elevates C++ from a low-level systems language to a highly expressive, data-driven tool. By mastering [[STL Containers]], engineers can select the mathematically optimal data structure (balancing $O(1)$ lookups with contiguous memory benefits). [[STL Iterators]] and [[STL Algorithms]] decouple logic from storage, allowing single lines of code—often powered by inline [[Lambda Expressions]]—to replace dozens of lines of manual loops. Combined with robust File I/O techniques using `ifstream` and string streams, programmers can efficiently parse massive external datasets (like CSVs), process them in memory, and export the results cleanly.

# [[Related Notes]]

- [[Data Structures and Algorithms]]
    
- [[Computational Complexity]] (Big O Notation)
    
- [[Memory Management and Advanced C++ Concepts]]
    
- [[Pointers and References]]
    
- [[Object-Oriented Programming in C++]]