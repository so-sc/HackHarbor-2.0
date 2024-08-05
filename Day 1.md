---
day: 1
title: "Refresher to C programming"
description: "History of C, basic syntax, hello-world, operators and expressions"
---

# Day 1 - Refresher to C Programming
<!-- Course content goes here -->
## Setting up the Environment
Installing a compiler: [GCC (MinGW)](https://sourceforge.net/projects/mingw/files/Installer/)

Install an IDE/Editor : [Visual Studio Code](https://code.visualstudio.com/download)

***Note:***: If `gcc` isn't recognized as a command, make sure that you've added its **bin** folder's path as an environment variable.

## Basic Syntax and Structure:  
1. **Preprocessor Directives:** Preprocessor directives are lines included in the code that are not program statements but instructions for the preprocessor. They begin with the # symbol. The most common preprocessor directive is `#include`. 

    *Example:* `#include<stdio.h>`, `#define PI 3.142`
2. **main() Function:**  Every C program must have a main function. This is the entry point of the program where execution begins.
```c
#include<stdio.h>
void main(){
    //your code here
}
``` 
3. **Statement Termination with `;`:** In C, each statement must end with a semicolon (`;`). This tells the compiler that the statement is complete.
```c
printf("Hello");
//semicolon marks the end of the statement
```
4. **Comments:** Comments are used to explain the code and are ignored by the compiler. They make the code more readable.
```c
//This is a single line comment
printf("Hello");
/*
This is a
multiline comment
*/
printf("There");
```
## Writing and running the first program ("Hello, World!")
```c
#include<stdio.h> //standard input-output header
void main(){
    printf("Hello World"); //simple print statement
}
```
##  Variables and Data Types: Integers, floats, characters, and basic I/O functions
Variables are used to store data. Each variable must be declared with a specific data type.  
`int`: Integer type  
`float`: Floating-point type  
`char`: Character type  
`double`: Long-floating-point type  
`void`: void type  
```c
int num = 10;        // Integer variable
float price = 9.99;  // Floating-point variable
char grade = 'A';    // Character variable
```
6. Input and Output  
C provides standard functions to take input and display output.  
`printf`: Used to print output to the screen.  
```c
printf("Hello, World!\n");
```
`scanf`: Used to take input from the user.  
```c
int n;
scanf("%d",&n);
```
Here `%d` is the format specifier used for integer datatype.
Some other format specifiers are
* `%f` -float
* `%c` -char
* `%lf` - long float/double
* `%s` - string/character_array
# Operators and Expressions
### Arithmetic Operators

Arithmetic operators are used to perform basic mathematical operations.

### Addition
```c
int a = 5;
int b = 3;
int sum = a + b;
printf("Sum: %d\n", sum);  // Output: Sum: 8
```

### Subtraction
```c
int a = 5;
int b = 3;
int difference = a - b;
printf("Difference: %d\n", difference);  // Output: Difference: 2
```

### Multiplication
```c
int a = 5;
int b = 3;
int product = a * b;
printf("Product: %d\n", product);  // Output: Product: 15
```

### Division
```c
int a = 6;
int b = 3;
int quotient = a / b;
printf("Quotient: %d\n", quotient);  // Output: Quotient: 2
```

### Modulus
```c
int a = 5;
int b = 3;
int remainder = a % b;
printf("Remainder: %d\n", remainder);  // Output: Remainder: 2
```

## Relational and Logical Operators

### Relational Operators

Relational operators are used to compare two values.

```c
int a = 5;
int b = 3;

printf("%d\n", a == b);  // Output: 0 (false)
printf("%d\n", a != b);  // Output: 1 (true)
printf("%d\n", a > b);   // Output: 1 (true)
printf("%d\n", a < b);   // Output: 0 (false)
printf("%d\n", a >= b);  // Output: 1 (true)
printf("%d\n", a <= b);  // Output: 0 (false)
```

### Logical Operators

Logical operators are used to combine multiple conditions.

```c
int a = 5;
int b = 3;
int c = 5;

printf("%d\n", (a > b) && (a == c));  // Output: 1 (true)
printf("%d\n", (a < b) || (a == c));  // Output: 1 (true)
printf("%d\n", !(a == c));            // Output: 0 (false)
```

## Increment and Decrement Operators

Increment and decrement operators are used to increase or decrease the value of a variable by one.

### Increment
```c
int a = 5;

a++;  // Postfix increment
printf("a: %d\n", a);  // Output: a: 6

++a;  // Prefix increment
printf("a: %d\n", a);  // Output: a: 7
```

### Decrement
```c
int a = 5;

a--;  // Postfix decrement
printf("a: %d\n", a);  // Output: a: 4

--a;  // Prefix decrement
printf("a: %d\n", a);  // Output: a: 3
```

## Assignment Operators

Assignment operators are used to assign values to variables.

### Basic Assignment
```c
int a = 5;
```

### Compound Assignment
```c
int a = 5;

a += 3;  // Equivalent to a = a + 3
printf("a: %d\n", a);  // Output: a: 8

a -= 2;  // Equivalent to a = a - 2
printf("a: %d\n", a);  // Output: a: 6

a *= 2;  // Equivalent to a = a * 2
printf("a: %d\n", a);  // Output: a: 12

a /= 3;  // Equivalent to a = a / 3
printf("a: %d\n", a);  // Output: a: 4

a %= 3;  // Equivalent to a = a % 3
printf("a: %d\n", a);  // Output: a: 1
```

## Type Casting and Type Conversion

Type casting and conversion allow you to change a variable's data type.

### Implicit Type Conversion
Automatically performed by the compiler when necessary.

```c
int a = 5;
float b = 2.5;
float result = a + b;  // a is implicitly converted to float
printf("Result: %.2f\n", result);  // Output: Result: 7.50
```

### Explicit Type Casting
Manually performed by the programmer.

```c
int a = 5;
int b = 2;
float result = (float)a / b;  // a is explicitly cast to float
printf("Result: %.2f\n", result);  // Output: Result: 2.50
```

## Activity Problems  
1. [Hello World in C](https://www.hackerrank.com/challenges/hello-world-c/problem)
2. [Playing with characters](https://www.hackerrank.com/challenges/playing-with-characters/problem)
3. [Sum and Diff of two numbers](https://www.hackerrank.com/challenges/sum-numbers-c/problem)
4. [Division Anomaly](https://www.codechef.com/practice/course/c/LPCAS01/problems/LCAS02)
5. [Modulo Game](https://www.codechef.com/practice/course/c/LPCAS01/problems/LCAS08)
6. [Increment Operator](https://www.geeksforgeeks.org/questions/c-operators-question-24/)
7. [Temperature Converter](https://www.codechef.com/practice/course/c/LPCAS03/problems/LCAS30B)
8. [Assignment Operator](https://www.codechef.com/learn/course/c/LBCL07A/problems/PPSC29)
8. [Total prize money (debug the code)](https://www.codechef.com/learn/course/c-beginner-v2-p1/BC01BC05_V2/problems/BMCP10)
10. [Ternary Operator](https://www.codechef.com/learn/course/c/LBCL07A/problems/PPSC27D)
