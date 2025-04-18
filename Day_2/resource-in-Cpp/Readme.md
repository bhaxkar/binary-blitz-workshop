# C++ Basics: Input/Output and Control Structures

This guide covers fundamental concepts of input/output operations in C++ along with essential control structures (loops and conditionals).

## Table of Contents
- [Input and Output](#input-and-output)
  - [Console Output](#console-output)
  - [Console Input](#console-input)
- [Control Structures](#control-structures)
  - [Conditional Statements](#conditional-statements)
  - [Loop Structures](#loop-structures)
- [Examples](#examples)

## Input and Output

### Console Output

C++ provides several ways to output data to the console:

```cpp
#include <iostream>

int main() {
    // Print without a new line
    std::cout << "Hello";
    
    // Print with a new line
    std::cout << "Hello World" << std::endl;
    
    // Alternative for new line
    std::cout << "Hello World\n";
    
    // Formatted output
    std::cout << "Number: " << 10 
              << ", String: " << "Hello"
              << ", Float: " << 5.12345 << std::endl;
    
    return 0;
}
```

### Console Input

To read input from the console, we use `cin`:

```cpp
#include <iostream>
#include <string>

int main() {
    // Variables to store input
    std::string name;
    int age;
    double height;
    
    // Read a string
    std::cout << "Enter your name: ";
    std::getline(std::cin, name);
    
    // Read an integer
    std::cout << "Enter your age: ";
    std::cin >> age;
    
    // Read a double
    std::cout << "Enter your height (in meters): ";
    std::cin >> height;
    
    std::cout << "Name: " << name << ", Age: " << age << ", Height: " << height << "m" << std::endl;
    
    return 0;
}
```

## Control Structures

### Conditional Statements

#### If-Else Statement

The `if-else` statement is used to execute different code blocks based on specified conditions.

```cpp
#include <iostream>

int main() {
    int number = 10;
    
    // Simple if statement
    if (number > 0) {
        std::cout << "The number is positive" << std::endl;
    }
    
    // If-else statement
    if (number % 2 == 0) {
        std::cout << "The number is even" << std::endl;
    } else {
        std::cout << "The number is odd" << std::endl;
    }
    
    // If-else-if ladder
    if (number > 0) {
        std::cout << "The number is positive" << std::endl;
    } else if (number < 0) {
        std::cout << "The number is negative" << std::endl;
    } else {
        std::cout << "The number is zero" << std::endl;
    }
    
    return 0;
}
```

#### Switch Statement

The `switch` statement is used to select one of many code blocks to be executed.

```cpp
#include <iostream>
#include <string>

int main() {
    int day = 3;
    std::string dayName;
    
    switch (day) {
        case 1:
            dayName = "Monday";
            break;
        case 2:
            dayName = "Tuesday";
            break;
        case 3:
            dayName = "Wednesday";
            break;
        case 4:
            dayName = "Thursday";
            break;
        case 5:
            dayName = "Friday";
            break;
        case 6:
            dayName = "Saturday";
            break;
        case 7:
            dayName = "Sunday";
            break;
        default:
            dayName = "Invalid day";
    }
    
    std::cout << "Day: " << dayName << std::endl;
    
    return 0;
}
```

### Loop Structures

#### For Loop

The `for` loop is used when you know how many times you want to execute a block of code.

```cpp
#include <iostream>

int main() {
    // Basic for loop
    for (int i = 0; i < 5; i++) {
        std::cout << "Iteration " << i << std::endl;
    }
    
    // For loop with multiple variables
    for (int i = 0, j = 10; i < j; i++, j--) {
        std::cout << "i = " << i << ", j = " << j << std::endl;
    }
    
    return 0;
}
``` 

#### While Loop

The `while` loop executes a block of code as long as a specified condition is true.

```cpp
#include <iostream>

int main() {
    int count = 0;
    
    while (count < 5) {
        std::cout << "Count: " << count << std::endl;
        count++;
    }
    
    return 0;
}
```

#### Do-While Loop

The `do-while` loop is similar to the while loop, but it executes the code block once before checking the condition.

```cpp
#include <iostream>

int main() {
    int count = 0;
    
    do {
        std::cout << "Count: " << count << std::endl;
        count++;
    } while (count < 5);
    
    return 0;
}
```

## Examples

### Example 1: Calculator using cin and If-Else

```cpp
#include <iostream>

int main() {
    double num1, num2, result;
    char op;
    
    // Get user input
    std::cout << "Enter first number: ";
    std::cin >> num1;
    
    std::cout << "Enter second number: ";
    std::cin >> num2;
    
    std::cout << "Enter an operator (+, -, *, /): ";
    std::cin >> op;
    
    // Perform calculation based on operator
    if (op == '+') {
        result = num1 + num2;
    } else if (op == '-') {
        result = num1 - num2;
    } else if (op == '*') {
        result = num1 * num2;
    } else if (op == '/') {
        if (num2 != 0) {
            result = num1 / num2;
        } else {
            std::cout << "Error: Division by zero" << std::endl;
            return 1;
        }
    } else {
        std::cout << "Error: Invalid operator" << std::endl;
        return 1;
    }
    
    // Display the result
    std::cout << num1 << " " << op << " " << num2 << " = " << result << std::endl;
    
    return 0;
}
```

### Example 2: Finding Prime Numbers using Loops

```cpp
#include <iostream>
#include <cmath>

int main() {
    int limit;
    
    // Get user input
    std::cout << "Enter the upper limit: ";
    std::cin >> limit;
    
    std::cout << "Prime numbers up to " << limit << ":" << std::endl;
    
    // Loop through numbers from 2 to the limit
    for (int number = 2; number <= limit; number++) {
        bool isPrime = true;
        
        // Check if the number is prime
        for (int i = 2; i <= std::sqrt(number); i++) {
            if (number % i == 0) {
                isPrime = false;
                break;
            }
        }
        
        // Print the number if it's prime
        if (isPrime) {
            std::cout << number << " ";
        }
    }
    
    std::cout << std::endl;
    
    return 0;
}
```
