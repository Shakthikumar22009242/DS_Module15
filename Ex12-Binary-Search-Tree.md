# EXERCISE 12: Binary Search Tree – Insertion

## DATE:
18-03-2025

## AIM:
To write a C function to insert the elements in the binary search tree.

---

## Algorithm:
1. Define a structure for the binary search tree node.
2. Create a function to allocate memory and initialize a new node.
3. Create a function to insert an element into the binary search tree:
   - If the tree is empty, create a new node and return it.
   - If the data is less than the root’s data, insert it into the left subtree.
   - If the data is greater than the root’s data, insert it into the right subtree.
4. In the `main()` function, insert multiple elements by calling the insert function.
5. Optionally display the tree using inorder traversal to verify insertion.
6. End.

---

## Program:
```c
/*
Program to insert the elements in the binary search tree
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in BST
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

// Function to insert a node into BST
struct Node* insert(struct Node* root, int value) {
    if (root == NULL)
        return createNode(value);
    
    if (value < root->data)
        root->left = insert(root->left, value);
    else if (value > root->data)
        root->right = insert(root->right, value);
    
    return root;
}

// Function for inorder traversal
void inorder(struct Node* root) {
    if (root != NULL) {
        inorder(root->left);
        printf("%d ", root->data);
        inorder(root->right);
    }
}

int main() {
    struct Node* root = NULL;
    int elements[] = {50, 30, 20, 40, 70, 60, 80};
    int n = sizeof(elements) / sizeof(elements[0]);

    for (int i = 0; i < n; i++) {
        root = insert(root, elements[i]);
    }

    printf("Inorder traversal of the BST after insertion: ");
    inorder(root);
    printf("\n");

    return 0;
}
```

## Output:

![image](https://github.com/user-attachments/assets/d2d63130-f2fe-4124-a215-857d10f7d995)


## Result:
Thus, the C function to insert the elements in the binary search tree is implemented successfully.
