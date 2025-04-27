# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
int main() {
    int length, breadth, area;
    int *ptrLength = &length, *ptrBreadth = &breadth, *ptrArea = &area;
    printf("Enter the length of the rectangle: ");
    scanf("%d", ptrLength);
    printf("Enter the breadth of the rectangle: ");
    scanf("%d", ptrBreadth);
    *ptrArea = (*ptrLength) * (*ptrBreadth);
    printf("Area of the rectangle: %d\n", *ptrArea);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/420c8f03-4563-4e62-b910-13db472ef3e8)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str = (char *)malloc(8 * sizeof(char)); // 7 characters + null terminator
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    str = "WELCOME";
    printf("%s\n", str);
    free(str);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/7674e41e-623d-480d-807c-8ffcf61f544f)



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.


# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

// Define the structure to store student information
struct Student {
    char name[50];
    int roll_number;
    float marks;
};

int main() {
    struct Student student;
    printf("Enter student's name: ");
    fgets(student.name, sizeof(student.name), stdin); 
    printf("Enter roll number: ");
    scanf("%d", &student.roll_number);
    printf("Enter marks: ");
    scanf("%f", &student.marks);
    printf("\nStudent Information:\n");
    printf("Name: %s", student.name);
    printf("Roll Number: %d\n", student.roll_number);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/72091913-6978-437c-9514-1e03447ea4b0)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
struct Employee {
    int id;
    char name[50];
    float basic_salary;
    float hra;
    float da;
    float gross_salary;
};

void calculateGrossSalary(struct Employee* emp) {
    emp->hra = emp->basic_salary * 0.20;
    emp->da = emp->basic_salary * 0.50;
    emp->gross_salary = emp->basic_salary + emp->hra + emp->da;
}

int main() {
    struct Employee employees[3];
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);
        printf("ID: ");
        scanf("%d", &employees[i].id);
        getchar(); 
        printf("Name: ");
        fgets(employees[i].name, sizeof(employees[i].name), stdin);
        printf("Basic Salary: ");
        scanf("%f", &employees[i].basic_salary);
        calculateGrossSalary(&employees[i]);
    }

    printf("\nEmployee Details:\n");
    for (int i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("ID: %d\n", employees[i].id);
        printf("Name: %s", employees[i].name);
        printf("Basic Salary: %.2f\n", employees[i].basic_salary);
        printf("HRA: %.2f\n", employees[i].hra);
        printf("DA: %.2f\n", employees[i].da);
        printf("Gross Salary: %.2f\n", employees[i].gross_salary);
    }

    return 0;
}

```
 ## OUTPUT
![image](https://github.com/user-attachments/assets/88fc29e7-c3b4-4f81-85fe-d633fa3fd283)

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>
struct Student {
    char name[50];
    int marks[5];
    int total;
    float average;
};
int main() {
    struct Student students[3];  
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Student %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", students[i].name);

        students[i].total = 0;
        for (int j = 0; j < 5; j++) {
            printf("Marks for subject %d: ", j + 1);
            scanf("%d", &students[i].marks[j]);
            students[i].total += students[i].marks[j];
        }
        students[i].average = students[i].total / 5.0;
    }
    for (int i = 0; i < 3; i++) {
        printf("\nStudent %d Details:\n", i + 1);
        printf("Name: %s\n", students[i].name);
        printf("Total Marks: %d\n", students[i].total);
        printf("Average Marks: %.2f\n", students[i].average);
    }

    return 0;
}

```

## OUTPUT

 ![image](https://github.com/user-attachments/assets/711742ac-e561-4506-b3e4-e233417e9f33)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


