---
day: 6
title: "Dynamic Memory Allocation"
description: "Covering Dynamic Memory Allocation, Pointer Arithmetic, and Pointer to Pointer"
---

# Day 6 - Dynamic Memory Allocation

## Difference between Static and Dynamic memory allocation


| |	Static Memory Allocation | Dynamic Memory Allocation |
| --- | --- | --- |
| **Allocation Time** | Compile-time | Runtime |
| **Memory Location** | Stack or Data Segment | Heap |
| **Size Flexibility** | Fixed-size | Variable-size |
| **Memory Leaks** | Not Possible | Possible |
| **Execution Speed** | Faster | Slower |
| **Deallocation** | Automatic | Manual |

## Dynamic Memory Allocation

### Introduction
Dynamic memory allocation is a technique used to allocate memory at runtime, rather than at compile time.

### malloc()
`malloc()` is a function that allocates a block of memory of a specified size.
```c
int* ptr = malloc(sizeof(int));
```

### calloc()
`calloc()` is a function that allocates a block of memory of a specified size and initializes all bits to zero.
```c
int* ptr = calloc(10, sizeof(int));
```

### realloc()
`realloc()` is a function that changes the size of a block of memory previously allocated by malloc() or calloc().
```c
int* ptr = malloc(sizeof(int));
ptr = realloc(ptr, 2 * sizeof(int));
```

### free()
`free()` is a function that releases a block of memory previously allocated by malloc(), calloc(), or realloc().
```c
int* ptr = malloc(sizeof(int));
free(ptr);
```

## Difference between malloc() and calloc()

### Similarities:

- **Both** malloc() and calloc() are used to dynamically allocate memory in C.
- **Both** functions return a void pointer to the beginning of the allocated memory block.
- **Both** functions can be used to allocate memory for arrays, structures, and other data types.

### Differences:

| | malloc() | calloc() |
| --- | --- | --- |
| **Initialization** | Does not initialize the allocated memory to any specific value| Initializes the allocated memory to zero. |
| **Number of arguments** | Takes one argument, the size of the memory block to be allocated | Takes two arguments, the number of elements and the size of each element. |
| **Memory layout** | Allocates a single block of memory | Allocates an array of memory blocks, each of the same size. |
| **Error handling** | If fails to allocate memory, returns a null pointer | Returns a null pointer if it fails to allocate memory, but also sets errno to ENOMEM. |
| **Performance** | Faster | Slower |

### When to use each:

#### Use malloc() when:
- You need to allocate memory for a single block of data.
- You don't need to initialize the memory to zero.
- You want faster allocation.
#### Use calloc() when:
- You need to allocate memory for an array of data.
- You need to initialize the memory to zero.
- You want to ensure that the memory is initialized to a specific value.

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // Using malloc()
    int* ptr1 = malloc(sizeof(int));
    if (ptr1 == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }
    *ptr1 = 10;
    printf("Value of ptr1: %d\n", *ptr1);

    // Using calloc()
    int* ptr2 = calloc(1, sizeof(int));
    if (ptr2 == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }
    printf("Value of ptr2: %d\n", *ptr2); // prints 0

    free(ptr1);
    free(ptr2);
    return 0;
}
```
In summary, malloc() and calloc() are both used for dynamic memory allocation, but calloc initializes the memory to zero and is generally used for allocating arrays of data, while malloc() is faster and used for allocating single blocks of data.

## Activity Problems
1. [Give the most appropriate pair](https://www.geeksforgeeks.org/questions/c-dynamic-memory-allocation-question-1/)
2. [Guess Output 1](https://www.geeksforgeeks.org/questions/c-dynamic-memory-allocation-question-3/)
3. [Guess Output 2](https://www.geeksforgeeks.org/questions/c-dynamic-memory-allocation-question-2/)
4. [Sparse Arrays](https://www.hackerrank.com/challenges/sparse-arrays/problem)