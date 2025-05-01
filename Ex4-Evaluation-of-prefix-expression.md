# EXERCISE 4: Evaluation of Prefix Expression

## DATE:
20.02.2025

##  AIM:
To write a C function to evaluate the given **prefix expression** using a **stack** and print the output from **inside the function**.

---

##  Algorithm:
1. Start the program.
2. Read the prefix expression from the user.
3. Initialize an empty stack.
4. Traverse the expression **from right to left**:
   - If the character is an **operand**, push it onto the stack.
   - If the character is an **operator**:
     - Pop two operands from the stack.
     - Apply the operator to them (`op1 operator op2`).
     - Push the result back onto the stack.
5. After the complete traversal, the final result is at the top of the stack.
6. Display the result.
7. End the program.

---

##  Program:
```c
/*
Program to evaluate the given prefix expression
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <ctype.h>
#include <math.h>
#include <string.h>

#define SIZE 100

int stack[SIZE];
int top = -1;

void push(int val) {
    stack[++top] = val;
}

int pop() {
    return stack[top--];
}

int evaluate(char prefix[]) {
    int i, op1, op2, res;
    char ch;

    // Start from rightmost character
    for(i = strlen(prefix) - 1; i >= 0; i--) {
        ch = prefix[i];

        if(isdigit(ch)) {
            push(ch - '0');  // Convert char digit to int
        }
        else {
            op1 = pop();
            op2 = pop();

            switch(ch) {
                case '+': res = op1 + op2; break;
                case '-': res = op1 - op2; break;
                case '*': res = op1 * op2; break;
                case '/': res = op1 / op2; break;
                case '^': res = pow(op1, op2); break;
                default:
                    printf("Invalid operator encountered.\n");
                    return 0;
            }

            push(res);
        }
    }

    printf("Result of the Prefix expression is: %d\n", stack[top]);
    return stack[top];
}

int main() {
    char prefix[SIZE];

    printf("Enter a prefix expression (e.g., +9*26): ");
    scanf("%s", prefix);

    evaluate(prefix);

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/e3ee316d-b469-48d4-ae0f-2b1492e4b167)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
