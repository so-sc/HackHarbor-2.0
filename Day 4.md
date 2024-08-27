---
day: 4
title: "Arrays in C"
description: "Covering Single-dimensional Arrays, Accessing Elements, and Basic Operations"
---

# Day 4 - Arrays in C

## Introduction to Arrays

### What is an Array?
An array is a collection of elements of the same data type stored in contiguous memory locations.

### Single-dimensional Arrays
A single-dimensional array is an array with only one row or column.
```c
int arr[5]; // Declare an array of 5 integers
```

### Accessing Elements
Elements in an array can be accessed using their index.
```c
int arr[5] = {1, 2, 3, 4, 5};
printf("%d", arr[0]); // Access the first element
```

## Basic Operations

### Initialization
Arrays can be initialized with values when they are declared.
```c
int arr[5] = {1, 2, 3, 4, 5};
```

### Assignment
Values can be assigned to individual elements of an array.
```c
int arr[5];
arr[0] = 10;
arr[1] = 20;
```

### Reading and Writing
Arrays can be read and written using loops.
```c
int arr[5];
for (int i = 0; i < 5; i++) {
    scanf("%d", &arr[i]);
}
for (int i = 0; i < 5; i++) {
    printf("%d ", arr[i]);
}
```

### Example
```c
#include <stdio.h>

int main() {
    int arr[5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

## 2D Arrays

### Declaration
A 2D array is declared with two sets of square brackets.
```c
int arr[3][4]; // Declare a 2D array with 3 rows and 4 columns
```

### Initialization
2D arrays can be initialized with values when they are declared, as an array inside an array.
```c
int arr[3][4] = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};
```

### Accessing Elements
Elements in a 2D array can be accessed using their row and column indices.
```c
int arr[3][4] = {{1, 2, 3, 4},
                {5, 6, 7, 8},
                {9, 10, 11, 12}};
printf("%d", arr[1][2]); // Access the element at row 1, column 2
```

## Multidimensional Arrays

### Declaration
A multidimensional array is declared with multiple sets of square brackets.
```c
int arr[2][3][4]; // Declare a 3D array with 2 layers, 3 rows, and 4 columns
```

### Initialization
Multidimensional arrays can be initialized with values when they are declared, using multiple pairs of corresponding braces.
```c
int arr[2][3][4] = {
                    {
                     {1, 2, 3, 4},
                     {5, 6, 7, 8},
                     {9, 10, 11, 12}
                    },
                    {
                     {13, 14, 15, 16},
                     {17, 18, 19, 20},
                     {21, 22, 23, 24}
                    }
                   };
```

### Accessing Elements
Elements in a multidimensional array can be accessed using their layer, row, and column indices.
```c
int arr[2][3][4] = {{{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}}, {{13, 14, 15, 16}, {17, 18, 19, 20}, {21, 22, 23, 24}}};
printf("%d", arr[1][2][3]); // Access the element at layer 1, row 2, column 3
```

### Example
```c
#include <stdio.h>

int main() {
    int arr[3][4] = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```