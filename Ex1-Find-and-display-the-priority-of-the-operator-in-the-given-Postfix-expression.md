# EXERCISE 1: Display Operator Precedence in the Infix Expression

## DATE:
14.02.2025

## AIM:
To write a C program to find and display the priority of the operators in a given **Postfix expression**.

---

## Algorithm:
1. Start the program.
2. Read the postfix expression from the user.
3. Traverse each character in the postfix expression.
4. If the character is an operator, determine its precedence:
   - `^` → precedence 3 (highest)
   - `*`, `/`, `%` → precedence 2 (medium)
   - `+`, `-` → precedence 1 (lowest)
5. Display each operator along with its precedence.
6. End the program.

---

##  Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <ctype.h>

// Function to return precedence of an operator
int precedence(char op) {
    switch(op) {
        case '^': return 3;
        case '*':
        case '/':
        case '%': return 2;
        case '+':
        case '-': return 1;
        default: return 0; // Not an operator
    }
}

int main() {
    char postfix[100];
    int i;

    printf("Enter a postfix expression: ");
    scanf("%s", postfix);

    printf("\nOperator Precedence:\n");
    for(i = 0; postfix[i] != '\0'; i++) {
        if(postfix[i] == '+' || postfix[i] == '-' || postfix[i] == '*' || 
           postfix[i] == '/' || postfix[i] == '%' || postfix[i] == '^') {
            printf("Operator '%c' has precedence %d\n", postfix[i], precedence(postfix[i]));
        }
    }

    return 0;
}
```

## OUTPUT :-
![image](https://github.com/user-attachments/assets/8f988df7-6448-4f23-b8f4-8fdef5ff91c8)


## Result:
Thus, the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully and the operator precedence is displayed accurately.
