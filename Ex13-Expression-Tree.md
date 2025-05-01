# EXERCISE 13: Expression Tree – Construction and Traversal

## DATE:
19-03-2025

## AIM:
To write a C function to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order, Pre-order, and Post-order traversal.

---

## Algorithm:

1. Start the program.
2. Define a structure for the expression tree node.
3. Create functions to perform:
   - `createNode` for node creation.
   - `isOperator` to check if a character is an operator.
4. Use a stack to construct the expression tree:
   - For each character in the postfix expression:
     - If it is an operand, create a node and push it onto the stack.
     - If it is an operator, pop two nodes, create a new node with the operator, set them as children, and push the new node.
5. Perform tree traversals:
   - In-order (Left, Root, Right)
   - Pre-order (Root, Left, Right)
   - Post-order (Left, Right, Root)
6. End.

---

## Program:
```c
/*
Program to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order, Pre-order and Post-order traversal.
Developed by: SHAKTHI KUMAR S
RegisterNumber: 212222110043
*/

#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

#define MAX 50

// Define structure for node
struct Node {
    char data;
    struct Node* left;
    struct Node* right;
};

// Stack for nodes
struct Node* stack[MAX];
int top = -1;

// Stack operations
void push(struct Node* node) {
    stack[++top] = node;
}

struct Node* pop() {
    return stack[top--];
}

// Create new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->left = newNode->right = NULL;
    return newNode;
}

// Check if character is operator
int isOperator(char ch) {
    return (ch == '+' || ch == '-' || ch == '*' || ch == '/');
}

// Inorder traversal
void inorder(struct Node* root) {
    if (root != NULL) {
        inorder(root->left);
        printf("%c ", root->data);
        inorder(root->right);
    }
}

// Preorder traversal
void preorder(struct Node* root) {
    if (root != NULL) {
        printf("%c ", root->data);
        preorder(root->left);
        preorder(root->right);
    }
}

// Postorder traversal
void postorder(struct Node* root) {
    if (root != NULL) {
        postorder(root->left);
        postorder(root->right);
        printf("%c ", root->data);
    }
}

int main() {
    char postfix[MAX];
    printf("Enter the postfix expression: ");
    scanf("%s", postfix);

    int i;
    struct Node* t, *t1, *t2;

    for (i = 0; postfix[i] != '\0'; i++) {
        if (isalnum(postfix[i])) {
            t = createNode(postfix[i]);
            push(t);
        } else if (isOperator(postfix[i])) {
            t = createNode(postfix[i]);
            t1 = pop();
            t2 = pop();
            t->right = t1;
            t->left = t2;
            push(t);
        }
    }

    struct Node* root = pop();

    printf("\nIn-order traversal: ");
    inorder(root);
    printf("\nPre-order traversal: ");
    preorder(root);
    printf("\nPost-order traversal: ");
    postorder(root);
    printf("\n");

    return 0;
}
```

## Output:
![image](https://github.com/user-attachments/assets/906f9a85-0b9b-4b46-939b-8693505c3315)



## Result:
Thus, the C program to display the Expression Tree in the format of In-order ,Pre-order and Post-order traversal.
