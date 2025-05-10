## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
### Aim:
To write a C program to create a function to find the greatest number

### Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
### Program:
```
#include <stdio.h>

int findGreatest(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max)
            max = arr[i];
    }
    return max;
}

int main() {
    int n;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter %d numbers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    int greatest = findGreatest(arr, n);
    printf("The greatest number is: %d\n", greatest);

    return 0;
}
```
### Output:
![Screenshot 2025-05-10 202755](https://github.com/user-attachments/assets/f56fe701-d0c9-407b-a1f7-91926c8e825d)


### Result:
Thus, the program  that create a function to find the greatest number is verified successfully.

-----------------------------------------------------------------------------------------------------------------------------
 
## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
### Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

### Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
### Program:
```
#include <stdio.h>


void findMaxBitwise(int n, int k) {
    int maxAND = 0, maxOR = 0, maxXOR = 0;

    for (int a = 1; a < n; a++) {
        for (int b = a + 1; b <= n; b++) {
            int and = a & b;
            int or = a | b;
            int xor = a ^ b;

            if (and < k && and > maxAND)
                maxAND = and;
            if (or < k && or > maxOR)
                maxOR = or;
            if (xor < k && xor > maxXOR)
                maxXOR = xor;
        }
    }

    printf("Maximum AND less than %d: %d\n", k, maxAND);
    printf("Maximum OR  less than %d: %d\n", k, maxOR);
    printf("Maximum XOR less than %d: %d\n", k, maxXOR);
}

int main() {
    int n, k;

    printf("Enter the value of n: ");
    scanf("%d", &n);

    printf("Enter the value of k: ");
    scanf("%d", &k);

    findMaxBitwise(n, k);

    return 0;
}
```

### Output:
![Screenshot 2025-05-10 203038](https://github.com/user-attachments/assets/301c7b46-2e2a-4bac-bdfc-50a7eb5706c4)


### Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.

-------------------------------------------------------------------------------------------------------------------------------
 
## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
### Aim:
To write a C program to write the logic for the requests

### Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
### Program:
```
#include <stdio.h>
#include <stdlib.h>

// Node structure
struct Node {
    int data;
    struct Node* next;
};

// Insert at end
void insertEnd(struct Node** head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

// Search for a value
void search(struct Node* head, int key) {
    int pos = 1;
    while (head != NULL) {
        if (head->data == key) {
            printf("Element %d found at position %d\n", key, pos);
            return;
        }
        head = head->next;
        pos++;
    }
    printf("Element %d not found\n", key);
}

// Delete a value
void deleteValue(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted\n", key);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted\n", key);
}

// Display the list
void display(struct Node* head) {
    printf("List: ");
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Main logic handler
int main() {
    struct Node* head = NULL;
    int choice, value;

    while (1) {
        printf("\n--- MENU ---\n");
        printf("1. Insert\n2. Search\n3. Delete\n4. Display\n5. Exit\n");
        printf("Enter your request: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                insertEnd(&head, value);
                break;
            case 2:
                printf("Enter value to search: ");
                scanf("%d", &value);
                search(head, value);
                break;
            case 3:
                printf("Enter value to delete: ");
                scanf("%d", &value);
                deleteValue(&head, value);
                break;
            case 4:
                display(head);
                break;
            case 5:
                printf("Exiting...\n");
                exit(0);
            default:
                printf("Invalid request.\n");
        }
    }

    return 0;
}
```

### Output:
![Screenshot 2025-05-10 203427](https://github.com/user-attachments/assets/7fbe03ff-3c59-4d15-98db-29b2abbadf8f)


### Result:
Thus, the program to write the logic for the requests is verified successfully.

--------------------------------------------------------------------------------------------------------------------------------
 
## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
### Aim:
To write a C program print the sum of the integers in the array.

### Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



### Program:
```
#include <stdio.h>

int main() {
    int n, i, sum = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];

    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];  // Add each element to sum
    }

    printf("Sum of the array elements is: %d\n", sum);

    return 0;
}
```
### Output:
![Screenshot 2025-05-10 203646](https://github.com/user-attachments/assets/a36a81ae-86d7-430e-81be-5addc4def389)


### Result:
Thus, the program prints the sum of the integers in the array is verified successfully.

---------------------------------------------------------------------------------------------------------------------------
 
## EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A  SENTENCE



### Aim:

To write a C program that counts the number of words in a given sentence.

### Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



### Program:
```
#include <stdio.h>
#include <ctype.h>

int countWords(char *sentence) {
    int count = 0, i = 0;
    int inWord = 0; 

    while (sentence[i] != '\0') {
        if (isspace(sentence[i]) || sentence[i] == '\0') {
            inWord = 0; 
        } else if (!inWord) {
            inWord = 1;  
            count++; 
        }
        i++;
    }
    return count;
}

int main() {
    char sentence[1000];

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin); 
    int wordCount = countWords(sentence);
    printf("Number of words in the sentence: %d\n", wordCount);
    return 0;
}
```

### Output:
![Screenshot 2025-05-10 203901](https://github.com/user-attachments/assets/5968d092-68c8-49b6-86b7-288a7d8065e2)


### Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
