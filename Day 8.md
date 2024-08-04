---
day: 8
title: "File Operations"
description: "Covering File Operations, File Modes, Error Handling, and Standard Library Functions for File Handling"
---

# Day 8 - File Operations

## File Operations

### Opening a File
A file can be opened using the `fopen` function, which returns a file pointer.
```c
FILE* fp = fopen("example.txt", "r");
```

### Reading from a File
Data can be read from a file using the fread function.
```c
char buffer[100];
fread(buffer, sizeof(char), 100, fp);
```

### Writing to a File
Data can be written to a file using the fwrite function.
```c
char* data = "Hello, World!";
fwrite(data, sizeof(char), strlen(data), fp);
```

### Closing a File
A file can be closed using the fclose function.
```c
fclose(fp);
```

## File Modes

### Text Mode
In text mode, files are opened in a way that allows for reading and writing text data.
```c
FILE* fp = fopen("example.txt", "r");
```

### Binary Mode
In binary mode, files are opened in a way that allows for reading and writing binary data.
```c
FILE* fp = fopen("example.bin", "rb");
```

## Error Handling in File Operations

### Checking for Errors
Errors can be checked using the ferror function.
```c
if (ferror(fp)) {
    printf("Error occurred while reading file\n");
}
```

### Handling Errors
Errors can be handled using the perror function.
```c
if (fopen("example.txt", "r") == NULL) {
    perror("Error opening file");
}
```

## Standard Library Functions for File Handling

### fopen
Opens a file and returns a file pointer.
```c
FILE* fp = fopen("example.txt", "r");
```

### fclose
Closes a file.
```c
fclose(fp);
```

### fread
Reads data from a file.
```c
char buffer[100];
fread(buffer, sizeof(char), 100, fp);
```

### fwrite
Writes data to a file.
```c
char* data = "Hello, World!";
fwrite(data, sizeof(char), strlen(data), fp);
```

### fseek
Moves the file pointer to a specified location.
```c
fseek(fp, 10, SEEK_SET);
```

### ftell
Returns the current position of the file pointer.
```c
long pos = ftell(fp);
```

### rewind
Moves the file pointer to the beginning of the file.
```c
rewind(fp);
```

### Example
```c
#include <stdio.h>

int main() {
    FILE* fp = fopen("example.txt", "w");
    if (fp == NULL) {
        perror("Error opening file");
        return 1;
    }
    char* data = "Hello, World!";
    fwrite(data, sizeof(char), strlen(data), fp);
    fclose(fp);
    return 0;
}
```

## Activity Problems
