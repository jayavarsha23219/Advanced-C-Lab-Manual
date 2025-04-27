# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.

## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```
#include <stdio.h>
#define MAX 5

int stack[MAX];
int top = -1;

void push(int val) {
    if (top == MAX - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = val;
}

void display() {
    if (top == -1)
        printf("Stack is empty\n");
    else {
        printf("Stack elements:\n");
        for (int i = top; i >= 0; i--)
            printf("%d\n", stack[i]);
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    return 0;
}

```
## Output:

![Screenshot 2025-04-27 082030](https://github.com/user-attachments/assets/e59089ef-44d8-4850-9aa0-e3879bb36796)



## Result:
Thus, the program to display stack elements using an array is verified successfully.
 
-------------------------------------------------------------------------------------------------
# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.

## Aim:
To create a C program to push the given element in to a stack using array.

## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```
#include <stdio.h>
#define MAX 5

int stack[MAX], top = -1;

void push(int val) {
    if (top == MAX - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = val;
}

int main() {
    int val;
    printf("Enter value to push: ");
    scanf("%d", &val);
    push(val);
    printf("Element pushed: %d\n", val);
    return 0;
}

```
## Output:
![Screenshot 2025-04-27 082156](https://github.com/user-attachments/assets/5afcef08-6de2-41e4-b3e5-d1a6e9ff78f3)


## Result:
Thus, the program to push the given element in to a stack using array is verified successfully

-----------------------------------------------------------------------------------------------------------------------
 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```
#include <stdio.h>
#define MAX 5

int queue[MAX], front = -1, rear = -1;

void enqueue(int val) {
    if (rear == MAX - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1) front = 0;
        queue[++rear] = val;
    }
}

void display() {
    if (front == -1 || front > rear)
        printf("Queue is empty\n");
    else {
        printf("Queue elements:\n");
        for (int i = front; i <= rear; i++)
            printf("%d\n", queue[i]);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}

```
## Output:
![Screenshot 2025-04-27 082338](https://github.com/user-attachments/assets/214e07cf-ed03-4065-842e-d4c138506a8f)


## Result:
Thus, the program to display queue elements using array is verified successfully.

-----------------------------------------------------------------------------------------------------------------------------
 
## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```
#include <stdio.h>
#define MAX 5

int queue[MAX], front = -1, rear = -1;

void enqueue(int val) {
    if (rear == MAX - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1) front = 0;
        queue[++rear] = val;
    }
}

int main() {
    int val;
    printf("Enter value to insert: ");
    scanf("%d", &val);
    enqueue(val);
    printf("Element inserted: %d\n", val);
    return 0;
}

```
## Output:

![Screenshot 2025-04-27 082446](https://github.com/user-attachments/assets/300cbfbe-95b2-4970-95bd-63d75068c260)


## Result:
Thus, the program to insert elements in queue using array is verified successfully.


-----------------------------------------------------------------------------------------------------------------------------------------------
 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim:
To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:
```
#include <stdio.h>
#define MAX 5

int queue[MAX], front = -1, rear = -1;

void dequeue() {
    if (front == -1 || front > rear)
        printf("Queue Underflow\n");
    else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
    }
}

int main() {
    // Example setup
    queue[0] = 10; queue[1] = 20; queue[2] = 30;
    front = 0; rear = 2;

    dequeue();
    return 0;
}
```
## Output:
![Screenshot 2025-04-27 082707](https://github.com/user-attachments/assets/178a0a94-ad38-4db4-92ee-22d68def6a4a)


## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
