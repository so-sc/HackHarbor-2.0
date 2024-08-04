---
day: 9
title: "Linked Lists"
description: "Covering Singly Linked Lists, Doubly Linked Lists, and Circular Linked Lists"
---

# Day 9 - Linked Lists

## Singly Linked Lists

![SLL](https://miro.medium.com/v2/resize:fit:953/1*iiEWrP2IznA6HbmuIdK0lQ.png "Singly Linked Lists")

### Implementation
A singly linked list consists of nodes, each containing data and a pointer to the next node.
```c
struct Node {
    int data;
    struct Node* next;
};
```

### Insertion
Insertion can be done at the beginning, end, or at a specific position.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = head;
    return newNode;
}
```

### Deletion
Deletion can be done from the beginning, end, or at a specific position.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    struct Node* temp = head;
    head = head->next;
    free(temp);
    return head;
}
```

### Traversal
Traversal involves visiting each node in the list.
```c
void traverse(struct Node* head) {
    struct Node* current = head;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
}
```

## Doubly Linked Lists

![DLL](https://www.sanfoundry.com/wp-content/uploads/2013/05/circular-doubly-linked-list-example.png "Doubly Linked Lists")

### Implementation
A doubly linked list has nodes with pointers to both the next and previous nodes.
```c
struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};
```

### Insertion
Insertion in a doubly linked list requires updating both next and prev pointers.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = head;
    if (head != NULL) head->prev = newNode;
    return newNode;
}
```

### Deletion
Deletion in a doubly linked list involves updating both next and prev pointers.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    struct Node* temp = head;
    head = head->next;
    if (head != NULL) head->prev = NULL;
    free(temp);
    return head;
}
```

### Traversal
Traversal can be done in both forward and backward directions.
```c
void traverseForward(struct Node* head) {
    struct Node* current = head;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
}

void traverseBackward(struct Node* tail) {
    struct Node* current = tail;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->prev;
    }
}
```

## Circular Linked Lists

![CLL](https://examradar.com/wp-content/uploads/2016/10/Figure-3.6.1.-Circular-Single-Linked-List.png "Circular Linked Lists")

### Implementation
A circular linked list connects the last node back to the first node.
```c
struct Node {
    int data;
    struct Node* next;
};
```

### Insertion
Insertion in a circular linked list requires special handling for the last node.
```c
// Insert at the beginning
struct Node* insertAtBeginning(struct Node* head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    if (head == NULL) {
        newNode->next = newNode;
        return newNode;
    }
    newNode->next = head;
    struct Node* current = head;
    while (current->next != head) {
        current = current->next;
    }
    current->next = newNode;
    return newNode;
}
```

### Deletion
Deletion in a circular linked list requires updating the last node's next pointer.
```c
// Delete from the beginning
struct Node* deleteFromBeginning(struct Node* head) {
    if (head == NULL) return NULL;
    if (head->next == head) {
        free(head);
        return NULL;
    }
    struct Node* current = head;
    while (current->next != head) {
        current = current->next;
    }
    struct Node* temp = head;
    head = head->next;
    current->next = head;
    free(temp);
    return head;
}
```

### Traversal
Traversal in a circular linked list requires stopping when we reach the first node again.
```c
void traverse(struct Node* head) {
    if (head == NULL) return;
    struct Node* current = head;
    do {
        printf("%d ", current->data);
        current = current->next;
    } while (current != head);
}
```

## Example
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node* head = createNode(1);
    head->next = createNode(2);
    head->next->next = createNode(3);
    
    struct Node* current = head;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    
    return 0;
}
```

## Activity Problems
