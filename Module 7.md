EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
#include <string.h>
struct Person {
    char name[50];
    int age;
    char gender[10];
};

void checkEligibility(struct Person p) {
    if (p.age >= 18) {
        printf("%s is eligible for the vaccine.\n", p.name);
    } else {
        printf("%s is not eligible for the vaccine.\n", p.name);
    }
}

int main() {
    int n;
    printf("Enter the number of people: ");
    scanf("%d", &n);
    
    struct Person people[n];

    for (int i = 0; i < n; i++) {
        printf("\nEnter details for person %d\n", i + 1);
        printf("Enter name: ");
        scanf(" %[^\n]s", people[i].name); 
        printf("Enter age: ");
        scanf("%d", &people[i].age);
        printf("Enter gender: ");
        scanf("%s", people[i].gender);
    }

    for (int i = 0; i < n; i++) {
        checkEligibility(people[i]);
    }

    return 0;
}
```
Output:

![Screenshot 2025-04-25 153652](https://github.com/user-attachments/assets/a1899a08-8999-4e96-816f-1085cf12b2c7)



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>
#include <string.h>
struct Student {
    char name[50];
    int age;
    float marks;
};

void printStudentInfo(struct Student s) {
    printf("Student Name: %s\n", s.name);
    printf("Student Age: %d\n", s.age);
    printf("Student Marks: %.2f\n", s.marks);
}
struct Student createStudent(char name[], int age, float marks) {
    struct Student newStudent;
    strcpy(newStudent.name, name);
    newStudent.age = age;
    newStudent.marks = marks;
    
    return newStudent;
}

int main() {
    struct Student student1 = {"Anu", 20, 88.5};
    printf("Passing structure as function argument:\n");
    printStudentInfo(student1);
    struct Student student2 = createStudent("Amitha", 22, 92.5);
    printf("\nReturning structure from function:\n");
    printStudentInfo(student2);
    return 0;
}
```
Output:
![Screenshot 2025-04-25 154218](https://github.com/user-attachments/assets/c965d3e7-9d0a-4c10-a61f-73d36b2b225f)


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    FILE *p;
    char name[100];

    printf("Enter the file name: ");
    scanf("%s", name);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error creating file.\n");
        return 1;
    }

    printf("File '%s' created successfully.\n", name);

    fclose(p);
    printf("File closed successfully.\n");

    return 0;
}
```
Output:
![Screenshot 2025-04-25 154922](https://github.com/user-attachments/assets/479e0a42-12d8-4dad-8992-b5f1028fb5ca)


Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```

```
Output:


//paste your output here






Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
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

Program:
```
#include <stdio.h>
struct Student {
    char name[50];
    int age;
    float marks;
};
void displayStudentDetails(struct Student s) {
    printf("\nStudent Details:\n");
    printf("Name: %s\n", s.name);
    printf("Age: %d\n", s.age);
    printf("Marks: %.2f\n", s.marks);
}

int main() {
    struct Student student1;
    printf("Enter student's name: ");
    scanf("%s", student1.name);
    printf("Enter student's age: ");
    scanf("%d", &student1.age);
    printf("Enter student's marks: ");
    scanf("%f", &student1.marks);
    displayStudentDetails(student1);
    return 0;
}
```
Output:
![Screenshot 2025-04-25 155914](https://github.com/user-attachments/assets/22868e8d-1c7c-4fec-8a1f-fd319a9d6b68)

Result:
Thus, the program is verified successfully
