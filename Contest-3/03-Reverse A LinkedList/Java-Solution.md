
### **Approach:**  
- Use three pointers: `prev`, `current`, and `next`.
- Traverse the list while adjusting the `next` pointers of each node to reverse the direction.
- Finally, return the new head of the reversed list.

---

### **Code Implementation:**  
```java
import java.util.*;

class SinglyLinkedListNode {
    int data;
    SinglyLinkedListNode next;

    SinglyLinkedListNode(int data) {
        this.data = data;
        this.next = null;
    }
}

public class ReverseLinkedList {
    
    // Function to reverse the linked list
    public static SinglyLinkedListNode reverse(SinglyLinkedListNode head) {
        SinglyLinkedListNode prev = null;
        SinglyLinkedListNode current = head;
        SinglyLinkedListNode next = null;

        while (current != null) {
            next = current.next;  // Store next node
            current.next = prev;  // Reverse current node's pointer
            prev = current;       // Move prev to current node
            current = next;       // Move current to next node
        }
        return prev;  // New head of the reversed list
    }

    // Function to print the linked list
    public static void printList(SinglyLinkedListNode head) {
        SinglyLinkedListNode temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    // Function to create a linked list from input
    public static SinglyLinkedListNode createList(Scanner scanner, int n) {
        if (n == 0) return null;

        SinglyLinkedListNode head = new SinglyLinkedListNode(scanner.nextInt());
        SinglyLinkedListNode current = head;

        for (int i = 1; i < n; i++) {
            current.next = new SinglyLinkedListNode(scanner.nextInt());
            current = current.next;
        }

        return head;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt(); // Number of test cases

        while (t-- > 0) {
            int n = scanner.nextInt(); // Number of elements in the linked list
            SinglyLinkedListNode head = createList(scanner, n);
            head = reverse(head);
            printList(head);
        }

        scanner.close();
    }
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

---

### **Alternative Approach (Recursion)**
If you want to reverse the linked list using recursion:
```java
public static SinglyLinkedListNode reverseRecursive(SinglyLinkedListNode head) {
    if (head == null || head.next == null) {
        return head; // Base case: if list is empty or single node
    }

    SinglyLinkedListNode newHead = reverseRecursive(head.next);
    head.next.next = head;
    head.next = null;

    return newHead;
}
```
