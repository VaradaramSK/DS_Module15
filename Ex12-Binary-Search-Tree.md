# Ex12 Binary Search Tree
## DATE: 15-03-25
## AIM:
To write a C function to insert the elements in the binary search tree

## Algorithm
1. Start 
2. Check if the current node is NULL; if true, create a new node with the given key. 
3. Allocate memory for the new node, set its key, and initialize its left and right children to 
NULL. 
4. If the current node is not NULL, compare the key with the current node's key. 
5. If key <= node->key, recursively insert the key into the left subtree and update the left child 
pointer. 
6. If key > node->key, recursively insert the key into the right subtree and update the right 
child pointer. 
7. Return the current node after the insertion. 
8. End 

## Program:
```
/*
Program to insert the elements in the binary search tree
Developed by: Varadaram SK
RegisterNumber:  212223040232
*/
/*struct node {
   int key;
   struct node *left, *right;
};*/
struct node* insert(struct node* node, int key) {
    
    struct node* temp;
    temp = (struct node*)malloc(sizeof(struct node));
    temp->key = key;
    temp->right = temp->left = NULL;
    
    if (node == NULL)
        node = temp;
    else
    {
        struct node* cur;
        if (key < node->key)
        {
            cur = insert(node->left,key);
            node->left = cur;
        }
        if (key > node->key)
        {
            cur = insert(node->right,key);
            node->right = cur;
        }
        
    }
    return node;
}
```

## Output:

![image](https://github.com/user-attachments/assets/e0a99254-179c-46ea-a0cc-1cdf2e39ebf3)


## Result:
Thus, the C function to insert the elements in the binary search tree is implemented successfully.
