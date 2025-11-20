# Ex5 Count Inversions in an Array
## DATE: 25.08.2025
## AIM:
To write a Java program  to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
1.Start the program.

2.Read the number of elements and store them in an array.

3.Use a modified merge sort to count inversions: .Recursively split the array into halves and count inversions in each half. .While merging two sorted halves,

4.count cross inversions when an element from the right half is placed before elements remaining in the left half.

5.Sum inversions from left half, right half, and cross inversions.

6.Display the total inversion count.

7.Stop the program. 

## Program:
```
/*
Program toto Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/
import java.util.Scanner;

public class CountInversions {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input size
        int n = sc.nextInt();
        int[] arr = new int[n];

        // Input array
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        // Count inversions
        long result = mergeSortAndCount(arr, 0, n - 1);
        System.out.println(result);
    }

    // Merge Sort function
    private static long mergeSortAndCount(int[] arr, int left, int right) {
        long count = 0;
        if (left < right) {
            int mid = (left + right) / 2;

            // Left subarray count
            count += mergeSortAndCount(arr, left, mid);

            // Right subarray count
            count += mergeSortAndCount(arr, mid + 1, right);

            // Merge count
            count += mergeAndCount(arr, left, mid, right);
        }
        return count;
    }

    // Merge two sorted halves and count inversions
    private static long mergeAndCount(int[] arr, int left, int mid, int right) {
        int[] leftArr = new int[mid - left + 1];
        int[] rightArr = new int[right - mid];

        // Copy data to temp arrays
        System.arraycopy(arr, left, leftArr, 0, leftArr.length);
        System.arraycopy(arr, mid + 1, rightArr, 0, rightArr.length);

        int i = 0, j = 0, k = left;
        long swaps = 0;

        // Merge process
        while (i < leftArr.length && j < rightArr.length) {
            if (leftArr[i] <= rightArr[j]) {
                arr[k++] = leftArr[i++];
            } else {
                arr[k++] = rightArr[j++];
                swaps += (mid + 1) - (left + i); // Count inversions
            }
        }

        // Copy remaining elements
        while (i < leftArr.length) {
            arr[k++] = leftArr[i++];
        }
        while (j < rightArr.length) {
            arr[k++] = rightArr[j++];
        }

        return swaps;
    }
}

```

## Output:
<img width="1232" height="337" alt="image" src="https://github.com/user-attachments/assets/1c867a54-301a-46d6-b6a9-c4446e695ec5" />




## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.
