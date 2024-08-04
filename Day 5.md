---
day: 5
title: "Refresher to C programming"
description: "Strings and Pointers"
---

# Day 5 - Strings and Pointers in C

## Strings in C

### String Handling Functions
Strings in C are arrays of characters terminated by a null character (`\0`).

### Array of Characters
To declare and initialize a string:
```c
char str[] = "Hello, World!";
```
Or:
```c
char str[50] = "Hello, World!";
```

### Standard Library Functions

#### `strlen`
Calculates the length of a string.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello, World!";
    printf("Length: %zu\n", strlen(str));
    return 0;
}
```

#### `strcpy`
Copies one string to another.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char src[] = "Hello, World!";
    char dest[50];
    strcpy(dest, src);
    printf("Copied String: %s\n", dest);
    return 0;
}
```

#### `strcmp`
Compares two strings.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "Hello";
    char str2[] = "World";
    int result = strcmp(str1, str2);
    if(result == 0) {
        printf("Strings are equal\n");
    } else {
        printf("Strings are not equal\n");
    }
    return 0;
}
```

#### `strcat`
Concatenates two strings.
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[50] = "Hello";
    char str2[] = ", World!";
    strcat(str1, str2);
    printf("Concatenated String: %s\n", str1);
    return 0;
}
```

## Pointers

### Definition
A pointer is a variable that stores the memory address of another variable.

### Declaration
To declare a pointer:
```c
int *ptr;
```

### Usage
Pointers are used to store and manage the addresses of other variables.

### Example
```c
#include <stdio.h>

int main() {
    int var = 10;
    int *ptr = &var;

    printf("Value of var: %d\n", var);
    printf("Address of var: %p\n", &var);
    printf("Value stored in ptr: %p\n", ptr);
    printf("Value pointed to by ptr: %d\n", *ptr);

    return 0;
}
```

### Pointer Arithmetic
You can perform arithmetic operations on pointers to navigate through an array.

### Example
```c
#include <stdio.h>

int main() {
    int arr[] = {10, 20, 30, 40, 50};
    int *ptr = arr;

    for(int i = 0; i < 5; i++) {
        printf("Value at ptr[%d]: %d\n", i, *(ptr + i));
    }

    return 0;
}
```

### Pointers and Arrays
Pointers can be used to manipulate arrays.

### Example
```c
#include <stdio.h>

void printArray(int *arr, int size) {
    for(int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int size = sizeof(arr) / sizeof(arr[0]);

    printArray(arr, size);

    return 0;
}
```

### Pointers to Pointers
A pointer to a pointer is a form of multiple indirection, or a chain of pointers.

### Example
```c
#include <stdio.h>

int main() {
    int var = 10;
    int *ptr = &var;
    int **pptr = &ptr;

    printf("Value of var: %d\n", var);
    printf("Value pointed to by ptr: %d\n", *ptr);
    printf("Value pointed to by pptr: %d\n", **pptr);

    return 0;
}
```

## Activity Problems  
<!-- TODO -->
