### **Problem Statement: Maximum Subarray Sum Modulo M**  

#### **Problem Description**  
You are given an array **`A`** of **`N`** integers and an integer **`M`**. Your task is to determine the **maximum possible sum of any subarray modulo `M`**.  

#### **Definitions**  
- A **subarray** is a contiguous sequence of elements from the array.  
- The **sum** of a subarray is the sum of its elements.  
- The **modulo operation (`x % M`)** finds the remainder when `x` is divided by `M`.  

#### **Function Signature**  
```  
maximumSum(A, M) -> integer  
```
**Parameters:**  
- `A`: A list/array of `N` integers.  
- `M`: A positive integer.  

**Returns:**  
- An integer representing the **maximum subarray sum modulo `M`**.  

---

### **Input Format**  
1. The first line contains an integer **`Q`** (number of test cases).  
2. Each test case consists of:  
   - An integer **`N`** (size of the array) and **`M`** (modulo divisor).  
   - A line containing **`N`** space-separated integers (elements of the array).  

---

### **Constraints**  
- \( 2 \leq N \leq 10^5 \)  _(Array length)_  
- \( 1 \leq M \leq 10^{15} \)  _(Modulo divisor)_  
- \( |A[i]| \leq 10^9 \)  _(Array elements)_  
- The sum over all test cases does not exceed \( 5 \times 10^6 \).  

---

### **Output Format**  
For each test case, print a **single integer**: the maximum sum of any subarray modulo **M**.  

---

### **Example**  
#### **Input**  
```
1  
5 7  
3 3 9 9 5  
```  
#### **Output**  
```
6  
```  

#### **Explanation**  
The subarrays and their sums modulo `7` are:  
- `{3}` → \(3 \mod 7 = 3\)  
- `{3,3}` → \(6 \mod 7 = 6\)  **(Maximum)**  
- `{3,3,9}` → \(15 \mod 7 = 1\)  
- `{9,9,5}` → \(23 \mod 7 = 2\)  
- `{3,3,9,9,5}` → \(29 \mod 7 = 1\)  

The **maximum subarray sum modulo `7`** is **6**.  
