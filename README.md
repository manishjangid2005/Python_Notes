# DSA Notes

## Unit -1 Introduction

### ADT - Abstract data type 
Data type which are used to solve real life problems where user is only aware about the options or operations available to use and unaware about how those operations are taking place.

### Asymptotic Notations

* Asymptotic Notations are mathematical representation used to describe the time complexity (or space complexity) of an algorithm

* Types of Asymptotic Notations
    1. Big O Notation (O): Describes the worst-case time complexity.
    2. Big Omega Notation (Ω): Describes the best-case time complexity.
    3. Theta Notation (Θ): Describes the average-case or tight bound time complexity.

### Types of Data Structures

* Primitive DS - int, float, char, pointer

1. Linear Data Structures:
    * Arrays
    * Linked Lists 
    * Stacks
    * Queues 

2. Non-Linear Data Structures:
    * Trees
    * Graphs 

### Sorting Algorithms

1. Insertion Sort
    * Best -  O(n)
    * Average - O(n^2)
    * Worst - O(n^2)
2. Quick sort
    * Best -  O(nlogn)
    * Average - O(nlogn)
    * Worst - O(n^2)
3. Merge sort
    * Best -  O(nlogn)
    * Average - O(nlogn)
    * Worst - O(nlogn)

### Insertion Sort Algorithm:
* Step 1: Start with the second element in the array (consider the first element as a sorted sub-array of one element).
* Step 2: Compare the current element with the elements in the sorted sub-array (left side) and find its correct position.
* Step 3: Shift all larger elements one position to the right to make space for the current element.
* Step 4: Insert the element into its correct position in the sorted sub-array.
* Step 5: Move to the next element and repeat the process until the entire array is sorted.

### Quick Sort Algorithm:
* Step 1: Choose a pivot element (can be the first, last, or middle element, or chosen randomly).
* Step 2: Partition the array: Rearrange the elements so that all elements smaller than the pivot are on its left and all elements larger than the pivot are on its right.
* Step 3: Recursively apply the partitioning to the sub-arrays on the left and right of the pivot.
* Step 4: Base case: If the sub-array has one or zero elements, it is already sorted.
* Step 5: Continue the recursive process until all sub-arrays are sorted, and the full array is sorted.

###  Merge Sort Algorithm:
* Step 1: Divide the array into two halves until each sub-array contains only a single element (i.e., divide recursively).
* Step 2: Once the sub-arrays contain a single element, start merging them back.
* Step 3: During the merge process, combine the sub-arrays by comparing their elements and sorting them in order.
* Step 4: Continue merging and sorting the sub-arrays until the entire array is sorted.
* Step 5: The array is now fully sorted after all sub-arrays have been merged.



### Static Memory Allocation
* Memory is allocated at compile time and cannot be changed during runtime.
* The size of memory is fixed once the program starts.
* The memory is allocated on the stack.

### Dynamic Memory Allocation
* Memory is allocated at runtime using dynamic memory functions.
* The size of memory can be changed during execution.
* The memory is allocated on the heap.
* More flexible as you can allocate memory as needed, but it's less efficient than static allocation due to manual management.

### Functions
* malloc() -  allocates a block of memory of a given size at runtime, but the memory is uninitialized, meaning it contains garbage values. 
* calloc() - also allocates memory but initializes all elements to zero, making it ideal for arrays. 
* realloc() - is used to resize a previously allocated memory block, either expanding or shrinking the memory while preserving the existing data. 
* free() - releases the memory previously allocated with malloc(), calloc(), or realloc() to avoid memory leaks.


## Unit -2 Linked List
* A linked list is a linear data structure that consists of a series of nodes connected by pointers
* Each node contains data and a pointer to the next node in the list. 
* Time complexity O(n) at begining ans O(n) at any position
* Searching, reversing O(n)

