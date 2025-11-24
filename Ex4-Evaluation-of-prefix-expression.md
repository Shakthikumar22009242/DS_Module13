# Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
## AIM
To write a java function to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix.

## Algorithm
1. Read matrix dimensions
   Input the number of rows r and columns c.
2. Read elements of Matrix A
   Fill the 2D array A[r][c] by reading integers row-wise.
3. Read elements of Matrix B
   Fill the 2D array B[r][c] similarly by reading integers row-wise.
4. Add corresponding elements of both matrices
   For each position (i, j), compute A[i][j] + B[i][j]. 
5. Print the resulting matrix
   Output each sum in matrix form, one row per line.  

## Program:
```PY

import java.util.*;

public class MatrixAddShort {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int r = sc.nextInt(), c = sc.nextInt();
        int[][] A = new int[r][c], B = new int[r][c];

        for (int i = 0; i < r; i++)  
            for (int j = 0; j < c; j++)
                A[i][j] = sc.nextInt();

        for (int i = 0; i < r; i++)  
            for (int j = 0; j < c; j++)
                B[i][j] = sc.nextInt();

       
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++)
                System.out.print((A[i][j] + B[i][j]) + " ");
            System.out.println();
        }
    }
}

*/
```

## Output:


<img width="451" height="704" alt="image" src="https://github.com/user-attachments/assets/4100fb70-69a4-4f08-aa17-86d01d55c951" />


## Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.
