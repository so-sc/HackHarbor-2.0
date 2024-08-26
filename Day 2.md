---
day: 2
title: "Control Structures and Functions"
description: "Covering Conditional Statements, Loops, Scope and Lifetime of Variables and Errors"
---

# Day 2 - Blocks

## Conditional Statements

### if Statement
The `if` statement is used to execute a block of code if a condition is true.
```c
if (condition) {
    // code to be executed
}
```

### else-if Statement
The `else if` statement is used to check another condition if the initial condition is false.
```c
if (condition1) {
    // code to be executed if condition1 is true
} else if (condition2) {
    // code to be executed if condition1 is false and condition2 is true
}
```

### else Statement
The `else` statement is used to execute a block of code if all conditions are false.
```c
if (condition1) {
    // code to be executed if condition1 is true
} else if (condition2) {
    // code to be executed if condition1 is false and condition2 is true
} else {
    // code to be executed if all conditions are false
}
```

### switch Statement
The `switch` statement is used to execute a block of code based on the value of a variable.
```c
switch (variable) {
    case value1:
        // code to be executed if variable == value1
        break;
    case value2:
        // code to be executed if variable == value2
        break;
    default:
        // code to be executed if variable does not match any value
        break;
}
```

## Loops

### for Loop
The `for` loop is used to execute a block of code repeatedly for a specified number of times.

```c
for (initialization; condition; increment) {
    // code to be executed
}
```

### while Loop
The `while` loop is used to execute a block of code repeatedly while a condition is true.

```c
while (condition) {
    // code to be executed
}
```

### do-while Loop
The `do-while` loop is used to execute a block of code repeatedly while a condition is true.

```c
do {
    // code to be executed
} while (condition);
```

## Scope and Lifetime of Variables

### Scope
Scope refers to the region of the program where a variable is accessible.

- **Local Scope:** Variables declared inside a function are local to that function.
- **Global Scope:** Variables declared outside any function are global and accessible by any function.

### Lifetime
Lifetime refers to the duration for which a variable exists in memory.

- **Automatic (local) variables:** Exist only within the function they are defined.
- **Static variables:** Retain their value between function calls and exist for the lifetime of the program.

### Local Variables in Blocks
Local variables can be declared within blocks of code other than functions, such as if statements, while loops, and for loops. These variables are only accessible within the block they are declared in.

```c
if (condition) {
    int local_var = 10; // Local variable
    // code to be executed
}
```
```c
for (int i = 0; i < 10; i++) {
    int local_var = 20; // Local variable
    // code to be executed
}
```
Note that these local variables are created and destroyed each time the block is executed.
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 10; i++) {
        int local_var = 20; // Local variable
        printf("Local variable: %d\n", local_var);
    }
    return 0;
}
```

### Variable Overiding
If there exist 2 variables with the same name, one in local scope and the other in global scope. The local scope will always have higher priority.
```c
#include <stdio.h>
int i = 30;                         // Global variable

int main() {
    printf("global version of i: %d\n", i);
    for (int i = 0; i < 10; i++) {  // Local variable 1
        printf("\tfor loop's version of i: %d\n", i);
        if (i < 5) {
            int i = 0;              // Local variable 2
            printf("\t\tif blocks's version of i: %d\n", i);
        }
        printf("\tfor loop's version of i: %d\n", i);
    }
    printf("global version of i: %d\n", i);
    return 0;
}
```

## Errors - Types and Definitions
In programming, errors can be classified into several types. Understanding these types is crucial for effective debugging and error handling.

### Syntax Errors
Syntax errors occur when the code violates the programming language's syntax rules. These errors are typically detected by the compiler or interpreter.
```c
// Syntax error example: missing semicolon
int x = 5
```

### Semantic Errors
Semantic errors occur when the code is syntactically correct but does not make sense in the context of the program. These errors can be detected by the compiler or at runtime.
```c
// Semantic error example: assigning a string to an integer variable
int x = "hello";
```

### Logical Errors
Logical errors occur when the code is syntactically correct and semantically correct but does not produce the desired output. These errors can be difficult to detect and require thorough testing.
```c
// Logical error example: incorrect calculation
int x = 5;
int y = 3;
int result = x - y; // instead of x + y
```

### Runtime Errors
Runtime errors occur when the code encounters an error during execution. These errors can be caused by various factors such as division by zero, null pointer exceptions, or out-of-range values.
```c
// Runtime error example: division by zero
int x = 5;
int y = 0;
int result = x / y;
```