![](https://media.geeksforgeeks.org/wp-content/uploads/20220712172013/Singlelinkedlist.png)

### Algorithm to create and traverse node

1. Step 1: Define a struct node with:
    * data: to store the value of the node.
    * link: a pointer to the next node in the list

2. Step 2: In the main() function:
    * Allocate memory for n nodes using malloc().

3. Step 3: For each node, starting from the first:
    * Assign a value to the node’s data field.
    * Set the node’s link pointer to point to the next node (if it exists).

4. Step 4: For the last node:
    * Assign its link pointer to NULL to mark the end of the linked list.

5. Step 5: Traverse the linked list:
    * Start from the head node.
    * While the current node is not NULL, print the data of the current node.
    * Move to the next node by setting the current node to its link.

6. Step 6: Continue traversing until all nodes are visited and printed, then terminate the program.

```c
#include<stdio.h>
#include<stdlib.h>

struct node{
    int data;
    struct node *link;
};

int main(){
    // Allocate memory for three nodes in the linked list
    struct node *head = malloc(sizeof(struct node));
    struct node *second = malloc(sizeof(struct node));
    struct node *third = malloc(sizeof(struct node));

    // Assign data to the first node and link it to the second node
    head->data = 45;
    head->link = second;

    // Assign data to the second node and link it to the third node
    second->data = 98;
    second->link = third; 

    // Assign data to the third node and terminate the list by setting the next to NULL
    third->data = 3;
    third->link = NULL;

    // Traverse the linked list and print the data of each node
    struct node* current = head;
    while (current != NULL) {
        printf("Node data: %d\n", current->data);
        current = current->link;
    }

    return 0;
}
```

### Insert at Beginning:
* Set the new node’s link to point to the current head.
* Update the head to point to the new node.

### Insert at End:
* Traverse the linked list until you find the last node (where link is NULL).
* Set the last node’s link to point to the new node.

### Insert at a Specific Position:
* Traverse to the node just before the desired position.
* Set the new node’s link to the link of the previous node.
* Set the previous node’s link to point to the new node.

## Doubly linked list

![](https://media.geeksforgeeks.org/wp-content/uploads/20240809123741/Insertion-at-the-End-in-Doubly-Linked-List-copy.webp)

* Doubly linked list is a data structure consisting of nodes, where each node contains three fields:
    1. A pointer to the previous node.
    1. A data field.
    1. A pointer to the next node.
* This allows traversal in both directions—forward and backward.

### Inserting at the Beginning
1. Create a new node.
2. Set the new node's next pointer to the current head.
3. Set the new node's previous pointer to NULL.
4. If the current head is not NULL, set the current head's previous pointer to the new node.
5. Update the head to point to the new node.

### Inserting at the End
1. Create a new node.
2. If the list is empty, set the head to the new node.
3. Otherwise, traverse to the last node.
4. Set the last node's next pointer to the new node.
5. Set the new node's previous pointer to the last node.

### Inserting at a Specific Position
1. Create a new node.
2. If the position is 0, call the function to insert at the beginning.
3. Otherwise, traverse to the node just before the desired position.
4. If the current node is NULL, the position is out of bounds.
5. Set the new node's next pointer to the current node's next pointer.
6. Set the new node's previous pointer to the current node.
7. If the next node is not NULL, set its previous pointer to the new node.
8. Set the current node's next pointer to the new node.


## Unit -3 Stacks 

1. In the array implementation of a stack, a fixed-size array is used to hold the stack elements. The stack follows the LIFO (Last In, First Out) principle, meaning that the last element added to the stack is the first one to be removed.

2. Components of Array-Based Stack:
* Array: The stack is represented using an array of a fixed size. This array will store the stack elements.
* Top Pointer: A variable, often called top, is used to keep track of the index of the top element in the stack.
Initially, the top is set to -1, indicating the stack is empty.

### Overflow and Underflow
* Stack overflow:
The condition resulting from trying to push an element onto a full stack.
* Stack underflow:
The condition resulting from trying to pop an empty stack.


## Algorithm to Push()
* Step 1 − Checks if the stack is full.
* Step 2 − If the stack is full, produces an error and exit.
* Step 3 − If the stack is not full, increments top to point next empty space.
* Step 4 − Adds data element to the stack location, where top is pointing.
* Step 5 − Returns success.

## Algorithm to Pop()
* Step 1 − Checks if the stack is empty.
* Step 2 − If the stack is empty, produces an error and exit.
* Step 3 − If the stack is not empty, accesses the data element at which top is
pointing.
* Step 4 − Decreases the value of top by 1.
* Step 5 − Returns success.

```c
#include <stdio.h>
#include <ctype.h>

#define MAX 5

int stack[MAX];
int top = -1;

int isfull() {
    if(top == MAX-1)
        return 1;
    else
        return 0;
}

int isempty() {
    if(top == -1)
        return 1;
    else
        return 0;
}

void push(int data) {
    if(!isfull()) {
        top = top + 1;
        stack[top] = data;
    }
    else {
        printf("Could not insert data, Stack is full.\n");
    }
}

int pop() {
    int data;
    if(!isempty()) {
        data = stack[top];
        top = top - 1;
        return data;
    }
    else {
        printf("Could not retrieve data, Stack is empty.\n");
    }
}

int main(){
    push(3);
    push(5);
    push(9);
    push(1);
    pop();
    push(12);

    while(!isempty()) {
        int data = pop();
        printf("%d\n",data);
    }

    return 0;
}
```
## Algorithm for infix to postfix

1. Initialize an empty stack for operators and an empty string for the postfix expression.
2. Scan the infix expression from left to right:
* If the scanned character is an operand, append it to the postfix expression.
* If the scanned character is '('(left parenthesis), push it to the stack.
* If the scanned character is ')'(right parenthesis), pop and append operators from the stack to the postfix expression until a '(' is encountered. Remove the '(' from the stack.
3. If the scanned character is an operator:
* While there is an operator at the top of the stack with greater or equal precedence, pop it and append to the postfix expression.
* Push the current operator to the stack.
4. After scanning the expression, pop all the operators from the stack and append them to the postfix expression.
5. End.
