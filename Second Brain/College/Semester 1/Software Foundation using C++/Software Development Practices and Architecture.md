# [[Software Development Practices and Architecture]]

## [[Software Development Life Cycle (SDLC)]]

The [[Software Development Life Cycle]] (SDLC) is a structured framework outlining the phases involved in building software applications, from initial planning to deployment and maintenance.

### [[Waterfall Methodology]]

The traditional, linear approach to software development. Each phase (Requirements, Design, Implementation, Testing, Deployment, Maintenance) must be completed sequentially before the next begins.

- **Strengths:** Highly predictable, well-documented, ideal for strict regulatory environments (e.g., aerospace, medical devices).
    
- **Weaknesses:** Inflexible. If a design flaw is discovered during the testing phase, returning to the design phase is costly and time-consuming.
    

### [[Agile Methodology]]

An iterative and incremental approach. Software is built in small, manageable cycles, allowing for rapid adaptation to changing requirements and continuous feedback from users.

### [[Scrum]]

The most popular [[Agile]] framework. Work is divided into fixed-length iterations called **Sprints** (typically 2-4 weeks).

- **Roles:** Product Owner (prioritizes work), Scrum Master (removes blockers), Development Team (builds the software).
    
- **Artifacts:** Product Backlog (everything that needs to be built), Sprint Backlog (work committed for the current sprint).
    

## [[Version Control]]

[[Version Control]] systems record changes to a file or set of files over time, allowing developers to recall specific versions, collaborate seamlessly, and track down bugs.

### [[Git]]

Git is a distributed version control system. Every developer has a complete local copy of the repository, including its entire history.

- **Commits:** A snapshot of the repository at a specific point in time. Each commit has a unique cryptographic SHA-1 hash.
    
- **Branching:** Creating an independent line of development. Developers create a branch to work on a new feature without affecting the stable main codebase.
    
- **Merging:** Combining the history of one branch into another.
    
- **Pull Requests (PRs):** A formal request to merge a feature branch into the main branch. PRs act as a gateway for code reviews and automated testing before code is integrated.
    

**ASCII Diagram of Git Branching and Merging:**

Plaintext

```
main:      A --- B --- C -------------- G
                        \              / (Merge PR)
feature:                 D --- E --- F
```

## [[Build Systems and Compilation]]

For a simple program, invoking the compiler directly (`g++ main.cpp -o app`) suffices. However, enterprise software contains thousands of source files. Recompiling everything after a single line change is computationally expensive.

### [[Makefiles]]

A [[Makefile]] uses the `make` utility to automate the build process. It relies on a dependency graph. If a target file is older than its dependencies, `make` recompiles it.

Makefile

```
# Simple Makefile Example
app: main.o math_utils.o
	g++ main.o math_utils.o -o app

main.o: main.cpp
	g++ -c main.cpp

math_utils.o: math_utils.cpp
	g++ -c math_utils.cpp
```

### [[CMake]]

[[CMake]] is a modern, cross-platform meta-build system. Instead of building the software directly, it generates native build environments (like Makefiles on Linux, or Visual Studio solutions on Windows) from a single `CMakeLists.txt` configuration file.

CMake

```
# Simple CMakeLists.txt Example
cmake_minimum_required(VERSION 3.10)
project(EngineeringApp)

# Create an executable named 'app' from these source files
add_executable(app main.cpp math_utils.cpp)
```

## [[Testing and Debugging]]

### [[Debugging]] with [[GDB]]

The GNU Debugger ([[GDB]]) allows you to inspect what a program is doing internally while it executes. To use it, you must compile your code with the `-g` flag to include debugging symbols.

- **Breakpoints:** Pause execution at a specific line.
    
- **Stepping:** Execute code line-by-line (`step` to go inside functions, `next` to step over them).
    
- **Backtrace:** View the call stack to see exactly which sequence of functions led to a crash (Segmentation Fault).
    

### [[Unit Testing]]

Testing individual components (functions or classes) in isolation to ensure they behave exactly as intended.

### [[Google Test]] (GTest)

A robust C++ testing framework. It uses macros to assert conditions.

C++

```
#include <gtest/gtest.h>
#include "math_utils.h"

// Test case for the add function
TEST(MathUtilsTest, HandlesPositiveInput) {
    EXPECT_EQ(add(2, 3), 5); // Non-fatal assertion
    ASSERT_TRUE(add(10, 10) == 20); // Fatal assertion (aborts test if false)
}

int main(int argc, char **argv) {
    ::testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}
```

## [[Software Design Principles]]

Writing code that simply "works" is insufficient. Enterprise code must be maintainable, scalable, and readable.

### [[SOLID Principles]]

Five core principles of object-oriented design:

1. **Single Responsibility Principle (SRP):** A class should have only one reason to change (it should do exactly one job).
    
2. **Open/Closed Principle (OCP):** Software entities should be open for extension (via inheritance/interfaces) but closed for modification.
    
3. **Liskov Substitution Principle (LSP):** Derived classes must be perfectly substitutable for their base classes without breaking program logic.
    
4. **Interface Segregation Principle (ISP):** Clients should not be forced to depend on interfaces they do not use. Prefer many small, specific interfaces over one large one.
    
5. **Dependency Inversion Principle (DIP):** High-level modules should not depend on low-level modules; both should depend on abstractions (interfaces).
    

### [[Design Patterns]]

Typical, reusable solutions to common problems in software design.

**1. [[Singleton Pattern]] (Creational):**

