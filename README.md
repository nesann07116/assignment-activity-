# assignment-activity-
name :otrumai nesan vr
reg no:212224060183



Write a C program to traverse a 2D matrix and print the values until a negative number is found. Use break statement.

AIM:
 To Write a C program to traverse a 2D matrix and print the values until a negative number is found. Use break statement.

ALGORITHM:
```
Start
Declare variables for rows and columns
Input number of rows and columns
Declare a 2D array (matrix)
Input elements into the matrix
Traverse the matrix using nested loops:
Outer loop for rows
Inner loop for columns
For each element:
If the element is negative:
Exit the inner loop using break
Use a flag or condition to break the outer loop as well
Otherwise, print the element
Stop when a negative number is found
End
```
PROGRAM:
```
#include <stdio.h>

int main() {
    int rows, cols;
    
    printf("Enter number of rows and columns: ");
    scanf("%d %d", &rows, &cols);

    int matrix[rows][cols];

    // Input matrix elements
    printf("Enter matrix elements:\n");
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    printf("Traversing matrix:\n");

    int stop = 0;  // flag to stop outer loop

    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            if(matrix[i][j] < 0) {
                stop = 1;
                break;  // breaks inner loop
            }
            printf("%d ", matrix[i][j]);
        }
        if(stop == 1) {
            break;  // breaks outer loop
        }
        printf("\n");
    }

    return 0;
}
```
OUTPUT:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/2f3c6af4-f891-4985-86da-9162084cae75" />

RESULT:

Thus the verification of  C program to traverse a 2D matrix and print the values until a negative number is found. Use break statement.


2.Write a C program to print the numbers from 1 to 100 but avoid printing multiples of 3 and number containing digit 5(5,15,25,35,..). Use continue in the program.

AIM:
To C program to print the numbers from 1 to 100 but avoid printing multiples of 3 and number containing digit 5(5,15,25,35,..). Use continue in the program.

ALGORITHM:
```
Start
Initialize a loop from 1 to 100
For each number:
Check if the number is a multiple of 3
If yes, skip using continue
Check if the number contains digit 5
If yes, skip using continue
Otherwise, print the number
End loop
Stop

```
PROGRAM:
```
#include <stdio.h>

int containsDigit5(int num) {
    while (num > 0) {
        if (num % 10 == 5) {
            return 1; // digit 5 found
        }
        num /= 10;
    }
    return 0; // no digit 5
}

int main() {
    for (int i = 1; i <= 100; i++) {
        
        // Skip multiples of 3
        if (i % 3 == 0) {
            continue;
        }

        // Skip numbers containing digit 5
        if (containsDigit5(i)) {
            continue;
        }

        printf("%d ", i);
    }

    return 0;
}

```
OUTPUT:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/e516000a-89e6-4fba-8f25-2a77b0f492da" />

RESULT:
Thus the execution C program to print the numbers from 1 to 100 but avoid printing multiples of 3 and number containing digit 5(5,15,25,35,..). Use continue in the program.

3.Write a C program that performs division of two user inputs and uses goto  to handle errors like division by zero or invalid input by redirecting control for re-entry.

AIM :
To Write a C program that performs division of two user inputs and uses goto  to handle errors like division by zero or invalid input by redirecting control for re-entry.

ALGORITHM:
```
Start
Label the input section (e.g., start:)
Prompt user to enter two numbers
Read inputs
Validate input:
If input is invalid (non-numeric), redirect to start using goto
Check if divisor is zero:
If yes, display error and redirect to start
Perform division
Display result
End

```
PROGRAM:
```
#include <stdio.h>

int main() {
    float num1, num2, result;
    int status;

start:
    printf("Enter two numbers (numerator and denominator): ");

    status = scanf("%f %f", &num1, &num2);

    // Check for invalid input
    if (status != 2) {
        printf("Invalid input! Please enter numeric values.\n");

        // Clear input buffer
        while (getchar() != '\n');

        goto start;
    }

    // Check for division by zero
    if (num2 == 0) {
        printf("Error: Division by zero is not allowed.\n");
        goto start;
    }

    // Perform division
    result = num1 / num2;

    printf("Result = %.2f\n", result);

    return 0;
}

```
OUTPUT:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/4edcd6e4-0b4c-4efc-9dcd-01f672fe2732" />

