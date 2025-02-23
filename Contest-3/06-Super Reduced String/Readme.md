### **Problem Statement: Super Reduced String**  

#### **Objective:**  
You are given a string **`s`** consisting of only lowercase English letters. Your task is to repeatedly perform the following operation:  
- Select **any two adjacent matching characters** and remove them from the string.  
- Continue this process until **no adjacent matching characters remain**.  
- If the resulting string is empty, return `"Empty String"`; otherwise, return the reduced string.  

#### **Input Format:**  
- A **single string** `s` of length **1 ≤ |s| ≤ 100**.

#### **Output Format:**  
- Return the **final reduced string** after performing all possible operations.  
- If the string is empty after reductions, return `"Empty String"`.

---

### **Examples & Explanations:**

#### **Example 1**  
🔹 **Input:**  
```
abba
```
🔹 **Process:**  
1. Remove "bb" → `"aa"`
2. Remove "aa" → `""` (Empty String)  

🔹 **Output:**  
```
Empty String
```

---

#### **Example 2**  
🔹 **Input:**  
```
aaabccddd
```
🔹 **Process:**  
1. Remove "aa" → `"bccddd"`
2. Remove "cc" → `"bddd"`
3. Remove "dd" → `"bd"`
  
🔹 **Output:**  
```
bd
```

---

#### **Example 3**  
🔹 **Input:**  
```
abc
```
🔹 **Process:**  
- No adjacent matching characters exist.  

🔹 **Output:**  
```
abc
```

---

### **Constraints:**
- \( 1 \leq |s| \leq 100 \)  
- \( s \) consists of **only lowercase English letters (a-z)**.

---

### **Approach:**
1. **Use a Stack-based Approach**:
   - Iterate through the string one character at a time.
   - If the **top element of the stack matches the current character**, remove the top element (i.e., delete the adjacent pair).
   - Otherwise, push the character onto the stack.

2. **Reconstruct the String**:
   - If the stack is empty, return `"Empty String"`.
   - Otherwise, return the remaining characters in order.

### **Time Complexity Analysis:**
- **Each character is pushed and popped at most once** → **\(O(n)\)**
- **Space Complexity**: **\(O(n)\)** in the worst case (when no adjacent pairs exist).  

Would you like further clarifications or alternative approaches? 🚀