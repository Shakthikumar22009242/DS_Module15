# EXERCISE 15: Largest Element in BST

## DATE:
24-03-2025

## AIM:
To write a C program to find the largest value in a Binary Search Tree.

---

## Algorithm:
1. Define the structure of a node for the Binary Search Tree (BST).
2. Create functions for:
   - `insert` to add elements to the BST.
   - `findLargest` to traverse the tree and find the rightmost node (the largest element).
3. In the `main()` function, insert elements into the BST.
4. Call the `findLargest` function to retrieve and display the largest element.
5. End.

---

## Program:
```c
/*
Program to find and display the largest value in a Binary Search Tree
Developed by:SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <stdlib.h>

// Define the structure of the node in the Binary Search Tree
struct Node {
    int data;
    struct Node* left;
    struct Node* right;
};

// Function to create a new node
struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->left = newNode->right = NULL;
    return newNode;
}

// Function to insert a node into the Binary Search Tree
struct Node* insert(struct Node* root, int value) {
    if (root == NULL)
        return createNode(value);
    
    if (value < root->data)
        root->left = insert(root->left, value);
    else if (value > root->data)
        root->right = insert(root->right, value);

    return root;
}

// Function to find the largest element in the Binary Search Tree
struct Node* findLargest(struct Node* root) {
    while (root != NULL && root->right != NULL) {
        root = root->right;  // Move to the rightmost node
    }
    return root;
}

int main() {
    struct Node* root = NULL;

    // Insert elements into the BST
    root = insert(root, 50);
    root = insert(root, 30);
    root = insert(root, 20);
    root = insert(root, 40);
    root = insert(root, 70);
    root = insert(root, 60);
    root = insert(root, 80);

    // Find the largest element in the BST
    struct Node* largestNode = findLargest(root);

    if (largestNode != NULL)
        printf("The largest value in the Binary Search Tree is: %d\n", largestNode->data);
    else
        printf("The tree is empty.\n");

    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/b3b38e61-1893-4328-a966-efcd4f98076c)



## Result:
Thus, the C program to find the largest value in a Binary Search Tree is implemented successfully.
