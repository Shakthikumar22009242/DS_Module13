# EXERCISE 5: Stack Operations in Infix to Postfix Conversion

## 📅 DATE:
21.02.2025

## AIM:
To write a C program to perform **push and pop operations** on a stack during the **infix to postfix conversion** process.

---

##  Algorithm:
1. Start the program.
2. Define a stack with push and pop functions.
3. Read an infix expression from the user.
4. Traverse the infix expression:
   - If an **operand**, add it directly to the postfix expression.
   - If an **operator**, perform:
     - **Push**: if the stack is empty or precedence of current operator is higher than top of stack.
     - **Pop**: while top of the stack has higher or equal precedence.
   - If `'('`, push to stack.
   - If `')'`, pop until `'('` is encountered.
5. After traversal, pop all remaining operators from the stack.
6. Display the postfix expression and demonstrate stack push/pop operations.
7. End the program.

---

## Program:
```c
/*
Program to perform push and pop operations in infix to postfix conversion
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <ctype.h>
#include <string.h>

#define SIZE 100

char stack[SIZE];
int top = -1;

// Push function
void push(char ch) {
    stack[++top] = ch;
    printf("Pushed '%c' to stack\n", ch);
}

// Pop function
char pop() {
    if(top == -1)
        return -1;
    char popped = stack[top--];
    printf("Popped '%c' from stack\n", popped);
    return popped;
}

// Precedence function
int precedence(char ch) {
    switch(ch) {
        case '^': return 3;
        case '*':
        case '/':
        case '%': return 2;
        case '+':
        case '-': return 1;
        default: return 0;
    }
}

int isOperator(char ch) {
    return ch == '+' || ch == '-' || ch == '*' || ch == '/' || ch == '%' || ch == '^';
}

int main() {
    char infix[SIZE], postfix[SIZE];
    int i, j = 0;
    char ch, temp;

    printf("Enter an infix expression: ");
    scanf("%s", infix);

    for(i = 0; i < strlen(infix); i++) {
        ch = infix[i];

        if(isalnum(ch)) {
            postfix[j++] = ch;
        }
        else if(ch == '(') {
            push(ch);
        }
        else if(ch == ')') {
            while((temp = pop()) != '(') {
                postfix[j++] = temp;
            }
        }
        else if(isOperator(ch)) {
            while(top != -1 && precedence(stack[top]) >= precedence(ch)) {
                postfix[j++] = pop();
            }
            push(ch);
        }
    }

    while(top != -1) {
        postfix[j++] = pop();
    }

    postfix[j] = '\0';

    printf("\nPostfix expression: %s\n", postfix);

    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/7a3e999c-d0a2-464d-a826-fd23bac44119)



## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
