# minimal-llvm-coding-rules
# LLVM Coding Rules

Welcome to the LLVM project! This README outlines the minimal coding rules to follow when contributing to LLVM.
Based on LLVM Coding Standards https://llvm.org/docs/CodingStandards.html

## Coding Rules

1. **Naming Conventions**:
   - Use camelCase for variable names, function names, and method names.
     ```cpp
     int myVariable;
     void myFunction() {}
     ```

2. **Formatting**:
   - Use consistent indentation (typically 2 or 4 spaces) for code blocks.
     ```cpp
     if (condition) {
       // Code block
     }
     ```

3. **Comments and Documentation**:
   - Use comments to explain non-obvious code.
     ```cpp
     // This function calculates the sum of two integers.
     int calculateSum(int a, int b) {
       return a + b;
     }
     ```

4. **Header Files**:
   - Use header guards or `#pragma once` to prevent multiple inclusions.
     ```cpp
     #ifndef EXAMPLE_H
     #define EXAMPLE_H

     // Code goes here

     #endif // EXAMPLE_H
     ```

5. **Memory Management**:
   - Use smart pointers for managing dynamically allocated memory.
     ```cpp
     std::unique_ptr<MyObject>  obj(new MyObject());;
     ```

6. **Error Handling**:
   - Prefer error codes or return values to indicate error conditions.
     ```cpp
     bool isValidIndex(int index) {
       if (index >= 0 && index < size) {
         return true;
       }
       return false;
     }
     ```

7. **Const Correctness**:
   - Use `const` wherever applicable to indicate immutability.
     ```cpp
     void printMessage(const std::string& message) {
       std::cout << message << std::endl;
     }
     ```

8. **Coding Style**:
   - Follow LLVM's coding style guide consistently.
     ```cpp
     // Example of LLVM coding style
     void exampleFunction() {
       // Code here
     }
     ```

9. **Standard Library**:
   - Utilize the C++ Standard Library for common tasks.
     ```cpp
     std::vector<int> myVector;
     myVector.push_back(10);
     ```

10. **Conventions and Idioms**:
    - Follow LLVM-specific conventions and idioms for coding patterns.
      ```cpp
      // LLVM coding convention for constants
      const int MY_CONSTANT = 42;
      ```

11. **Class Private Variables Naming**:
    - Prefix class private variables with `m_` to distinguish them from other variables.
    ```cpp
    class MyClass {
    private:
        int m_value;
        const int m_constantValue;
    };
    ```

12. **Class Member Visibility**:
    - Explicitly specify the visibility of class members as `public`, `protected`, or `private`.
    ```cpp
    class MyClass {
    public:
        int publicMember;

    protected:
        int protectedMember;

    private:
        int privateMember;
    };
    ```

13. **Structure of Classes**:
    - Follow a consistent structure for class definitions:
      - Public section: Contains public member functions and data members.
      - Protected section: Contains protected member functions and data members.
      - Private section: Contains private member functions and data members.
    ```cpp
    class MyClass {
    public:
        // Public member functions

    protected:
        // Protected member functions

    private:
        // Private member functions
    };
    ```

14. **Use of `struct` for Plain Data Structures**:
    - Use `struct` for plain data structures that consist solely of data members without member functions.
    ```cpp
    struct Point {
        int x;
        int y;
    };
    ```

15. **Initialization of Class Members**:
    - Prefer initialization lists to initialize class members, especially for non-trivial types or const members.
    ```cpp
    class MyClass {
    private:
        int value;
        const int constantValue;

    public:
        MyClass(int v, int cv) : value(v), constantValue(cv) {}
    };
    ```

16. **Class Declaration in Header Files**:
    - Declare class and structure definitions in header files (`.h` or `.hpp`).
    - Define member functions in separate source files (`.cpp`) to adhere to the separation of interface and implementation.
    ```cpp
    // MyClass.h
    #ifndef MYCLASS_H
    #define MYCLASS_H

    class MyClass {
    public:
        void myFunction();
    };

    #endif // MYCLASS_H
    ```

    ```cpp
    // MyClass.cpp
    #include "MyClass.h"

    void MyClass::myFunction() {
        // Function implementation
    }
    ```

These coding rules provide guidance on naming conventions, formatting, comments, documentation, and best practices for writing clean and consistent C++ code in the LLVM project. Adhering to these rules helps maintain readability, consistency, and maintainability of the codebase.