RESULT:
Thus the verification of C program that performs division of two user inputs and uses goto  to handle errors like division by zero or invalid input by redirecting control for re-entry.

4.Write a C program for a number guessing game where the loop continues for wrong guesses, breaks on a correct guess, and exits the program using return if the user enters -1

AIM:
To Write a C program for a number guessing game where the loop continues for wrong guesses, breaks on a correct guess, and exits the program using return if the user enters -1

ALGORITHM:
```
Start
Set a fixed number (secret number)
Declare a variable for user guess
Start an infinite loop
Ask user to enter a guess
If guess is -1:
Exit program using return
If guess equals the secret number:
Print success message
Exit loop using break
Otherwise:
Print “Wrong guess, try again”
End loop
End

```

PROGRAM;
```
#include <stdio.h>

int main() {
    int secret = 7;   // predefined number
    int guess;

    printf("Number Guessing Game\n");
    printf("Enter -1 to quit\n");

    while (1) {
        printf("Enter your guess: ");
        scanf("%d", &guess);

        // Exit condition
        if (guess == -1) {
            printf("You exited the game.\n");
            return 0;
        }

        // Correct guess
        if (guess == secret) {
            printf("Correct! You guessed the number.\n");
            break;
        }

        // Wrong guess
        printf("Wrong guess! Try again.\n");
    }

    printf("Game Over.\n");

    return 0;
}

```

OUTPUT:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/745ed11a-ba3c-4221-9986-21549943ecec" />

RESULT:

Thus the execution of C program for a number guessing game where the loop continues for wrong guesses, breaks on a correct guess, and exits the program using return if the user enters -1

5.Write a C program that iterates through an array and, within a loop, uses continue  to skip negative elements, break when a zero is encountered, and return to exit the program if an element greater than 100 is found, then print the resulting behavior for the array {10, -5, 20, 0, 150, 30}.

AIM:

To Write a C program that iterates through an array and, within a loop, uses continue  to skip negative elements, break when a zero is encountered, and return to exit the program if an element greater than 100 is found, then print the resulting behavior for the array {10, -5, 20, 0, 150, 30}.

ALGORITHM:
```
Start
Initialize array: {10, -5, 20, 0, 150, 30}
Traverse the array using a loop
For each element:
If element < 0 → skip using continue
If element == 0 → stop loop using break
If element > 100 → exit program using return
Otherwise, print the element
End loop
End

```
PROGRAM:
```

#include <stdio.h>

int main() {
    int arr[] = {10, -5, 20, 0, 150, 30};
    int n = sizeof(arr) / sizeof(arr[0]);

    printf("Processing array:\n");

    for (int i = 0; i < n; i++) {

        // Skip negative numbers
        if (arr[i] < 0) {
            continue;
        }

        // Break when zero is found
        if (arr[i] == 0) {
            printf("Zero encountered. Stopping loop.\n");
            break;
        }

        // Exit program if element > 100
        if (arr[i] > 100) {
            printf("Element greater than 100 found. Exiting program.\n");
            return 0;
        }

        // Print valid element
        printf("%d ", arr[i]);
    }

    printf("\nProgram finished.\n");

    return 0;
}

```

OUTPUT:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/aa5de7dc-9b9d-485d-82b9-4366a26016a6" />

RESULT:
Thus the verification of C program that iterates through an array and, within a loop, uses continue  to skip negative elements, break when a zero is encountered, and return to exit the program if an element greater than 100 is found, then print the resulting behavior for the array {10, -5, 20, 0, 150, 30}.
