# Ex15 Value Existence Check in a TreeMap
## DATE: 06-10-25
## AIM:
To write a Java program that checks whether a given value exists in a TreeMap.

## Algorithm
1. Create a TreeMap to store key–value pairs.   
2. Insert some sample key–value pairs into the TreeMap.
3. Display the contents of the TreeMap.
4. Use the containsValue() method to check whether a specific value exists in the map
5. Display the result based on the check.
  

## Program:
```
/*
Program to checks whether a given value exists in a TreeMap.
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/


import java.util.*;

public class TreeMapValueExistenceCheck {

    public static void checkValue(TreeMap<Integer, String> map, String searchValue) {
        if(map.containsValue(searchValue)){
            System.out.println("Value \""+searchValue+"\" exists in the TreeMap.");
        }else{
            System.out.println("Value \""+searchValue+"\" does not exist in the TreeMap.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        TreeMap<Integer, String> map = new TreeMap<>();

        int n = sc.nextInt();

        for (int i = 0; i < n; i++) {
            int key = sc.nextInt();
            sc.nextLine();  
            String value = sc.nextLine();
            map.put(key, value);
        }
        String searchValue = sc.nextLine();

        checkValue(map, searchValue);
        sc.close();
    }
}
```

## Output:


<img width="1091" height="793" alt="514963263-f4bd3cf4-c0ae-4991-81d3-2653f1dc3e8e" src="https://github.com/user-attachments/assets/4e667ed3-56b5-4a0f-be44-a89fda224de0" />

## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.
