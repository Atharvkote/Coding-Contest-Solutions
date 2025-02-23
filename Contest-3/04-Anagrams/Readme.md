### **Problem Statement:**
Given a string `s`, split it into two contiguous substrings of equal length. Determine the minimum number of character changes required to make the two substrings anagrams of each other.

### **Function Signature (Java & C++):**
```java
int anagram(String s);
```
```cpp
int anagram(string s);
```

### **Input Format:**
- The first line contains an integer `t` (1 ≤ t ≤ 100), the number of test cases.
- Each test case consists of a single string `s` (1 ≤ |s| ≤ 10⁴), consisting only of lowercase English letters (`'a'` to `'z'`).

### **Output Format:**
For each test case, print the minimum number of character changes required. If `s` has an odd length, print `-1` (since it cannot be split into two equal halves).

### **Constraints:**
- The length of `s` is between 1 and 10⁴.
- Only lowercase English letters are present in `s`.

### **Example Input & Output:**

#### **Input:**
```
6
aaabbb
ab
abc
mnop
xyyx
xaxbbbxx
```

#### **Output:**
```
3
1
-1
2
0
1
```

### **Explanation of Sample Cases:**
1. **`aaabbb`** → Split into `"aaa"` and `"bbb"`. Change all 3 `'a'` to `'b'`. **Output: 3**  
2. **`ab`** → Split into `"a"` and `"b"`. Change `'a'` to `'b'`. **Output: 1**  
3. **`abc`** → Odd length, cannot split equally. **Output: -1**  
4. **`mnop`** → Split into `"mn"` and `"op"`. Change `'m' → 'o'` and `'n' → 'p'`. **Output: 2**  
5. **`xyyx`** → Split into `"xy"` and `"yx"`. Already anagrams. **Output: 0**  
6. **`xaxbbbxx`** → Split into `"xaxb"` and `"bbxx"`. Change `'a' → 'b'`. **Output: 1**  

---
