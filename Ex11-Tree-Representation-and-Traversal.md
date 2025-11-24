# Ex11 Convert HashSet to ArrayList in Java
## DATE: 06-10-25
## AIM:
To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
## Algorithm
1.Start the program.

2.Create a HashSet to store a collection of distinct integers.

3.Add a few integers to the HashSet.

4.Create an ArrayList and initialize it with the elements of the HashSet.

5.Display the elements of both HashSet and ArrayList and End the program.

## Program:
```
/*
Program to To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
Developed by: SHAKTHI KUMAR S
RegisterNumber:  212222110043
*/

import java.util.*;

public class HashSetToArrayList {
    public static void main(String[] args) {
        HashSet<Integer> set = new HashSet<>();
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(40);
        set.add(50);

        System.out.println("HashSet: " + set);

        ArrayList<Integer> list = new ArrayList<>(set);
        System.out.println("ArrayList: " + list);
    }
}
```

## Output:

<img width="611" height="748" alt="514719400-446bb67e-e7e2-4c79-a139-aafbccb144b9" src="https://github.com/user-attachments/assets/12b4abc6-21b0-4caf-87c2-aad3d89f51b9" />


## Result:
The program successfully converts a collection of distinct integers stored in a HashSet into an ArrayList
