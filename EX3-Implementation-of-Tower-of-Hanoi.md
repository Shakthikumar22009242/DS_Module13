# EX3 Write a program to count the number of digits in an integer.
## DATE:18/08/2025
## AIM:
To write a JAVA program to implement Tower of Hanoi
## Algorithm
1. Read the input number
   Take an integer num from the user.
2. Convert the number to a non-negative value
   Use Math.abs(num) and store it in n to handle negative numbers.
3. Check if the number is zero
   If n == 0, set digit count to 1 (since zero has one digit).
4. Count digits for non-zero numbers
   Repeatedly divide n by 10 and increment the counter until n becomes 0.
5.  Display the digit count
    Output the total number of digits. 

## Program:
```py

import java.util.Scanner;

public class CountDigits {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();

        int count = 0;
        int n = Math.abs(num); 

        if (n == 0) {
            count = 1; 
        } else {
            while (n > 0) {
                n /= 10; 
                count++;
            }
        }

        System.out.println("Number of digits: " + count);
    }
}

```

## Output:
<img width="650" height="382" alt="image" src="https://github.com/user-attachments/assets/2a10a83f-b4ec-455f-aae2-10f45546b7bd" />



## Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.
