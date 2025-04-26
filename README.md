# Advanced-C-Lab-Manual
## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:

Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0

## Program:
```
#include <stdio.h>
#define MAX_PEOPLE 100
struct Person {
    char name[50];
    int age;
};
int main() {
    struct Person people[MAX_PEOPLE];
    int n, i;

    printf("Enter the number of people: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++) {
        printf("\nEnter details for person %d:\n", i+1);
        printf("Name: ");
        scanf(" %[^\n]%*c", people[i].name); // To read string with spaces
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    printf("\nEligibility for vaccination:\n");
    for(i = 0; i < n; i++) {
        printf("%s (%d years old): ", people[i].name, people[i].age);
        if(people[i].age >= 18) {
            printf("Eligible\n");
        } else {
            printf("Not Eligible\n");
        }
    }

    return 0;
}
```
## Output:

![Screenshot 2025-04-26 102920](https://github.com/user-attachments/assets/13a91fa2-b5a8-411f-874a-1ee92af0256c)


## Result: 
Thus, the program is verified successfully.

---------------------------------------------------------------------------------------------------------------------------

## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION 

## Aim:
To write a C program for passing structure as function and returning a structure from a function

## Algorithm:

Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0

## Program:
```
#include <stdio.h>
struct Student {
    char name[50];
    int marks1;
    int marks2;
    int total;
};
struct Student calculateTotal(struct Student s) {
    s.total = s.marks1 + s.marks2;
    return s;  // returning a structure
}
void displayStudent(struct Student s) {
    printf("\nStudent Name: %s", s.name);
    printf("\nMarks 1: %d", s.marks1);
    printf("\nMarks 2: %d", s.marks2);
    printf("\nTotal Marks: %d\n", s.total);
}
int main() {
    struct Student s1;
    printf("Enter student name: ");
    scanf(" %[^\n]%*c", s1.name);

    printf("Enter marks for subject 1: ");
    scanf("%d", &s1.marks1);

    printf("Enter marks for subject 2: ");
    scanf("%d", &s1.marks2);
    s1 = calculateTotal(s1);
    displayStudent(s1);

    return 0;
}
```
## Output:
![Screenshot 2025-04-26 103209](https://github.com/user-attachments/assets/0eb91b22-dc01-4526-a46f-7f2afba6f204)


## Result:
Thus, the program is verified successfully

-------------------------------------------------------------------------------------------------------------------------

## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

## Aim:
To write a C program to read a file name from user

## Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.

## Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    char text[1000];
    FILE *fp;

    // Read the file name
    printf("Enter the file name to create/write: ");
    scanf("%s", filename);

    // Open the file in write mode
    fp = fopen(filename, "w");
    
    if (fp == NULL) {
        printf("Error opening file!\n");
        return 1;
    }

    // Get text from user
    printf("Enter text to write to the file (end with ~ on a new line):\n");

    // Clear input buffer
    getchar();

    // Read multiple lines until user enters '~'
    while (1) {
        fgets(text, sizeof(text), stdin);
        if (text[0] == '~') break;
        fputs(text, fp);
    }

    // Close the file
    fclose(fp);

    printf("Data written successfully to '%s'.\n", filename);
    return 0;
}

```
## Output:

![Screenshot 2025-04-26 103756](https://github.com/user-attachments/assets/6a3d98b0-a2b8-47c0-8097-22ca6a6ce753)


## Result:
Thus, the program is verified successfully

-------------------------------------------------------------------------------------------------------------------

## EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 

## Aim:
To write a C program to read, a file and insert text in that file Algorithm:

## Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.

Program:
```
#include <stdio.h>
int main() {
    char filename[100];
    char text[1000];
    FILE *fp;
    printf("Enter the file name: ");
    scanf("%s", filename);
    fp = fopen(filename, "a");
    printf("Enter text to insert into the file (type ~ on a new line to finish):\n");
    getchar();

    while (1) {
        fgets(text, sizeof(text), stdin);
        if (text[0] == '~') break;
        fputs(text, fp);
    }
    fclose(fp);
    printf("Text inserted successfully into '%s'.\n", filename);

    return 0;
}
```
## Output:
![WhatsApp Image 2025-04-26 at 10 45 30_800ec98d](https://github.com/user-attachments/assets/9ef75d4a-d7dd-42a3-a827-c0882faee8f2)


## Result: 
Thus, the program is verified successfully

--------------------------------------------------------------------------------------------------------------------------------------------

## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

## Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

## Algorithm:

1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

## Program:
```
#include <stdio.h>
struct Student {
    char name[50];
    int roll;
    float marks;
};

int main() {
    struct Student s;
    printf("Enter student name: ");
    scanf(" %[^\n]%*c", s.name); 
    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\n--- Student Details ---\n");
    printf("Name       : %s\n", s.name);
    printf("Roll No.   : %d\n", s.roll);
    printf("Marks      : %.2f\n", s.marks);

    return 0;
}
```
## Output:
![Screenshot 2025-04-26 104813](https://github.com/user-attachments/assets/f0f9e68f-5cc4-4c34-a260-2a4a20379c42)


## Result:
Thus, the program is verified successfully
