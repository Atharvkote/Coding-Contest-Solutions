### **Approach:**
We can solve this problem efficiently using the **frequency array (modulo counting)** approach. Instead of checking each pair explicitly (which takes \(O(n^2)\)), we use the following trick:

1. **Use an array `freq[]`** to store the count of elements with the same remainder when divided by `k`.
2. **Iterate through the array** and for each element:
   - Compute its remainder `rem = ar[i] % k`.
   - Find the complementary remainder `(k - rem) % k` that, when added to `rem`, gives a sum divisible by `k`.
   - Count how many such elements exist using the `freq` array.
   - Increment the count of `rem` in `freq`.

This reduces the time complexity to **\(O(n)\)** instead of **\(O(n^2)\)**.

---

### **C++ Code:**
```cpp
#include <iostream>
#include <vector>

using namespace std;

int divisibleSumPairs(int n, int k, vector<int>& ar) {
    vector<int> freq(k, 0);  // Frequency array to store remainder counts
    int count = 0;

    for (int i = 0; i < n; i++) {
        int rem = ar[i] % k;  // Find remainder
        int complement = (k - rem) % k;  // Find complement remainder
        
        count += freq[complement];  // Add valid pairs found so far
        
        freq[rem]++;  // Store current element remainder
    }

    return count;
}

int main() {
    // Sample Input
    int n = 6, k = 3;
    vector<int> ar = {1, 3, 2, 6, 1, 2};

    // Function Call
    cout << divisibleSumPairs(n, k, ar) << endl;

    return 0;
}
```

---

### **Sample Input & Output:**
#### **Input:**
```
6 3
1 3 2 6 1 2
```
#### **Output:**
```
5
```

---

### **Explanation:**
For `k = 3`, the valid pairs `(i, j)` are:
- `(0,2) → 1 + 2 = 3`
- `(0,5) → 1 + 2 = 3`
- `(1,3) → 3 + 6 = 9`
- `(2,4) → 2 + 1 = 3`
- `(4,5) → 1 + 2 = 3`

Thus, the answer is `5`.

---

### **Time Complexity Analysis:**
- **Optimized Approach:** \(O(n)\)  
  - Each element is processed **once** (storing frequency and checking valid pairs).
  - No nested loops, making it much faster than brute-force.

- **Brute Force Approach:** \(O(n^2)\)  
  - Iterates through all possible pairs, checking divisibility condition.

---

### **Why is This Approach Efficient?**
- Instead of iterating over all pairs, we use **modulo frequency counting**.
- **Each number is processed once**, reducing complexity from **\(O(n^2)\) to \(O(n)\)**.
