#  EXERCISE 2: Conversion of Infix Expression into Postfix Expression

##  DATE:
15.02.2025

## AIM:
To write a C program to convert the **infix expression** into **postfix form** using **stack**, by following operator precedence and associativity rules.

---

##  Algorithm:
1. Start the program.
2. Read the infix expression from the user.
3. Initialize an empty stack for operators and an output array for the postfix result.
4. Traverse the infix expression from left to right:
   - If the character is an **operand**, add it to the postfix expression.
   - If the character is an **operator**:
     - Pop from the stack while the stack is not empty and the precedence of the top operator is **greater than or equal to** the current operator.
     - Push the current operator onto the stack.
   - If the character is `'('`, push it onto the stack.
   - If the character is `')'`, pop from the stack until `'('` is encountered.
5. After the expression is scanned, pop any remaining operators from the stack and append them to the postfix result.
6. Display the postfix expression.
7. End the program.

---

##  Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <ctype.h>
#include <string.h>

#define SIZE 100

char stack[SIZE];
int top = -1;

void push(char c) {
    stack[++top] = c;
}

char pop() {
    if(top == -1)
        return -1;
    return stack[top--];
}

int precedence(char c) {
    switch(c) {
        case '^': return 3;
        case '*':
        case '/':
        case '%': return 2;
        case '+':
        case '-': return 1;
        default: return 0;
    }
}

int isOperator(char c) {
    return c == '+' || c == '-' || c == '*' || c == '/' || c == '%' || c == '^';
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
            while((temp = pop()) != '(')
                postfix[j++] = temp;
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

    printf("Postfix expression: %s\n", postfix);

    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/b7b7a818-7051-44e7-9e6a-b3ba9872dd9f)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
