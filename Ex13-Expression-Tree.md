# Ex13 Fill the First 10 Elements of an Array with a Constant using Arrays.fill()
## DATE: 06-10-25

## AIM:
To write a Java program that fills the first 10 elements of an array with a constant value using the Arrays.fill() method.
## Algorithm
1. Start the program.

2. Create an integer array of size 10.
   
3. Use Arrays.fill() to assign a constant value to all 10 elements.
   
4. Print the array elements using Arrays.toString().
   
5. End the program.

## Program:
```
/*
Program to FILL the first 10 elements of an array with a constant value using the Arrays.fill() method.
Developed by: SHAKTHI KUMAR S
RegisterNumber:  212222110043
*/

import java.util.*;

public class FillArrayUsingArraysFill {

    public static int[] fillArray(int size, int value) {
        int[] arr = new int[size];
        Arrays.fill(arr, value);
        return arr;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int value = sc.nextInt();
        int[] arr = fillArray(10, value);
        System.out.println("Array elements:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
        sc.close();
    }
}
```

## Output:

<img width="783" height="387" alt="514883530-7b71119b-0fcd-4cb7-9860-6b99824e0355" src="https://github.com/user-attachments/assets/bb4df078-35b0-454c-811d-936d6a374bad" />


## Result:
