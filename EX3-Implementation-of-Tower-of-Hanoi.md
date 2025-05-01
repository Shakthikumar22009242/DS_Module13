#  EXERCISE 3: Implementation of Tower of Hanoi

## DATE:
19.02.2025

## AIM:
To write a C program to implement the **Tower of Hanoi** problem using **recursion**.

---

## Algorithm:
1. Start the program.
2. Define a recursive function `hanoi(n, source, auxiliary, destination)`:
   - If `n == 1`, move the disk from source to destination.
   - Else:
     - Recursively move `n-1` disks from source to auxiliary using destination as helper.
     - Move the remaining disk from source to destination.
     - Recursively move `n-1` disks from auxiliary to destination using source as helper.
3. In the `main()` function:
   - Read the number of disks from the user.
   - Call the `hanoi()` function with appropriate arguments.
4. End the program.

---

## 💻 Program:
```
/*
Program to implement Tower of Hanoi
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>

void hanoi(int n, char source, char auxiliary, char destination) {
    if (n == 1) {
        printf("Move disk 1 from %c to %c\n", source, destination);
        return;
    }
    hanoi(n - 1, source, destination, auxiliary);
    printf("Move disk %d from %c to %c\n", n, source, destination);
    hanoi(n - 1, auxiliary, source, destination);
}

int main() {
    int n;
    printf("Enter the number of disks: ");
    scanf("%d", &n);
    
    printf("\nSteps to solve Tower of Hanoi:\n");
    hanoi(n, 'A', 'B', 'C');
    
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/ae4b0fce-3381-4722-bcee-67d29f25be28)


## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
