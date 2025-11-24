# Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap
## DATE: 06-10-25
## AIM:
To implement a program that tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

## Algorithm
1. Start the program.

2. Create a LinkedHashMap to store numbers and their frequency counts.

3. For each incoming number in the stream:

4. Increment its count in the map.

5. Iterate through the map to find the first number with a count of 1.

6. Display the first unique number.

7. Stop the program. 

## Program:
```
/*
Program to tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.
Developed by: SHAKTHI KUMAR S
RegisterNumber:  212222110043
*/

import java.util.*;

public class FirstUniqueNumberStream {

    public static void processStream(int n, Scanner sc) {
        LinkedHashMap<Integer, Integer> freqMap = new LinkedHashMap<>();
        for(int i=0; i<n; i++){
            int current = sc.nextInt();
            
            freqMap.put(current, freqMap.getOrDefault(current, 0)+1);
            
            int fUniq = -1;
            
            for(Map.Entry<Integer, Integer> entry : freqMap.entrySet()){
                if(entry.getValue() == 1){
                    fUniq = entry.getKey();
                    break;
                }
            }
            
            if(fUniq != -1){
                System.out.println("First unique number: "+fUniq);
            }else{
                System.out.println("No unique number");
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        processStream(n, sc);
        sc.close();
    }
}
```

## Output:

<img width="860" height="719" alt="514892746-419d5d2f-f551-409c-be4c-d1225fdba393" src="https://github.com/user-attachments/assets/5acd9373-f22d-4282-9f3e-134c221efc79" />


## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.
