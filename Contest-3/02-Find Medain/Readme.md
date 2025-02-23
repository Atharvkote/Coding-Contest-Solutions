### **Problem Statement: Find the Median**  

#### **Description**  
The median of a list of numbers is the middle element when the numbers are arranged in **ascending order**. Given an **odd-sized** list of integers, determine the median.

#### **Input Format**  
- The first line contains an integer **n** (**1 < n < 1,000,001**) – the size of the list.  
- The second line contains **n** space-separated integers **arr[i]** (**-10,000 ≤ arr[i] ≤ 10,000**).  
- The value of **n** is guaranteed to be **odd**.

#### **Output Format**  
- Print a single integer representing the median.

#### **Constraints**  
- \(1 < n < 1,000,001\)  
- \( n \) is always **odd**  
- \( -10,000 \leq arr[i] \leq 10,000 \)  

---

### **Example 1**  

#### **Input:**  
```
7
0 1 2 4 6 5 3
```
#### **Sorted List:**  
```
[0, 1, 2, 3, 4, 5, 6]
```
#### **Output:**  
```
3
```

---

### **Example 2**  

#### **Input:**  
```
5
5 3 1 2 4
```
#### **Sorted List:**  
```
[1, 2, 3, 4, 5]
```
#### **Output:**  
```
3
```

---

### **Approach**  
1. **Sort the list** in ascending order.  
2. **Find the middle index** using `n / 2`.  
3. **Return the element at the middle index** as the median.  

---

### **Time Complexity**  
- **Sorting the list:** `O(n log n)` (using an efficient sorting algorithm like QuickSort or MergeSort).  
- **Finding the median:** `O(1)` (direct index access).  
- **Overall Complexity:** **O(n log n)**.  

This ensures efficiency for input sizes up to **1,000,000** as per the problem constraints. 🚀