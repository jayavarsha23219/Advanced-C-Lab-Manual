## EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
### Aim:
To write a C program to display stack elements using linked list.

### Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
### Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
} *top = NULL;

void push(int val) {
    struct Node* n = malloc(sizeof(struct Node));
    n->data = val;
    n->next = top;
    top = n;
}

void pop() {
    if (!top) return;
    struct Node* temp = top;
    top = top->next;
    free(temp);
}

void display() {
    struct Node* temp = top;
    while (temp) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main() {
    push(10); push(20); push(30);
    printf("Stack:\n"); display();
    pop();
    printf("After pop:\n"); display();
    return 0;
}
 
```
### Output:
![Screenshot 2025-05-15 000236](https://github.com/user-attachments/assets/b1eefe5e-6410-4d90-b151-cd19e1e014e4)

### Result:
Thus, the program to display stack elements using linked list is verified successfully. 

-------------------------------------------------------------------------------------------------------------------------

## EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.
### Aim:
To write a C program to pop an element from the given stack using liked list.

### Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
### Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
} *top = NULL;

void push(int val) {
    struct Node* n = malloc(sizeof(struct Node));
    n->data = val;
    n->next = top;
    top = n;
}

void pop() {
    if (!top) {
        printf("Stack Underflow\n");
        return;
    }
    printf("Popped: %d\n", top->data);
    struct Node* temp = top;
    top = top->next;
    free(temp);
}

int main() {
    push(10); push(20); push(30);
    pop(); // Pops 30
    return 0;
}

```
### Output:
![Screenshot 2025-05-15 000419](https://github.com/user-attachments/assets/1ab6bc74-88b8-40e7-bce3-ac0b8a14b3b3)


### Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

-----------------------------------------------------------------------------------------------------------------

## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
### Aim:
To write a C program to display queue elements using linked list.
### Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
### Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
} *front = NULL, *rear = NULL;

void enqueue(int val) {
    struct Node* n = malloc(sizeof(struct Node));
    n->data = val; n->next = NULL;
    if (!rear) front = rear = n;
    else rear->next = n, rear = n;
}

void display() {
    struct Node* temp = front;
    while (temp) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main() {
    enqueue(10); enqueue(20); enqueue(30);
    printf("Queue:\n"); display();
    return 0;
}

```
### Output:
![Screenshot 2025-05-15 000544](https://github.com/user-attachments/assets/58be0b6d-b3d3-4e5e-8a23-2ae0ba415818)


### Result:
Thus, the program to display queue elements using linked list is verified successfully.

--------------------------------------------------------------------------------------------------------------------------------
 
## EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

### Aim:
To write a C program to insert elements in queue using linked list

### Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
### Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
} *front = NULL, *rear = NULL;

void enqueue(int val) {
    struct Node* n = malloc(sizeof(struct Node));
    n->data = val; n->next = NULL;
    if (!rear) front = rear = n;
    else rear->next = n, rear = n;
    printf("Inserted: %d\n", val);
}

int main() {
    enqueue(5);
    enqueue(15);
    enqueue(25);
    return 0;
}

```
### Output:
![Screenshot 2025-05-15 000714](https://github.com/user-attachments/assets/e056d439-4804-4f97-be55-80bf3515b875)


### Result:
Thus, the program to insert elements in queue using linked list is verified successfully.

----------------------------------------------------------------------------------------------------------------------------------

## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


### Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

### Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

### Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
} *front = NULL, *rear = NULL;

void enqueue(int val) {
    struct Node* n = malloc(sizeof(struct Node));
    n->data = val; n->next = NULL;
    if (!rear) front = rear = n;
    else rear->next = n, rear = n;
}

void peek() {
    if (!front) printf("Queue is empty\n");
    else printf("Front element: %d\n", front->data);
}

int main() {
    enqueue(10);
    enqueue(20);
    peek();  // Should print 10
    return 0;
}

```
### Output:
![Screenshot 2025-05-15 000814](https://github.com/user-attachments/assets/44c9a6fe-d631-4172-b71c-22180e8b43c6)


### Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


