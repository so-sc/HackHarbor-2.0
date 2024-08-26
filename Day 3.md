---
day: 3
title: "Function Basics"
description: "Covering Function Definition, Declaration, and Calling Functions"
---


## Function Basics: Definition, Declaration, and Calling Functions

### Definition
A function definition provides the actual body of the function. It includes the function's return type, name, parameters, and body.
```c
return_type function_name(parameter_list) {
    // function body
}
```

### Declaration
A function declaration, also known as a prototype, declares the function and its parameters without providing the body. This informs the compiler about the function's existence.
```c
return_type function_name(parameter_list);
```

### Calling Functions
To call a function, simply use its name followed by the argument list.
```c
function_name(argument_list);
```

### Example
```c
#include<stdio.h>

// Function declaration
int add(int a, int b);

int main() {
    int sum = add(5, 3);
    printf("Sum: %d\n", sum);
    return 0;
}

// Function definition
int add(int a, int b) {
    return a + b;
}
```

## Parameters and Return Values

### Parameters
Parameters are variables listed as part of a function's declaration and definition.
- **Formal Parameters:** Parameters in the function definition.
- **Actual Parameters:** Parameters passed to the function when it is called.

### Return Values
A function can return a value back to the caller using the `return` statement.
```c
#include<stdio.h>

int multiply(int x, int y) {
    return x*y;
}

int main() {
    int result = multiply(4, 5);
    printf("Result: %d\n", result);
    return 0;
}
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

### Example
```c
#include<stdio.h>

int global_var = 10; // Global variable

void demo() {
    int local_var = 20; // Local variable
    static int static_var = 30; // Static variable
    printf("Local: %d, Static: %d, Global: %d\n", local_var, static_var, global_var);
    local_var++;
    static_var++;
}

void main(){
    demo();
    demo();
}
```

## Recursive Functions

### Definition
A recursive function is a function that calls itself either directly or indirectly to solve a problem.

### Example
```c
#include<stdio.h>

// Function to calculate factorial of a number
int factorial(int n) {
   if(n==1||n==0) return 1; //base cases
   return n*factorial(n-1);
}

int main() {
    int num;
    scanf("%d",&num);
    printf("Factorial of %d is %d\n", num, factorial(num));
    return 0;
}
```

### Advantages and Disadvantages
**Advantages:**
- Simplifies the code for problems that can be broken down into similar sub-problems.

**Disadvantages:**
- Can lead to excessive memory usage and stack overflow if not implemented correctly.