Ensures a class has only one instance and provides a global point of access to it. Often used for hardware interfaces or configuration managers.

C++

```
class Database {
private:
    static Database* instance;
    Database() {} // Private constructor
public:
    static Database* getInstance() {
        if (instance == nullptr) {
            instance = new Database();
        }
        return instance;
    }
};
```

**2. [[Factory Pattern]] (Creational):**

Provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created. Prevents tight coupling to specific concrete classes.

**3. [[Observer Pattern]] (Behavioral):**

Defines a one-to-many dependency between objects. When one object (the Subject) changes state, all its dependents (Observers) are notified and updated automatically. Heavily used in GUI event handling and real-time data feeds.

# [[Formula Sheet]]

While software architecture is largely conceptual, performance and testing metrics are often quantified mathematically.

- **Test Coverage:** The percentage of your codebase executed by your automated tests.
    
    $$C = \left( \frac{L_{tested}}{L_{total}} \right) \times 100$$
    
- **Cyclomatic Complexity ($M$):** A software metric used to indicate the complexity of a program, measuring the number of linearly independent paths through a program's source code. High complexity indicates code that is difficult to test and maintain.
    
    $$M = E - N + 2P$$
    
    **Variables:**
    
    - $E$: Number of edges in the control flow graph.
        
    - $N$: Number of nodes (sequential blocks of code).
        
    - $P$: Number of connected components (usually $1$ for a single program).
        

**Core Git Commands:**

- `git clone <url>`: Download a repository.
    
- `git checkout -b <branch>`: Create and switch to a new branch.
    
- `git commit -m "Message"`: Commit staged changes.
    
- `git push origin <branch>`: Upload branch to remote server.
    

**Core GDB Commands:**

- `break main`: Set breakpoint at main function.
    
- `run`: Start execution.
    
- `next`: Execute next line.
    
- `print var`: Display value of variable `var`.
    

# [[Problem Solving Strategy]]

When architecting a new software feature or fixing a complex bug, follow these systematic steps:

1. **Requirement Analysis (SDLC):** Define exactly what the code must do before writing a single line. Draft the interfaces (headers).
    
2. **Apply SOLID Principles:** Ensure your new class has a single responsibility. If it needs to interact with an external system, use the [[Dependency Inversion Principle]] to inject an interface rather than hard-coding the dependency.
    
3. **Write Tests First (TDD):** Use [[Google Test]] to write assertions defining the expected behavior. The tests will fail initially.
    
4. **Implement and Build:** Write the C++ implementation. Configure your `CMakeLists.txt` to link the files properly.
    
5. **Debug Scientifically:** If a crash occurs, do not use random `std::cout` statements. Compile with `-g`, load the executable into [[GDB]], type `run`, and use the `backtrace` command to pinpoint the exact line causing the segmentation fault.
    
6. **Version Control Integration:** Commit small, logical chunks of work with descriptive messages. Push your branch and open a Pull Request.
    

# [[Common Mistakes]]

- **God Classes:** Violating the Single Responsibility Principle by creating massive classes (e.g., `SystemManager`) that handle rendering, physics, networking, and saving files. This makes the code impossible to test or maintain.
    
- **Hardcoding Dependencies:** Instantiating objects directly inside a class using `new` instead of passing them in via the constructor (Dependency Injection). This makes mocking and unit testing impossible.
    
- **Committing Broken Code to Main:** Failing to use Git branching properly. The `main` branch should always be in a deployable state. All experimentation should happen on feature branches.
    
- **Ignoring Build Systems:** Compiling complex projects manually via the terminal. This leads to missing linker flags and inconsistencies between developer machines. Always rely on [[CMake]].
    
- **Catching General Exceptions:** Catching `std::exception` without understanding why the program failed, effectively hiding bugs rather than fixing the underlying architectural flaw.
    

# [[Applications]]

- **Continuous Integration / Continuous Deployment (CI/CD):** Whenever a Pull Request is opened, automated build servers pull the code, use [[CMake]] to build the project, and execute the [[Google Test]] suite. If any test fails, the code is blocked from merging.
    
- **Game Engine Architecture:** Engines like Unreal Engine rely heavily on the [[Observer Pattern]] for event systems (e.g., triggering sounds when an entity takes damage) and the [[Factory Pattern]] for spawning different types of enemies dynamically.
    
- **Embedded Systems:** In environments where memory is strictly constrained, developers use the [[Singleton Pattern]] to manage exclusive access to specific hardware registers or communication buses (like I2C or SPI) to prevent data collisions.
    

# [[Summary]]

Transitioning from writing simple scripts to engineering enterprise software requires rigorous [[Software Development Practices and Architecture]]. By organizing work through Agile [[SDLC]] frameworks like [[Scrum]], teams can adapt to changing requirements. [[Version Control]] systems like [[Git]] ensure code history is safely tracked and collaboration is seamless. Large codebases rely on [[Build Systems and Compilation]] tools like [[CMake]] to manage dependencies across platforms. Ensuring reliability requires strict [[Testing and Debugging]] regimens using [[GDB]] and frameworks like [[Google Test]]. Ultimately, organizing code using [[SOLID Principles]] and established [[Design Patterns]] ensures the software remains scalable, maintainable, and robust against future changes.

# [[Related Notes]]

- [[Object-Oriented Programming in C++]]
    
- [[Fundamentals of C++ and Procedural Programming]]
    
- [[Memory Management and Advanced C++ Concepts]]
    
- [[Data Structures and Algorithms]]
    
- [[Operating Systems Memory Management]]