# EXERCISE 14: Heap Tree – Deletion

## DATE:
21-03-2025

## AIM:
To write a C function to delete an element in a Heap Tree.

---

## Algorithm:
1. Start the program.
2. Define a structure for the heap tree.
3. Create a function to delete the root element from the heap:
   - Replace the root with the last element.
   - Decrease the heap size.
   - Apply the heapify process to restore the heap property (Max Heap or Min Heap).
4. In the `main()` function:
   - Insert elements into the heap.
   - Display the heap before and after deletion.
5. End.

---

## Program:
```c
/*
Program to delete an element in a Heap Tree
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <stdlib.h>

// Define a structure for the heap tree
struct Heap {
    int* arr;
    int size;
    int capacity;
};

// Function to swap two elements
void swap(int* x, int* y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

// Heapify function to maintain the heap property
void heapify(struct Heap* h, int i) {
    int largest = i;
    int left = 2 * i + 1;
    int right = 2 * i + 2;

    if (left < h->size && h->arr[left] > h->arr[largest])
        largest = left;
    if (right < h->size && h->arr[right] > h->arr[largest])
        largest = right;

    if (largest != i) {
        swap(&h->arr[i], &h->arr[largest]);
        heapify(h, largest);
    }
}

// Function to delete an element (the root) from the heap
void deleteElement(struct Heap* h) {
    if (h->size == 0) {
        printf("Heap is empty\n");
        return;
    }

    // Replace the root with the last element
    h->arr[0] = h->arr[h->size - 1];
    h->size--;

    // Restore the heap property
    heapify(h, 0);
}

// Function to insert an element into the heap
void insert(struct Heap* h, int key) {
    if (h->size == h->capacity) {
        printf("Heap is full\n");
        return;
    }

    // Insert the new element at the end
    h->size++;
    h->arr[h->size - 1] = key;

    // Fix the heap property if it is violated
    for (int i = h->size / 2 - 1; i >= 0; i--)
        heapify(h, i);
}

// Function to display the heap
void display(struct Heap* h) {
    for (int i = 0; i < h->size; i++) {
        printf("%d ", h->arr[i]);
    }
    printf("\n");
}

int main() {
    // Create a heap with a maximum capacity of 10 elements
    struct Heap h;
    h.capacity = 10;
    h.size = 0;
    h.arr = (int*)malloc(h.capacity * sizeof(int));

    // Insert elements into the heap
    insert(&h, 10);
    insert(&h, 20);
    insert(&h, 30);
    insert(&h, 40);
    insert(&h, 50);
    insert(&h, 60);
    
    printf("Heap before deletion: ");
    display(&h);

    // Delete the root element (largest element in max heap)
    deleteElement(&h);

    printf("Heap after deletion: ");
    display(&h);

    free(h.arr);
    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/9540cbe5-974e-4afd-8dfb-05cf3f0f7142)



## Result:
Thus, the function to delete an element in a Heap Tree is implemented successfully.
