# Ex12 Add Elements from an Array into a TreeSet
## DATE: 06-10-25
## AIM:
To write a Java program that adds elements from an array into a TreeSet and displays the elements in sorted order.
## Algorithm
1.Start the program.

2.Initialize an array with integer elements.

3.Create an empty TreeSet.

4.Add all elements from the array into the TreeSet.

5.Display the elements of the TreeSet (which are automatically sorted).

6.Stop the program.  

## Program:
```
/*
Program that adds elements from an array into a TreeSet and displays the elements in sorted order.
Developed by: SHAKTHI KUMAR S
RegisterNumber:  212222110043
*/

import java.util.*;

public class ArrayToTreeSet {

    public static TreeSet<Integer> convertArrayToTreeSet(int[] arr) {
        List<Integer> list = new ArrayList<>();
        for(int x : arr){
            list.add(x);
        }
        
        TreeSet<Integer> treeSet = new TreeSet<>(list);
        return treeSet;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        TreeSet<Integer> treeSet = convertArrayToTreeSet(arr);
        System.out.println("Elements in TreeSet:");
        for (int num : treeSet) {
            System.out.println(num);
        }

        sc.close();
    }
}
```

## Output:
<img width="728" height="633" alt="514720326-22497514-1f81-4585-8cbf-b9b4ddd279ad" src="https://github.com/user-attachments/assets/8aa9b5c2-98af-4ee6-8ec8-1c863000790a" />



## Result:
The program successfully adds elements from an array into a TreeSet.
