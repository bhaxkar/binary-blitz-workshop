# C++ Programming Examples: Loops and Problem Solving

This guide provides several example problems in C++ demonstrating the use of loops and various problem-solving techniques.

## Table of Contents
- [Example 1: Fibonacci Sequence Generator](#example-1-fibonacci-sequence-generator)
- [Example 2: Palindrome Checker](#example-2-palindrome-checker)
- [Example 3: Armstrong Number Checker](#example-3-armstrong-number-checker)
- [Example 4: Pattern Printing using Nested Loops](#example-4-pattern-printing-using-nested-loops)
- [Example 5: Find All Factors of a Number](#example-5-find-all-factors-of-a-number)
- [Example 6: Sum of Digits Calculator](#example-6-sum-of-digits-calculator)

## Example 1: Fibonacci Sequence Generator

This program generates the Fibonacci sequence up to a user-specified number of terms.

```cpp
#include <iostream>

int main() {
    int n;
    
    // Get user input
    std::cout << "Enter the number of Fibonacci terms to generate: ";
    std::cin >> n;
    
    std::cout << "First " << n << " Fibonacci numbers:" << std::endl;
    
    int first = 0;
    int second = 1;
    
    // Handle special cases
    if (n >= 1) {
        std::cout << first << " ";
    }
    if (n >= 2) {
        std::cout << second << " ";
    }
    
    // Generate remaining Fibonacci numbers using a loop
    for (int i = 3; i <= n; i++) {
        int next = first + second;
        std::cout << next << " ";
        
        // Update for next iteration
        first = second;
        second = next;
    }
    
    std::cout << std::endl;
    
    return 0;
}
```

## Example 2: Palindrome Checker

This program checks whether a given string is a palindrome (reads the same forward and backward).

```cpp
#include <iostream>
#include <string>

int main() {
    std::string input;
    
    // Get user input
    std::cout << "Enter a string: ";
    std::getline(std::cin, input);
    
    bool isPalindrome = true;
    int length = input.length();
    
    // Check if the string is a palindrome using for loop
    for (int i = 0; i < length / 2; i++) {
        if (input[i] != input[length - i - 1]) {
            isPalindrome = false;
            break;
        }
    }
    
    if (isPalindrome) {
        std::cout << "\"" << input << "\" is a palindrome." << std::endl;
    } else {
        std::cout << "\"" << input << "\" is not a palindrome." << std::endl;
    }
    
    return 0;
}
```

## Example 3: Armstrong Number Checker

This program checks whether a given number is an Armstrong number (the sum of its digits each raised to the power of the number of digits equals the number itself).

```cpp
#include <iostream>
#include <cmath>

int main() {
    int number;
    
    // Get user input
    std::cout << "Enter a number: ";
    std::cin >> number;
    
    // Store the original number
    int originalNumber = number;
    
    // Count the number of digits
    int digits = 0;
    int temp = number;
    while (temp > 0) {
        temp /= 10;
        digits++;
    }
    
    // Compute sum of nth powers of digits
    int sum = 0;
    temp = number;
    
    while (temp > 0) {
        int digit = temp % 10;
        int power = 1;
        
        // Calculate power using a loop
        for (int i = 0; i < digits; i++) {
            power *= digit;
        }
        
        sum += power;
        temp /= 10;
    }
    
    // Check if it's an Armstrong number
    if (sum == originalNumber) {
        std::cout << originalNumber << " is an Armstrong number." << std::endl;
    } else {
        std::cout << originalNumber << " is not an Armstrong number." << std::endl;
    }
    
    return 0;
}
```

## Example 4: Pattern Printing using Nested Loops

This program prints a pyramid pattern of stars based on the number of rows specified by the user.

```cpp
#include <iostream>

int main() {
    int rows;
    
    // Get user input
    std::cout << "Enter the number of rows: ";
    std::cin >> rows;
    
    std::cout << "Pattern:" << std::endl;
    
    // Outer loop for rows
    for (int i = 1; i <= rows; i++) {
        // Inner loop for spaces
        for (int j = 1; j <= rows - i; j++) {
            std::cout << " ";
        }
        
        // Inner loop for stars
        for (int k = 1; k <= 2 * i - 1; k++) {
            std::cout << "*";
        }
        
        std::cout << std::endl;
    }
    
    return 0;
}
```

## Example 5: Find All Factors of a Number

This program finds and displays all factors of a user-specified positive integer.

```cpp
#include <iostream>

int main() {
    int number;
    
    // Get user input
    std::cout << "Enter a positive integer: ";
    std::cin >> number;
    
    std::cout << "Factors of " << number << ":" << std::endl;
    
    // Find and print all factors
    for (int i = 1; i <= number; i++) {
        if (number % i == 0) {
            std::cout << i << " ";
        }
    }
    
    std::cout << std::endl;
    
    return 0;
}
```

## Example 6: Sum of Digits Calculator

This program calculates the sum of all digits in a user-specified number.

```cpp
#include <iostream>

int main() {
    int number;
    
    // Get user input
    std::cout << "Enter a number: ";
    std::cin >> number;
    
    int originalNumber = number;
    int sum = 0;
    
    // Calculate sum of digits using a while loop
    while (number > 0) {
        int digit = number % 10;
        sum += digit;
        number /= 10;
    }
    
    std::cout << "Sum of digits in " << originalNumber << " = " << sum << std::endl;
    
    return 0;
}
```


