### **Problem Statement: Reverse a Singly Linked List**  

#### **Objective:**  
Given the head pointer of a singly linked list, reverse the linked list by modifying the `next` pointers of the nodes. Return the new head of the reversed list.

#### **Input:**  
- An integer **T** (1 ≤ T ≤ 10), the number of test cases.  
- For each test case:  
  - An integer **N** (1 ≤ N ≤ 1000), the number of elements in the linked list.  
  - **N** space-separated integers (1 ≤ list[i] ≤ 1000), representing the values of the nodes in the linked list.

#### **Output:**  
- Print the elements of the reversed linked list for each test case.

#### **Example:**  
**Input:**  
```
1
5
1 2 3 4 5
```
**Output:**  
```
5 4 3 2 1
```

#### **Explanation:**  
- The given linked list: `1 → 2 → 3 → 4 → 5 → NULL`  
- After reversing: `5 → 4 → 3 → 2 → 1 → NULL`  
- The new head of the list is `5`, and the order of elements is reversed.

#### **Constraints:**  
- The reversal must be done **in place** by modifying the `next` pointers of the nodes.  
- No additional data structures (such as arrays or stacks) should be used for storing node values.  
- The function should handle cases where the list is empty (i.e., head is `NULL`).  

Would you like any refinements or additional constraints? 🚀