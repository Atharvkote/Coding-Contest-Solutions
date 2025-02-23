
### **Approach:**
- Use three pointers: `prev`, `current`, and `next`.
- Traverse the list while adjusting the `next` pointers of each node to reverse the direction.
- Finally, return the new head of the reversed list.

---

### **Code Implementation:**
```cpp
#include <bits/stdc++.h>
using namespace std;

// Definition for singly-linked list node
struct SinglyLinkedListNode {
    int data;
    SinglyLinkedListNode* next;
    SinglyLinkedListNode(int val) : data(val), next(nullptr) {}
};

// Function to reverse the linked list
SinglyLinkedListNode* reverse(SinglyLinkedListNode* head) {
    SinglyLinkedListNode* prev = nullptr;
    SinglyLinkedListNode* current = head;
    SinglyLinkedListNode* next = nullptr;

    while (current) {
        next = current->next;  // Store next node
        current->next = prev;  // Reverse current node's pointer
        prev = current;        // Move prev to current node
        current = next;        // Move current to next node
    }
    
    return prev;  // New head of the reversed list
}

// Function to print the linked list
void printList(SinglyLinkedListNode* head) {
    while (head) {
        cout << head->data << " ";
        head = head->next;
    }
    cout << endl;
}

// Function to create a linked list from input
SinglyLinkedListNode* createList(vector<int>& values) {
    if (values.empty()) return nullptr;
    
    SinglyLinkedListNode* head = new SinglyLinkedListNode(values[0]);
    SinglyLinkedListNode* current = head;
    
    for (size_t i = 1; i < values.size(); i++) {
        current->next = new SinglyLinkedListNode(values[i]);
        current = current->next;
    }
    
    return head;
}

// Driver Code
int main() {
    int t;
    cin >> t; // Number of test cases
    
    while (t--) {
        int n;
        cin >> n; // Number of elements in the linked list
        vector<int> values(n);
        
        for (int i = 0; i < n; i++) {
            cin >> values[i]; // Input linked list elements
        }
        
        SinglyLinkedListNode* head = createList(values);
        head = reverse(head);
        printList(head);
    }

    return 0;
}
```

---

### **Explanation:**
1. **Reversing the List:**
   - We maintain `prev`, `current`, and `next` pointers.
   - We iterate through the list and adjust each node’s `next` pointer to point to the previous node.
   - The `prev` pointer holds the new head of the reversed list.

2. **Printing the List:**
   - The `printList` function iterates through the list and prints each node’s data.

3. **Creating a List:**
   - The `createList` function dynamically creates a linked list based on user input.

---

### **Complexity Analysis:**
- **Time Complexity:** \(O(n)\) (We traverse the list once)
- **Space Complexity:** \(O(1)\) (In-place reversal, no extra memory used)

---

### **Example Walkthrough:**
#### **Input:**
```
1
5
1 2 3 4 5
```
#### **Processing:**
- Original list: `1 → 2 → 3 → 4 → 5 → NULL`
- After reversal: `5 → 4 → 3 → 2 → 1 → NULL`
#### **Output:**
```
5 4 3 2 1
```
