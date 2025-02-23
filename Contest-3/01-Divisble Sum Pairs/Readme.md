## **Problem Statement: Divisible Sum Pairs**  

### **Objective:**  
Given an array of integers and a positive integer **k**, determine the number of pairs **(i, j)** such that:  
- \( 0 \leq i < j < n \)  
- \( (arr[i] + arr[j]) \) is **divisible by k**  

---

### **Function Description**  
Implement the function:  
```java
public static int divisibleSumPairs(int n, int k, int[] arr)
```
#### **Parameters:**
- `int n` → Number of elements in the array.
- `int k` → The divisor.
- `int[] arr` → An array of **n** integers.

#### **Returns:**  
- An **integer** representing the count of valid pairs.

---

### **Constraints:**  
- \( 2 \leq n \leq 100 \)  
- \( 1 \leq k \leq 100 \)  
- \( 1 \leq arr[i] \leq 100 \)  

---

### **Input Format:**  
1. The first line contains **two space-separated integers**: `n` (size of the array) and `k` (divisor).  
2. The second line contains **n space-separated integers**, the elements of `arr`.

---

### **Output Format:**  
Print a **single integer**: the number of valid pairs.

---

## **Example 1**  

### **Input:**  
```
6 3
1 3 2 6 1 2
```
### **Processing:**  
Valid pairs whose sum is divisible by `3`:
- (0,2) → 1 + 2 = 3 ✅
- (0,5) → 1 + 2 = 3 ✅
- (1,3) → 3 + 6 = 9 ✅
- (2,4) → 2 + 1 = 3 ✅
- (4,5) → 1 + 2 = 3 ✅

### **Output:**  
```
5
```

---

## **Example 2**  

### **Input:**  
```
5 4
4 8 12 16 20
```
### **Processing:**  
Valid pairs whose sum is divisible by `4`:
- (0,1) → 4 + 8 = 12 ✅
- (0,2) → 4 + 12 = 16 ✅
- (0,3) → 4 + 16 = 20 ✅
- (0,4) → 4 + 20 = 24 ✅
- (1,2) → 8 + 12 = 20 ✅
- (1,3) → 8 + 16 = 24 ✅
- (1,4) → 8 + 20 = 28 ✅
- (2,3) → 12 + 16 = 28 ✅
- (2,4) → 12 + 20 = 32 ✅
- (3,4) → 16 + 20 = 36 ✅

### **Output:**  
```
10
```
