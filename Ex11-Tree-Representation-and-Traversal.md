# EXERCISE 11: Tree Representation and Traversal – Postorder Traversal

## DATE:
17-03-2025

## AIM:
To write a C function to perform post order traversal of a binary tree.

---

## Algorithm:
1. Define a structure for the binary tree node.
2. Create a binary tree manually or using dynamic memory allocation.
3. Implement the `postorder` traversal function:
   - If the node is not NULL:
     - Recursively call `postorder(left subtree)`
     - Recursively call `postorder(right subtree)`
     - Process the current node (print its value)
4. Call the postorder function with the root node.
5. End.

---

## Program:
```c
/*
Program to perform post order traversal of a binary tree.
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <stdlib.h>

// Define a structure for tree node
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

// Function for postorder traversal
void postorder(struct Node* root) {
    if (root == NULL)
        return;
    postorder(root->left);
    postorder(root->right);
    printf("%d ", root->data);
}

int main() {
    // Creating a simple binary tree
    /*
            1
           / \
          2   3
         / \
        4   5
    */
    struct Node* root = createNode(1);
    root->left = createNode(2);
    root->right = createNode(3);
    root->left->left = createNode(4);
    root->left->right = createNode(5);

    printf("Postorder traversal of the binary tree: ");
    postorder(root);
    printf("\n");

    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/3edaf7b6-2631-4115-bbd8-6d7139efa9b4)



## Result:
Thus, the function to perform post order traversal of a binary tree is implemented successfully
